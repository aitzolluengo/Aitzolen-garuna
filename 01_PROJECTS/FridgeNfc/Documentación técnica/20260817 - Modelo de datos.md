---
fecha: 2026-08-17
tags:
  - proyecto
  - fridgenfc
---

# Modelo de datos — FridgeNFC

> Nota de contexto: [[Idea principal]]
> Stack final: Supabase (PostgreSQL) en lugar de Firebase — mismo concepto, mejor para queries y sin coste de tiempo real que no necesitamos.

---

## Por qué una sola tabla

La app es deliberadamente simple: una lista de items por nevera. No hay usuarios, no hay sesiones, no hay categorías. Una tabla `items` es suficiente para todo.

Cada fila representa **un producto que falta (o ya se compró)** en una nevera concreta.

---

## Esquema

```sql
create table items (
  id         uuid        primary key default gen_random_uuid(),
  room_id    text        not null,
  name       text        not null,
  done       boolean     not null default false,
  added_by   text,
  created_at timestamptz not null default now()
);
```

### Columna a columna

**`id`** — Identificador único de cada item. Lo genera Supabase automáticamente con `gen_random_uuid()` cada vez que se inserta una fila. No hay que enviarlo desde la app al crear un item.

**`room_id`** — El corazón de la arquitectura. Es un texto de 12 caracteres aleatorios (ej. `a3f9bc12de45`) que identifica una nevera concreta. Viene del hash de la URL: `frigenfc.com/#a3f9bc12de45`. Todos los que escaneen el mismo sticker NFC comparten el mismo `room_id` y por tanto ven la misma lista. Si alguien tiene dos neveras, tiene dos stickers con dos `room_id` distintos.

**`name`** — El nombre del producto que falta. Texto libre, máximo 60 caracteres (limitado desde la UI). Ejemplos: "Leche", "Pan de molde", "Yogures".

**`done`** — Estado del item. `false` significa que todavía falta comprarlo (aparece arriba en la lista). `true` significa que ya está comprado (aparece tachado abajo). Cuando alguien toca el checkbox en la app, este campo cambia.

**`added_by`** — Nombre de la persona que añadió el item. La app pide seleccionar quién eres antes de añadir algo (hasta 6 personas por casa). Esto permite filtrar la lista por persona y saber quién apuntó qué. Es texto libre, no está vinculado a ningún sistema de usuarios.

**`created_at`** — Fecha y hora exacta en que se creó el item. Supabase lo rellena solo. Se usa para ordenar la lista cronológicamente (los más recientes primero dentro de cada estado).

---

## Índice

```sql
create index on items (room_id, created_at);
```

Sin este índice, cada vez que la app carga la lista tendría que recorrer **todos** los items de todas las neveras del mundo para encontrar los de tu `room_id`. Con el índice, la base de datos va directamente a los tuyos. Es especialmente importante a medida que la app tenga más usuarios.

---

## Seguridad: Row Level Security (RLS)

Supabase tiene RLS activado por defecto — sin una policy explícita, nadie puede leer ni escribir nada, aunque tenga la `anon key`.

```sql
alter table items enable row level security;

create policy "acceso libre por room_id"
  on items for all
  using (true)
  with check (true);
```

La policy `using (true)` permite **leer** cualquier fila. La policy `with check (true)` permite **escribir** cualquier fila. Esto puede parecer inseguro, pero hay que entenderlo en contexto:

- No hay datos personales. Solo nombres de productos y quién los añadió.
- La "seguridad" de cada nevera es la oscuridad del `room_id`. Con 12 caracteres aleatorios hay 36^12 ≈ 4.7 billones de combinaciones posibles. Nadie va a adivinar el de tu nevera.
- Si en el futuro se quiere añadir login, se puede refinar la policy para que solo el propietario del `room_id` pueda escribir.

---

## Cómo se usa desde la app

La app no usa el SDK de Supabase — llama directamente a su API REST con `fetch`. Esto mantiene el `index.html` sin dependencias externas.

Todas las llamadas llevan en el header la `anon key` como autenticación. Las credenciales van en las primeras líneas del `<script>` del `index.html`:

```js
const SUPABASE_URL = '...';      // Project Settings → API → Project URL
const SUPABASE_ANON_KEY = '...'; // Project Settings → API → anon public
```

### Cargar la lista de una nevera

```
GET /rest/v1/items?room_id=eq.{room_id}&order=created_at.asc
```

Devuelve todos los items de esa nevera ordenados por fecha. La app separa los `done: false` (pestaña "Falta") de los `done: true` (pestaña "Comprado").

### Añadir un item

```
POST /rest/v1/items
Body: { "room_id": "abc123", "name": "Leche", "done": false, "added_by": "Miren" }
```

Supabase genera el `id` y el `created_at` automáticamente.

### Marcar como comprado (o desmarcar)

```
PATCH /rest/v1/items?id=eq.{id}
Body: { "done": true }
```

Solo se actualiza el campo `done`. El resto del item no cambia.

### Borrar un item

```
DELETE /rest/v1/items?id=eq.{id}
```

Borra permanentemente esa fila.

### Limpiar todos los comprados de una nevera

```
DELETE /rest/v1/items?room_id=eq.{room_id}&done=eq.true
```

Útil para limpiar la lista después de volver de la compra.

---

## Flujo completo de datos (primera vez)

1. Usuario escanea el sticker NFC → se abre `frigenfc.com/#a3f9bc12de45`
2. La app lee `a3f9bc12de45` del hash de la URL y lo guarda en `localStorage`
3. Se hace un `GET` a Supabase filtrando por `room_id = a3f9bc12de45`
4. Se muestra la lista (vacía la primera vez)
5. Usuario selecciona su nombre y añade "Leche" → `POST` a Supabase
6. La fila aparece en la lista al instante (optimistic update)
7. La próxima vez que alguien de la misma casa escanee el sticker, verá "Leche" en la lista
