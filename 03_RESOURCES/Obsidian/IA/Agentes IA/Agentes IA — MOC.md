---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia
revisado: false
tags:
  - jardin/semilla
---

> [!warning] Pendiente de revisión
> Nota generada el 2026-04-29. Léela, ajusta lo que no encaje y cambia `revisado: true` cuando la hagas tuya.

# Agentes IA — MOC

Mapa central de mis semillas sobre agentes de IA. Esto es un **hub**, no un curso. Las notas son atómicas — entras por una y vas saltando por wikilinks.

## Punto de partida

Un **agente IA** = un LLM con capas extra (memoria, herramientas, recuperación de información, loop de razonamiento). Sin esas capas, un LLM solo conversa; con ellas, **actúa**.

Ver [[LLM]] y [[Prompt engineering]] para la base.

## Las 4 capas que hacen un agente

### 1. Conocimiento más allá del prompt
Cuando el contexto no cabe en la ventana del modelo:
- [[RAG]] — recuperar trozos relevantes antes de generar
- [[Embeddings]] — la representación vectorial que hace posible la búsqueda semántica


### 2. Capacidad de actuar
Cómo el agente deja de "solo hablar":
- [[Tools y function calling]] — funciones que el modelo puede llamar
- [[MCP]] — protocolo estándar para conectar agentes a servicios

### 3. Razonamiento iterativo
Patrón ReAct (Reason + Act): el agente piensa → llama tool → observa → vuelve a pensar. (Crear nota cuando lea el paper.)

### 4. Orquestación
- **Workflow:** flujo fijo y predecible. Recomendado para empezar.
- **Agente autónomo:** decide qué hacer en cada vuelta. Más potente, más impredecible, más caro en tokens.

## Recorrido sugerido (no obligatorio)

Si quiero leer ordenado: [[LLM]] → [[Prompt engineering]] → [[Tools y function calling]] → [[RAG]] → [[Embeddings]] → [[MCP]].

## Para descubrir más

Ver [[Recursos agentes IA]] — recopilatorio de papers, cursos gratuitos, repos y vídeos.

## Aplicación a mi vault

Las propuestas concretas de agentes para mi vault están fuera del jardín, en `000_INBOX/Ideas Agentes IA/`:
- [[01 - Curador del Jardín Digital]]
- [[02 - Generador del Plan Semanal]]
- [[03 - Tutor de Inglés B2]]
- [[04 - Asistente de TFG (Think&DoIT)]]

## Origen de esta semilla

- Brote [[Segundo cerebro]] (pendiente "Cómo integrar IA local cuando sea posible")
- Calma [[Aprender Flowise]] y [[Smart connections con Ollama]]
- Conversación con Claude el 2026-04-29 sobre por dónde empezar a aprender el campo
