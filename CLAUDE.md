# Mi Vault — Contexto para Claude Code

Este vault es un sistema personal de gestión del conocimiento en Obsidian. Cuando crees o edites notas, respeta siempre la estructura, el frontmatter y las convenciones del sistema.

---

## Mapa de carpetas

| Carpeta | Propósito |
|---|---|
| `000_INBOX/` | Captura rápida y procesamiento pendiente |
| `000_INBOX/Inbox.md` | **Punto único de captura** — checkboxes `- [ ] tarea 📅 fecha` |
| `000_INBOX/Dashboards/` | Dashboards (Tareas, Cine, Plan Semanal) |
| `000_INBOX/Plantillas/` | Plantillas Templater organizadas por tema |
| `000_INBOX/Adjuntos/` | Imágenes y archivos adjuntos |
| `00_JARDIN DIGITAL/` | Ideas organizadas por nivel de madurez |
| `00_JARDIN DIGITAL/01🌱 Semillas/<Tema>/` | Semillas agrupadas por tema cuando hay 3+ del mismo |
| `01_PROJECTS/` | Proyectos activos (con o sin deadline) |
| `02_AREAS/` | Responsabilidades continuas (deporte, música, bajo, aprendizaje) |
| `03_RESOURCES/` | Conocimiento de referencia |
| `03_RESOURCES/Cine/{Películas,Directores,Actores}/` | Sistema de cine |
| `03_RESOURCES/IA/` | Notas técnicas sobre LLMs, agentes, herramientas |
| `04_ARCHIVE/` | Material inactivo y tareas completadas |
| `Cómo usar este vault.md` | Documentación principal del sistema (raíz del vault) |

---

## Sistema de tareas (sin TaskNotes)

- Las **tareas son checkboxes** con el formato del plugin Tasks: `- [ ] cosa 📅 2026-05-02 ⏫ #tag`.
- **Crear nuevas tareas:** dentro de `Inbox.md` o, si tienen contexto largo, dentro de la nota del proyecto/área que les corresponde.
- **Vista global:** [[Dashboards/Tareas]] muestra todas las tareas del vault con queries del plugin Tasks (Hoy, Esta semana, Atrasadas, Sin fecha, Prioridad alta, Completadas).
- **No usar TaskNotes** — las tareas no son notas individuales, son items dentro de notas.
- **Procesamiento semanal:** lo capturado en Inbox se mueve a su proyecto/área correspondiente o se archiva.

---

## Jardín Digital — niveles de madurez

| Carpeta | Emoji | Tag | Uso |
|---|---|---|---|
| `00_JARDIN DIGITAL/01🌱 Semillas/` | 🌱 | `jardin/semilla` | Idea nueva, sin desarrollar |
| `00_JARDIN DIGITAL/02🌿 Brotes/` | 🌿 | `jardin/brote` | Idea en desarrollo |
| `00_JARDIN DIGITAL/03🌳 Arboles/` | 🌳 | `jardin/arbol` | Conocimiento maduro y consolidado |
| `00_JARDIN DIGITAL/04❄️ Calma/` | ❄️ | `jardin/calma` | Idea aparcada temporalmente |

Frontmatter de jardín: `fecha`, `madurez` (emoji), `contexto`, `tags`.

---

## Frontmatter por tipo de nota

**Semilla / Brote / Árbol:**
```yaml
fecha: YYYY-MM-DD
madurez: 🌱 | 🌿 | 🌳 | ❄️
contexto: (tema o área de vida)
tags:
  - jardin/semilla
```

**Proyecto:**
```yaml
fecha_inicio: YYYY-MM-DD
estado: activo | pausado | terminado
tags:
  - tipo/proyecto
```

**Película:**
```yaml
fecha_vista: YYYY-MM-DD
titulo: 
director: 
año: 
genero: 
reparto:
  - "[[Actor]]"
puntuacion: (1-5)
tags:
  - tipo/pelicula
  - cine/vista | cine/por-ver
```

**Daily note:**
```yaml
fecha: YYYY-MM-DD
dia: (nombre del día)
tags:
  - tipo/daily
```

**Tarea:**
```yaml
(sin frontmatter obligatorio — usar formato Tasks plugin: - [ ] tarea 📅 YYYY-MM-DD)
```

---

## Sistema de Cine

- Películas: `03_RESOURCES/Cine/Películas/TÍTULO.md`
- Directores: `03_RESOURCES/Cine/Directores/NOMBRE.md`
- Actores: `03_RESOURCES/Cine/Actores/NOMBRE.md`
- Dashboard: `000_INBOX/01 Dashboard/Dashboard Cine.md`
- Las notas de película enlazan al director y actores con `[[Nombre]]`.

---

## Taxonomía de tags

- `tipo/proyecto`, `tipo/pelicula`, `tipo/daily`, `tipo/referencia`
- `jardin/semilla`, `jardin/brote`, `jardin/arbol`, `jardin/calma`
- `cine/vista`, `cine/por-ver`
- `area/aprendizaje`, `area/musica`, `area/deporte`

---

## Plugins activos y cómo afectan las notas

- **Templater** — las plantillas usan `<% tp.* %>`. Al crear notas manualmente sin Templater, rellena esos valores con datos reales.
- **Dataview** — los dashboards hacen queries sobre frontmatter. Respetar nombres de campos exactos.
- **Tasks** — tareas con formato `- [ ] texto 📅 YYYY-MM-DD` o `⏫` para prioridad.
- **Obsidian Git** — commits automáticos del vault, no tocar configuración de git salvo que se pida.
- **Periodic Notes / Calendar** — daily y weekly notes en `000_INBOX/` o carpeta configurada.

---

## Reglas al crear o editar notas

1. Crear el archivo en la carpeta correcta según el tipo.
2. Incluir frontmatter completo con los campos del tipo correspondiente.
3. Usar `[[Nombre]]` para enlaces internos, nunca rutas relativas.
4. No inventar tags nuevos; usar los de la taxonomía definida arriba.
5. El título del archivo es el título de la nota (sin fecha en el nombre salvo dailies).
6. Las tareas van en `000_INBOX/00 TASKS/Tareas/` como notas individuales o como ítems `- [ ]` dentro de otra nota.
