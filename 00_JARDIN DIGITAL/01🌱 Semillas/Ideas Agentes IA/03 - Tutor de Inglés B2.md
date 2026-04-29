---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / aprendizaje
tags:
  - jardin/semilla
---

# Tutor de Inglés B2

## La idea original

Tienes 8+ notas de gramática B2 estructuradas en `02_AREAS/Aprendizaje/` (Conditionals, Inversions, Modal Verbs, Reported Speech, Passive Voice, Linking Words, Non-defining Relatives, Wishes and Regrets). Falta una capa de práctica activa — lo que de verdad mueve el nivel. Un tutor IA que cada semana te genere un ejercicio nuevo basado en lo que ya tienes documentado.

## Objetivo

Mantener práctica de inglés constante sin pagar a un profesor ni buscar material — el contenido sale de tus propias notas.

## Inputs

- Todas las notas de `02_AREAS/Aprendizaje/*.md` (gramática B2).
- Frontmatter de cada una para saber `last_review`. Si no existe, crearlo.
- Notas anteriores de práctica (las que va creando el agente) para no repetir temas y subir dificultad.

## Outputs

- Cada lunes, una nota nueva `02_AREAS/Aprendizaje/Práctica Semanal YYYY-WW.md` con:
  - **Writing prompt** (alternando essay / formal letter / report — los 3 que aparecen en tu plan)
  - **Rúbrica de corrección** (banda B2 de Cambridge)
  - **Mini-test gramatical** de la estructura menos revisada (10 huecos + 5 transformaciones)
  - **Listening recomendado** (referencia a un vídeo/podcast de nivel — del MCP de YouTube si está, o sugerencia textual)
  - Solucionario al final colapsado (`> [!note]- Soluciones`)

## Modo "corrector"

Segundo modo opcional: si rellenas el writing y ejecutas `python tutor.py --review <archivo>`, te corrige con criterios B2:
- Errores gramaticales con explicación
- Sugerencias de vocabulario más natural
- Banda estimada (1-5)

## Stack sugerido

- **LLM:** Modelo grande para calidad lingüística — Claude Haiku 4.5 vía API o GPT-OSS-20B local. La gramática B2 requiere precisión, no es tarea para un 3B.
- **Lenguaje:** Python script disparado por cron o QuickAdd.
- **Conocimiento de tus notas:** envía contenido completo de las gramáticas como contexto (~5K tokens, cabe sin RAG).

## Pasos de implementación

1. Añadir `last_review: YYYY-MM-DD` al frontmatter de cada nota de gramática (manual una vez, luego el agente lo mantiene).
2. Script `b2_tutor.py` que:
   - Selecciona la gramática con `last_review` más antigua
   - Carga su contenido + ejemplos
   - Pide al LLM ejercicio + rúbrica
   - Escribe la nota
   - Actualiza `last_review` de la gramática elegida
3. Modo `--review`: lee tu writing y produce nota de feedback paralela.

## Prioridad

🟢 **Alta.** Área activa con material ya estructurado. Alto impacto en un objetivo personal claro (B2). Implementación directa.

## Riesgos

- LLM puede generar ejercicios con errores sutiles. Mitigación: pedir al modelo que genere, después auto-revise antes de devolver.
- El "listening recomendado" sin acceso a internet → mejor referenciar tipo (TED-Ed, BBC 6 Minute English) que URLs concretas que pueden 404.

## Relacionado

- [[Ingles B2 - MOC]]
- [[Conditionals (B2)]]
- [[Inversions (B2)]]
- [[Modal Verbs for Speculation (B2)]]
- [[00 - Ideas Agentes IA — MOC]]
