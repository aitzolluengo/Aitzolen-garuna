---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / recursos
revisado: false
tags:
  - jardin/semilla
---

> [!warning] Pendiente de revisión
> Nota generada el 2026-04-29. Léelos uno a uno y descarta los que no aporten. Cambia `revisado: true` cuando la nota sea solo lo que tú validaste.

# Recursos agentes IA

Compendio curado de recursos para descubrir el campo. Priorizado: lo que está más arriba es por donde empezaría yo.

## Lectura imprescindible (todo en inglés, B2 ayuda)

- **Anthropic — *Building effective agents*** (post de referencia 2024-2025, siguen actualizándolo). Cuándo usar workflow, cuándo agentes autónomos, patrones canónicos. Si solo lees una cosa, esta.
  https://www.anthropic.com/research/building-effective-agents

- **Anthropic — *Contextual Retrieval*** (técnica que mejora [[RAG]] de forma muy clara).
  https://www.anthropic.com/news/contextual-retrieval

- **Spec de [[MCP]]**.
  https://modelcontextprotocol.io/

## Cursos gratuitos (DeepLearning.AI + Andrew Ng)

Todos en inglés, ~2 horas cada uno, vídeos cortos + notebooks Jupyter ejecutables. Calidad muy alta.

- **ChatGPT Prompt Engineering for Developers** — base de [[Prompt engineering]].
  https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/

- **Building and Evaluating Advanced RAG** — con LlamaIndex.
  https://www.deeplearning.ai/short-courses/building-evaluating-advanced-rag/

- **Functions, Tools and Agents with LangChain** — patrones de [[Tools y function calling]].
  https://www.deeplearning.ai/short-courses/functions-tools-agents-langchain/

- **AI Agents in LangGraph** — introducción a agentes autónomos con grafos.
  https://www.deeplearning.ai/short-courses/ai-agents-in-langgraph/

## Vídeos sueltos

- **Andrej Karpathy — *Software 3.0*** (visión de campo, alto nivel, motivacional).
  https://www.youtube.com/watch?v=LCEmiRjPEtQ

- **Andrej Karpathy — *Deep dive into LLMs***. 3 horas, profundidad técnica.
  https://www.youtube.com/watch?v=7xTGNNLPyMI

## Repositorios para leer código

- **`langchain-ai/rag-from-scratch`** — RAG paso a paso, 12 partes.
  https://github.com/langchain-ai/rag-from-scratch

- **`modelcontextprotocol/servers`** — implementaciones de referencia de servidores [[MCP]].
  https://github.com/modelcontextprotocol/servers

- **`humanlayer/12-factor-agents`** — principios de ingeniería para agentes en producción (manifesto 2025).
  https://github.com/humanlayer/12-factor-agents

## Frameworks para conocer (no para empezar)

| Framework | Para qué |
|---|---|
| **LangChain** | El primero, popular, abstracciones por todas partes. Útil leerlo, peligroso depender |
| **LlamaIndex** | Especializado en RAG, mejor que LangChain para eso |
| **LangGraph** | Grafos de agentes, multi-agente |
| **Pydantic AI** | Moderno (2024), basado en type hints, simple |
| **Flowise** | Sin código, drag & drop. Ya tengo semilla [[Aprender Flowise]] |
| **n8n** | Workflows generales con nodos de IA |

## Comunidades para descubrir

- **r/LocalLLaMA** — todo lo que pasa con modelos abiertos: https://www.reddit.com/r/LocalLLaMA/
- **HuggingFace daily papers** — papers nuevos curados: https://huggingface.co/papers
- **Latent Space** — newsletter / podcast de calidad: https://www.latent.space/

## Específico Obsidian + IA

- **Smart Connections plugin** (versión gratis básica, pago para Ollama): https://smartconnections.app/
- **Copilot for Obsidian** (más simple, también soporta Ollama): https://github.com/logancyang/obsidian-copilot
- **Khoj** (RAG sobre Obsidian, open-source, local-first): https://khoj.dev/

## Para mi caso (Ollama local)

- **Ollama** instalación y catálogo: https://ollama.com/
- **Modelos pequeños recomendados para empezar:**
  - `qwen2.5:7b` — generalista, calidad alta para su tamaño
  - `llama3.1:8b` — muy estable
  - `nomic-embed-text` — embeddings ([[Embeddings]])
  - `gpt-oss:20b` — calidad cercana a APIs, requiere GPU decente

## Relacionado

- [[Agentes IA — MOC]]
- [[Aprender Flowise]]
- [[Smart connections con Ollama]]
- [[Conectar Claude Code con Open Router]]
- [[Openrouter Free Models]]

Sources:
- [Anthropic — Building effective agents](https://www.anthropic.com/research/building-effective-agents)
- [Obsidian Forum — atomic notes debate](https://forum.obsidian.md/t/debating-the-usefulness-of-atomic-notes-a-novel-pragmatic-obsidian-based-approach-to-pkm-strategies/38077)
- [Maps of Content guide](https://www.dsebastien.net/2022-05-15-maps-of-content/)
- [Fusing PARA + Zettelkasten in Obsidian](https://parazettel.com/articles/fusing-basb-zettelkasten-obsidian/)
