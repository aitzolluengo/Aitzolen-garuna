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

# Embeddings

## ¿Qué es?

Un **embedding** es la representación de un texto (palabra, frase, párrafo, nota entera) como un **vector de números** — típicamente entre 384 y 3072 dimensiones.

La gracia: textos con significado parecido producen vectores cercanos en el espacio vectorial. Eso permite **búsqueda semántica** — encontrar contenido por significado, no por palabra exacta.

Ejemplo intuitivo: "perro" y "can" están cerca en el espacio. "Perro" y "neumático" están lejos. Un buscador clásico (palabra clave) no relaciona "perro" con "can"; un buscador con embeddings sí.

## Cómo se generan

Se usa un **modelo de embeddings** (distinto del [[LLM]] que conversa). Lo más usado en 2026:

| Modelo | Dimensiones | Coste | Notas |
|---|---|---|---|
| `text-embedding-3-small` (OpenAI) | 1536 | API barata | Buen baseline |
| `text-embedding-3-large` (OpenAI) | 3072 | API | Mejor calidad |
| `voyage-3` (Voyage AI) | 1024 | API | Top calidad 2026 |
| `nomic-embed-text` (Ollama) | 768 | Gratis local | Decente |
| `bge-m3` (BAAI) | 1024 | Gratis local | Multilingüe potente |

Para mi vault personal con notas en castellano + euskera + inglés → `bge-m3` local es la apuesta más razonable.

## Para qué los usa un agente

- **[[RAG]]** → buscar las notas más relevantes para una pregunta
- **Clustering** → agrupar notas similares
- **Detección de duplicados** → ¿esta semilla ya existe en el jardín?
- **Sugerencia de links** → dadas dos notas, ¿deberían enlazarse? (caso del [[01 - Curador del Jardín Digital]])

## Dónde se guardan

En una **base de datos vectorial**: estructura optimizada para encontrar los vectores más cercanos a uno dado en milisegundos, incluso con millones de items. Opciones:

- **Chroma** — la más fácil para empezar, todo en local
- **Qdrant** — más profesional, escala mejor
- **sqlite-vec** — extensión de SQLite, dependencia cero
- **pgvector** — extensión de PostgreSQL si ya uso Postgres

## ¿Qué me falta por entender?

- ¿Realmente cambia tanto el resultado de RAG según el modelo de embedding que use?
- Cómo medir la calidad de un embedding antes de comprometerme con él.
- Qué pasa cuando indexo notas mezcladas en idiomas distintos.

## Para profundizar

- *MTEB Leaderboard* — ranking público de modelos de embeddings: https://huggingface.co/spaces/mteb/leaderboard
- Vídeo de Cohere sobre embeddings (corto y claro): https://www.youtube.com/watch?v=ySus5ZS0b94

## Relacionado

- [[RAG]]
- [[LLM]]
- [[Agentes IA — MOC]]
