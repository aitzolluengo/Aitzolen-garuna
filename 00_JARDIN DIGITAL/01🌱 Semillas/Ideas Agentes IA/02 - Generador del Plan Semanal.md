---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / planificacion
tags:
  - jardin/semilla
---

# Generador del Plan Semanal

## La idea original

Ya generas planes semanales (ej. `Plan Semanal 2026-04-29 - 2026-05-05.md`) pero el archivo actual está roto en encoding (todos los emojis aparecen como `ðŸš€` y los acentos como `Ã­`) y se nota que es output de un LLM externo pegado a mano. Un agente local lo regenera cada lunes leyendo el estado real del vault.

## Objetivo

Tener un plan semanal fresco cada lunes, equilibrado entre prioridades, sin trabajo manual y con encoding UTF-8 correcto.

## Inputs

- **Tareas pendientes:** notas de `000_INBOX/00 TASKS/Tareas/*.md` con `status != done` y `scheduled` en la semana objetivo.
- **Tasks plugin items:** todos los `- [ ] tarea 📅 YYYY-MM-DD` del vault donde la fecha cae dentro de la semana.
- **Sesiones recientes del TFG:** últimas 3 notas de `01_PROJECTS/Think and Do it/📅 Sesiones/` para saber por dónde vas.
- **Estado del jardín:** notas modificadas en los últimos 7 días en `00_JARDIN DIGITAL/`.
- **Áreas activas:** lectura ligera de `02_AREAS/Aprendizaje/` (gramática menos revisada → priorizar) y `02_AREAS/Kirola/`.

## Outputs

- Crea `000_INBOX/01 Dashboard/Plan Semanal YYYY-MM-DD - YYYY-MM-DD.md` con:
  - Frontmatter `fecha_inicio`, `fecha_fin`, `tags: [plan/semanal]`
  - Sección por bloque temático (TFG, B2, Jardín, Kirola, Música, Tareas)
  - Cada item enlaza a la nota fuente con `[[wikilink]]` real (no inventado)
  - Recordatorio personalizado al final basado en tu carga de la semana anterior

## Stack sugerido

- **LLM:** Ollama local (suficiente con un modelo pequeño 3-7B — el formato es repetitivo).
- **Lenguaje:** Python con `python-frontmatter` para parsear y `pathlib` para recorrer.
- **Plantilla:** Templater plugin (ya lo tienes) — el agente solo rellena placeholders, no genera Markdown libre. Reduce alucinaciones.

## Pasos de implementación

1. Crear plantilla Templater `02 Templates/Plan Semanal.md` con placeholders `<% tp.user.tfg_status() %>`, etc.
2. Script `weekly_plan.py` que:
   - Calcula rango lunes-domingo
   - Recolecta tareas, sesiones, jardín
   - Pide al LLM solo el "tono motivador" de cada bloque, no la estructura
   - Escribe el archivo con encoding UTF-8 explícito
3. Cron lunes 07:00 o ejecución manual.
4. Validador de wikilinks: ningún `[[X]]` que no exista realmente — si el LLM inventa un link, se elimina.

## Prioridad

🟢 **Alta.** Trabajo manual recurrente + el plan actual está degradado por el encoding. Implementación de pocas horas.

## Variante futura

- Plan diario corto (top-3 del día) como subproducto, leyendo daily note de ayer.
- Integración con [[Google Calendar + Obsidian]] para incluir eventos reales.

## Relacionado

- `Plan Semanal 2026-04-29 - 2026-05-05.md` (referencia rota)
- [[Google Calendar + Obsidian]]
- [[Dashboard Tareas]]
- [[00 - Ideas Agentes IA — MOC]]
