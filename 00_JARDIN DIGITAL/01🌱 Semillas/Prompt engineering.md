---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia
revisado: false
tags:
  - jardin/semilla
---

> [!warning] Pendiente de revisión
> Nota generada el 2026-04-29. Cambia `revisado: true` cuando la hagas tuya.

# Prompt engineering

## ¿Qué es?

Diseñar el texto que le mandas a un [[LLM]] para sacar el mejor resultado posible.

Suena trivial. No lo es. La diferencia entre un prompt mal escrito y uno bien escrito puede ser la diferencia entre un agente inútil y uno fiable.

## Anatomía de un prompt

- **System prompt:** instrucciones generales sobre rol, tono, restricciones. ("Eres un tutor de inglés B2. Responde en inglés. Nunca des la respuesta del ejercicio directamente.")
- **User prompt:** la pregunta o tarea concreta de cada turno.
- **Contexto:** información de fondo que el modelo necesita para responder (notas recuperadas por [[RAG]], historial, etc.).

## Técnicas que merecen aprender

| Técnica | En qué consiste | Cuándo usarla |
|---|---|---|
| **Zero-shot** | Pides directamente sin ejemplos | Tareas simples |
| **Few-shot** | Das 2-3 ejemplos input→output | El modelo no acierta el formato sin ver ejemplos |
| **Chain-of-thought** | Le pides que razone paso a paso antes de responder | Problemas matemáticos, lógicos, planificación |
| **Role prompting** | "Actúa como X" | Para fijar tono y estilo |
| **Structured output** | Pides JSON con esquema fijo | Cuando el output va a otra parte del sistema |
| **Self-critique** | El modelo genera, luego se auto-revisa | Calidad sobre velocidad |

## Reglas que aprendí en mi TFG

- Las **reglas absolutas** funcionan: "NUNCA des la respuesta directamente" salió fiable en el TFG.
- **Detección automática de idioma**: una sola línea en el system prompt (`detecta el idioma del usuario y responde en ese idioma`) evita lógica de detección por código.
- **Respuestas cortas**: pedir "máximo 2-3 frases" es más eficaz que `max_tokens`.

## ¿Qué me falta por entender?

- Por qué algunos prompts que funcionan en GPT fallan en Claude y viceversa.
- Cómo iterar un prompt de forma sistemática en lugar de a ojo.
- *Prompt injection*: cuándo es un riesgo real y cómo defenderse.

## Para profundizar

- *Prompting Guide* libre y muy completo: https://www.promptingguide.ai/
- Anthropic Prompt Engineering: https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview
- Curso gratis *ChatGPT Prompt Engineering for Developers* (Andrew Ng + DeepLearning.AI): https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/

## Relacionado

- [[LLM]]
- [[Agentes IA — MOC]]
- [[Tools y function calling]]
