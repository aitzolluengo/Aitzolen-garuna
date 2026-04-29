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

# LLM

## ¿Qué es?

**Large Language Model.** Pieza central de cualquier agente. Recibe texto, devuelve texto. Eso es todo lo que hace.

Modelos famosos en 2026: Claude (Anthropic), GPT (OpenAI), Llama (Meta), Qwen (Alibaba), Gemini (Google), Mistral, gpt-oss (la familia open de OpenAI).

## Conceptos que importan

- **Ventana de contexto:** cuánto texto puede leer + escribir en una llamada. Claude 4.7 = 1M tokens. Modelos pequeños locales = 8K-128K.
- **Tokens ≠ palabras.** 1 token ≈ 0.75 palabras en castellano. Las APIs cobran por token.
- **Parámetros de generación:**
  - `temperature` — 0 determinista, 1 creativo
  - `max_tokens` — límite de la respuesta
  - `top_p` — alternativa a temperature

## Tipos de modelo

- **Base:** completa texto crudo. No conversa. Casi nunca lo uso directamente.
- **Instruct / Chat:** afinado para seguir instrucciones y dialogar. El que normalmente uso.
- **Embeddings:** especializado en convertir texto a vector ([[Embeddings]]).

## Open vs cerrado

- **Cerrados (API):** Claude, GPT-4, Gemini. Mejor calidad. Pago por token. Datos salen de mi máquina.
- **Abiertos (locales con Ollama):** Llama, Qwen, Mistral, gpt-oss. Calidad menor pero suficiente para muchas tareas. Privacidad total.

Para mi vault: si toco notas personales, prefiero local. Si necesito calidad lingüística (corrección de inglés B2), pago una API.

## ¿Qué me falta por entender?

- Cómo elegir el modelo adecuado (tamaño, coste, latencia).
- Qué es exactamente *prompt caching* (lo usa Claude para reducir coste cuando repites contexto largo).
- Cuándo merece la pena hacer fine-tuning frente a buen prompting + RAG.

## Relacionado

- [[Agentes IA — MOC]]
- [[Prompt engineering]]
- [[Embeddings]]
- [[Recursos agentes IA]]
