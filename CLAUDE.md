# Mi Vault — Contexto para Claude Code

Este vault es un cuaderno digital personal en Obsidian. Sirve para escribir, desarrollar ideas y documentar conocimiento. Las tareas y la vida diaria van en el Bullet Journal físico.

---

## Mapa de carpetas

| Carpeta | Propósito |
|---|---|
| `Escritura/Películas/` | Reflexiones sobre películas vistas |
| `Escritura/Reflexiones/` | Pensamientos, escritura libre |
| `Bajo/Teoría/` | Teoría musical, técnica de bajo |
| `Bajo/Canciones/` | Líneas de bajo aprendidas, letras propias |
| `Proyectos/` | Proyectos personales activos (Shopping List Recorder, Rowing Fantasy…) |
| `Gimnasio/` | Rutinas y seguimiento de entrenamiento |
| `00_JARDIN DIGITAL/` | Ideas organizadas por nivel de madurez — no tocar estructura |
| `000_INBOX/` | Captura rápida y adjuntos |
| `03_RESOURCES/Compras/` | Lista de artículos y fichas de compra |
| `04_ARCHIVE/` | TFG, Inglés, sistema de cine antiguo, docs Obsidian |

---

## Cómo es este vault

- **No es un sistema de productividad.** Las tareas van en el BuJo físico.
- **Es un espacio para escribir y pensar.** Notas simples, sin frontmatter complejo salvo cuando tenga sentido.
- **Las conexiones importan más que la estructura.** Usar `[[wikilinks]]` libremente.
- **Jardín digital:** se mantiene tal cual, con su sistema de semillas/brotes/árboles/calma.

---

## Frontmatter por tipo de nota

**Película (reflexión):**
```yaml
fecha: YYYY-MM-DD
titulo:
director:
año:
puntuacion: (1-5)
tags:
  - pelicula
```

**Nota de bajo / teoría:**
```yaml
fecha: YYYY-MM-DD
tags:
  - bajo
```

**Proyecto:**
```yaml
fecha_inicio: YYYY-MM-DD
estado: activo | pausado | terminado
tags:
  - proyecto
```

**Jardín digital (sin cambios):**
```yaml
fecha: YYYY-MM-DD
madurez: 🌱 | 🌿 | 🌳 | ❄️
contexto:
tags:
  - jardin/semilla | jardin/brote | jardin/arbol | jardin/calma
```

---

## Reglas al crear notas

1. Crear el archivo en la carpeta correcta según el tipo.
2. Frontmatter mínimo — solo los campos que aporten valor.
3. Usar `[[Nombre]]` para enlaces internos.
4. Las tareas NO van en Obsidian — van en el BuJo físico.
5. El título del archivo es el título de la nota.

---

## Plugins activos

- **Obsidian Git** — commits automáticos, no tocar configuración.
- **Templater** — plantillas con `<% tp.* %>`.
- **Jardín digital** — usa tags `jardin/*` para el sistema de madurez.
