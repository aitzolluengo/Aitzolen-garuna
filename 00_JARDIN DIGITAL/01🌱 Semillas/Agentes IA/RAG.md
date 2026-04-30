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

# RAG

**Retrieval Augmented Generation** — generación aumentada por recuperación.

## ¿Qué problema resuelve?

Mi vault tiene 134 notas. Mi [[LLM]] no las conoce, y no caben todas en el prompt. RAG es la técnica que permite responder usando información que **no estaba en los datos de entrenamiento del modelo** — por ejemplo, mis notas personales — sin necesidad de re-entrenar nada.

## Cómo funciona, paso a paso

1. **Chunking:** parto cada nota en trozos de 100-500 palabras.
2. **Embedding:** paso cada trozo por un modelo de [[Embeddings]] → me devuelve un vector que representa el *significado*.
3. **Storage:** guardo todos los vectores en una base de datos vectorial (Chroma, Qdrant, sqlite-vec…).
4. **Query time:**
   - El usuario pregunta algo.
   - Convierto la pregunta a vector con el mismo modelo de embeddings.
   - Busco en la BD los **K vectores más cercanos** (similitud coseno).
5. **Generación:** construyo el prompt como `<trozos recuperados> + <pregunta>` y se lo paso al [[LLM]]. El modelo responde citando solo los trozos.

## Por qué importa para mí

Es la respuesta directa a [[Smart connections con Ollama]], que aparqué porque pedía Pro. Smart Connections de pago = un RAG envuelto en plugin. Lo puedo construir yo con Ollama gratis y más control.

## Variantes para el futuro

- **Hybrid search:** búsqueda vectorial + búsqueda por palabra clave (BM25). Mejora cuando la consulta tiene términos exactos (nombres propios, código).
- **Reranking:** después del top-20 vectorial, otro modelo más caro reordena para devolver el top-5 final.
- **Contextual Retrieval:** técnica de Anthropic que añade contexto a cada chunk antes de embeber. Mejora la recuperación drásticamente.
- **GraphRAG:** un grafo de entidades y relaciones en vez de vectores planos. Microsoft tiene paper.
- **Agentic RAG:** el agente decide qué buscar, lanza varias queries, refina iterativamente.

## ¿Qué me falta por entender?

- Cómo evaluar si mi RAG funciona bien (RAGAS, TruLens).
- Tamaño óptimo de chunk para notas Markdown con frontmatter.
- Si vale la pena indexar también el frontmatter como metadatos filtrables.

## Para profundizar

- Anthropic — *Contextual Retrieval* (mejora muy clara sobre RAG estándar): https://www.anthropic.com/news/contextual-retrieval
- *RAG from scratch* — serie 12 partes de LangChain, código incluido: https://github.com/langchain-ai/rag-from-scratch
- Curso *Building and Evaluating Advanced RAG* (DeepLearning.AI + LlamaIndex): https://www.deeplearning.ai/short-courses/building-evaluating-advanced-rag/

## Relacionado

- [[Embeddings]]
- [[LLM]]
- [[Smart connections con Ollama]]
- [[01 - Curador del Jardín Digital]]
- [[Agentes IA — MOC]]
- [[Recursos agentes IA]]
