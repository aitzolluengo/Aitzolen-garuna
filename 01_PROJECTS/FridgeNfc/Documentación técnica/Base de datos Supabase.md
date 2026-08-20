---
fecha: 2026-08-17
tags:
  - proyecto
  - fridgenfc
---

# Base de datos — Supabase

Proyecto: [[Idea principal]]
Stack: Supabase (PostgreSQL + REST API) + GitHub Pages

---

## Credenciales

Las credenciales van en `index.html` (líneas de config al inicio del `<script>`):

```js
const SUPABASE_URL = '...';       // Project Settings → API → Project URL
const SUPABASE_ANON_KEY = '...';  // Project Settings → API → anon public
```

> Pedir acceso al proyecto Supabase a Aitzol.

---

## Tabla `items`

```sql
create table items (
  id         uuid        primary key default gen_random_uuid(),
  room_id    text        not null,
  name       text        not null,
  done       boolean     not null default false,
  added_by   text,
  created_at timestamptz not null default now()
);

create index on items (room_id, created_at);
```

| Columna | Tipo | Descripción |
|---|---|---|
| `id` | uuid | PK autogenerada |
| `room_id` | text | ID único de cada nevera (viene del hash de la URL) |
| `name` | text | Nombre del ítem que falta |
| `done` | boolean | `false` = pendiente, `true` = comprado |
| `added_by` | text | Nombre de la persona que lo añadió |
| `created_at` | timestamptz | Fecha de creación |

---

## Row Level Security (RLS)

RLS activado. La policy permite acceso libre a quien conozca el `room_id`:

```sql
alter table items enable row level security;

create policy "acceso libre por room_id"
  on items for all
  using (true)
  with check (true);
```

**Por qué:** la app no tiene login. La seguridad es la oscuridad del `room_id` (12 caracteres aleatorios). Suficiente para uso doméstico.

---

## Arquitectura multi-familia

Cada familia tiene una URL única: `frigenfc.com/#abc123`

- El `room_id` se genera en el primer acceso y se guarda en `localStorage`
- La URL con el hash es la que va en el sticker NFC
- Todas las queries filtran por `room_id` — los datos de cada familia están aislados

---

## Queries principales

La app usa la REST API de Supabase directamente (sin SDK), con `fetch`:

```js
// Leer items de una nevera
GET /rest/v1/items?room_id=eq.{room_id}&order=created_at.asc

// Añadir item
POST /rest/v1/items
Body: { room_id, name, done: false, added_by }

// Marcar comprado
PATCH /rest/v1/items?id=eq.{id}
Body: { done: true }

// Borrar item
DELETE /rest/v1/items?id=eq.{id}

// Limpiar comprados
DELETE /rest/v1/items?room_id=eq.{room_id}&done=eq.true
```
