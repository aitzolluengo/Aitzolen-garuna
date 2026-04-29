---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / deporte
tags:
  - jardin/semilla
---

# Coach de Kirola

## La idea original

Tienes en `02_AREAS/Kirola/`: `Periodización carga.md`, `Entrenamiento 1.md`, `Entrenamiento 2.md`, y `00_TAREAS.md`. La semilla [[Documentar nombres técnicos de mi rutina]] está parada. La tarea "Documentar entrenamientos de forma correcta" lleva tiempo en INBOX. Un agente coach que conozca tu plan teórico y te genere el microciclo semanal real con espacios para registrar RPE/sensaciones.

## Objetivo

Convertir el plan teórico (periodización) en sesiones concretas semanales y mantener el registro de carga real para ajustar la siguiente semana.

## Inputs

- `02_AREAS/Kirola/Periodización carga.md` — modelo teórico de cómo distribuyes carga.
- `Entrenamiento 1.md`, `Entrenamiento 2.md` — sesiones tipo.
- Notas de sesiones pasadas (cuando empieces a generarlas) con `RPE`, `volumen`, `notas` en frontmatter.
- (Opcional) Strava/Garmin/HealthFit vía MCP o export CSV.

## Outputs

Cada lunes, nota `02_AREAS/Kirola/Microciclo YYYY-WW.md`:

```markdown
---
fecha_inicio: 2026-04-29
fecha_fin: 2026-05-05
tipo: microciclo
fase: hipertrofia | fuerza | descarga
volumen_planificado: 8h
---

## Lunes — Entrenamiento 1 (Tirón)
- Sentadilla: 4×6 @ RPE 7
- Remo: 4×8 @ RPE 7
...
| Ejercicio | Series | Reps | RPE objetivo | RPE real | Notas |
|---|---|---|---|---|---|
| Sentadilla | 4 | 6 | 7 | _ | _ |

## Martes — Recuperación activa
...
```

Después tú rellenas RPE real / notas, y la próxima semana el agente lee eso para ajustar carga.

## Modo "registro rápido"

Comando `python coach.py --log "sentadilla 4x6 @ 100kg RPE 8"` que parsea y añade a la sesión del día.

## Stack sugerido

- **LLM:** Modelo pequeño local (la planificación de carga es regla + LLM para redactar instrucciones).
- **Lenguaje:** Python.
- **Conocimiento deportivo:** prompt enriquecido con principios de [[Periodización carga]] como contexto.

## Pasos de implementación

1. Estandarizar formato de sesión (frontmatter con campos clave).
2. Script `coach.py weekly` que:
   - Lee periodización + última semana real
   - Aplica regla de progresión (5-10% volumen si RPE medio < 7, descarga si RPE > 8.5)
   - Pide al LLM rellenar el detalle de cada sesión con tono motivador
3. Cron domingo noche.

## Prioridad

🔵 **Baja.** Útil pero requiere que primero estandarices el formato de tus sesiones. Segundo paso natural una vez la semilla [[Documentar nombres técnicos de mi rutina]] avance.

## Riesgos

- IA dando consejos deportivos puede ser temeraria. Mitigación: el agente solo aplica reglas que tú definiste en `Periodización carga`, no inventa principios.
- No sustituye a un entrenador real, sobre todo si hay objetivos competitivos.

## Relacionado

- [[Periodización carga]]
- [[Entrenamiento 1]]
- [[Entrenamiento 2]]
- [[Documentar nombres técnicos de mi rutina]]
- [[00 - Ideas Agentes IA — MOC]]
