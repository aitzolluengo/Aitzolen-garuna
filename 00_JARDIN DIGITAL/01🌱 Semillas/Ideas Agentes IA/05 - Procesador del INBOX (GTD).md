---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / productividad
tags:
  - jardin/semilla
---

# Procesador del INBOX (GTD)

## La idea original

`000_INBOX/00 TASKS/Tareas/` acumula notas heterogéneas: tareas concretas (`Listening 29 abril.md`), investigaciones (`Conectar Claude Code con Open Router.md`, `OpenRouter mejor modelo.md`), referencias técnicas (`Openrouter Free Models.md`), y tareas de proyectos (`Acabar de escribir El Golpe.md`, `Mandar punto 2 documentacion TFG.md`). Todas mezcladas. Procesar PARA semanalmente es trabajo manual repetitivo.

## Objetivo

Para cada nota del INBOX, decidir:
- ¿Es **tarea ejecutable**? → mantener formato Tasks, etiquetar con proyecto/área.
- ¿Es **referencia/investigación**? → mover a `03_RESOURCES/<tema>/`.
- ¿Es **idea**? → mover a `00_JARDIN DIGITAL/01🌱 Semillas/` con frontmatter de jardín.
- ¿Pertenece a **un proyecto activo**? → mover a `01_PROJECTS/<proyecto>/`.

## Inputs

- Todas las notas de `000_INBOX/00 TASKS/Tareas/*.md`.
- Lista de proyectos activos: `01_PROJECTS/*/`.
- Lista de áreas: `02_AREAS/*/`.
- Taxonomía de tags definida en `CLAUDE.md` del vault.

## Outputs

Nota `000_INBOX/Procesar INBOX YYYY-MM-DD.md` con tabla:

| Nota | Tipo detectado | Destino propuesto | Frontmatter sugerido | Tags |
|---|---|---|---|---|
| `Openrouter Free Models.md` | Referencia | `03_RESOURCES/IA/` | tipo/referencia | `tema/llm` |
| `Mandar punto 2 documentación TFG.md` | Tarea de proyecto | `01_PROJECTS/Think and Do it/` | priority: high | `tfg` |
| `Conectar Claude Code con Open Router.md` | Investigación | `00_JARDIN DIGITAL/01🌱 Semillas/` | madurez: 🌱 | `jardin/semilla` |

Marcas de checkbox al lado para que confirmes con un click — tras confirmación, el agente mueve archivos y actualiza frontmatter.

## Stack sugerido

- **LLM:** Modelo pequeño (Qwen2.5:7B local). Es tarea de clasificación.
- **Lenguaje:** Python con `python-frontmatter` y `shutil` para mover.
- **Convenciones:** carga `CLAUDE.md` del vault como contexto del prompt — así respeta tu taxonomía exacta de tags.

## Pasos de implementación

1. Script `inbox_processor.py` que:
   - Lee `CLAUDE.md` del vault (taxonomía, frontmatter de cada tipo)
   - Para cada `*.md` en INBOX/Tareas: pide al LLM clasificación + destino + frontmatter sugerido
   - Devuelve tabla Markdown
2. Comando `--apply <fecha>` que lee la nota de propuesta y mueve archivos según los checkboxes marcados.
3. Cron domingos por la tarde — antes de la planificación semanal.

## Prioridad

🟡 **Media.** Útil pero no urgente — el INBOX no está desbordado (10 notas). Más valor si crece. Bueno como segundo agente cuando ya tengas el #1 (curador).

## Riesgos

- Mover archivos rompe wikilinks. Mitigación: el agente actualiza wikilinks `[[Tarea]]` → `[[Carpeta/Tarea]]` en notas que enlazaban a la movida.
- El plugin Obsidian Git puede liarse con cambios masivos. Hacer commit antes de aplicar.

## Relacionado

- [[Cómo usar este vault]]
- [[Dashboard Tareas]]
- [[00 - Ideas Agentes IA — MOC]]
