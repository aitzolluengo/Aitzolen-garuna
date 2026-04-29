---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / tfg
tags:
  - jardin/semilla
---

# Asistente de TFG (Think&DoIT)

## La idea original

Documentas cada sesión de trabajo del TFG en `01_PROJECTS/Think and Do it/📅 Sesiones/YYYY-MM-DD — <tema>.md` y cada reunión con el tutor en `📋 Reuniones/YYYY-MM-DD — Bilera Tutorearekin.md`. Cuando llega la siguiente reunión, repasar manualmente todo lo hecho desde la anterior es trabajo. Y la tarea recurrente "Mandar punto 2 documentación TFG" sugiere que tienes que enviar resúmenes periódicamente.

## Objetivo

Preparar automáticamente:
1. Orden del día para la próxima reunión con el tutor.
2. Resumen de progreso para enviar por correo.
3. Sección de la memoria del TFG correspondiente al último sprint.

## Inputs

- `01_PROJECTS/Think and Do it/📅 Sesiones/*.md` — daily notes de programación.
- `01_PROJECTS/Think and Do it/📋 Reuniones/*.md` — actas anteriores (para saber qué tareas dejó el tutor pendientes).
- `01_PROJECTS/Think and Do it/Documentación Obsidian/*.md` — las notas técnicas que ya has empezado (las creadas hoy: CSS compartido, XSS, modales, toasts, badges euskera, panel alumno).
- Git log del repo `c:\Git\ThinkAndDoIt` — commits de la última semana (vía MCP git o `git log` directo).

## Outputs

### 1. Orden del día reunión

Nota nueva `📋 Reuniones/YYYY-MM-DD — Orden del día.md`:
- Tareas pendientes de la reunión anterior y su estado actual
- Avances desde la última reunión (extraídos de sesiones)
- Decisiones que necesitas confirmar
- Preguntas/dudas (extraídas de notas con `#duda` o tareas tipo "Apuntar dudas del tfg")

### 2. Resumen de progreso (correo)

Nota `📋 Reuniones/YYYY-MM-DD — Resumen progreso.md` formato email:
- Asunto sugerido
- 3-5 bullets de avances
- 1-2 bullets de bloqueos / preguntas
- Adjuntos sugeridos (referencia a docs)

### 3. Sección de memoria

Nota `📄 Documentos/Memoria — Sprint YYYY-WW.md`:
- Texto en estilo memoria académica (no daily) sobre lo desarrollado
- Cita commits relevantes
- Referencia a las notas técnicas de `Documentación Obsidian/`

## Stack sugerido

- **LLM:** Claude Haiku 4.5 vía API (calidad de redacción académica importa) o Qwen2.5:14B local.
- **Lenguaje:** Python.
- **Acceso a git:** subprocess `git log --since="last meeting"` o GitPython.
- **Plantilla:** Templater para el orden del día.

## Pasos de implementación

1. Detectar fecha de última reunión leyendo nombres de archivos en `📋 Reuniones/`.
2. Recolectar sesiones desde esa fecha + commits desde esa fecha.
3. Para orden del día → estructura fija con LLM rellenando.
4. Para resumen email → LLM con estilo "profesional, conciso, en castellano (o euskera si la reunión es con tutor de euskera)".
5. Para memoria → LLM con estilo académico + bibliografía mínima.

## Prioridad

🟢 **Alta.** Es tu proyecto principal, tienes la fricción ya identificada (la tarea recurrente de mandar documentación), y reutilizas el output como capítulos de la memoria del TFG.

## Bonus: capítulo "metodología" de la memoria

Como caso de estudio en tu propia memoria del TFG: "He construido un agente que asiste el desarrollo del propio TFG". Recursivo y bonito.

## Relacionado

- [[🗺️ ThinkAndDoIT — MOC]]
- `📅 Sesiones/2026-04-26 — Generacion IA y Prompt`
- `📅 Sesiones/2026-04-28 — Mejoras UI Profesional`
- `📋 Reuniones/2026-04-28 — Bilera Tutorearekin`
- [[00 - Ideas Agentes IA — MOC]]
