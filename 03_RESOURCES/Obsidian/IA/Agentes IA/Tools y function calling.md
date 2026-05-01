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

# Tools y function calling

## ¿Qué es?

Le doy al [[LLM]] una **lista de funciones** que puede llamar, con su nombre, descripción y parámetros. El modelo, durante una conversación, decide cuándo llamar a cuál y con qué argumentos.

Ejemplos típicos:
- `leer_archivo(path)`
- `buscar_web(query)`
- `enviar_email(destinatario, asunto, cuerpo)`
- `ejecutar_python(codigo)`
- `crear_nota(titulo, contenido)`

Con esto el agente pasa de "dame texto" a "haz cosas en el mundo real".

## Cómo funciona técnicamente

1. Le doy al modelo el esquema JSON de mis funciones en el prompt.
2. El modelo responde con un objeto `{"tool": "nombre", "args": {...}}` cuando decide usar una.
3. Mi código ejecuta la función real y le devuelve el resultado.
4. El modelo continúa la conversación con ese resultado en contexto.

Suena simple. Lo es. La magia de los agentes modernos es básicamente esto en bucle.

## Anthropic, OpenAI, Ollama — formato

Cada proveedor define su esquema de tools de forma ligeramente distinta, pero el principio es el mismo. En 2026, casi todos soportan el formato JSON Schema directamente.

## Buenas prácticas

- **Descripciones claras.** El modelo elige qué tool llamar según la descripción que le pongas. "Lee un archivo" es peor que "Lee un archivo del filesystem local y devuelve su contenido como texto. Útil cuando el usuario pregunta sobre código o configuración".
- **Pocas tools, mejor.** 5-10 funciona bien. 30+ confunde al modelo.
- **Validar argumentos.** El modelo a veces pasa tipos incorrectos. Siempre validar antes de ejecutar.
- **Idempotencia.** Las tools que escriben (mover archivo, enviar email) deben ser robustas a llamadas duplicadas.
- **Confirmación humana** para acciones irreversibles.

## Mi caso concreto

Claude Code (lo uso para mi TFG) tiene ~15 tools: Read, Edit, Write, Bash, Grep, Glob, WebSearch... La mayoría de los agentes que voy a construir tendrán 3-7 tools cada uno.

## ¿Qué me falta por entender?

- Cómo decidir cuándo una capacidad debe ser tool vs estar implícita en el prompt.
- Cómo testear tools sin gastar tokens (mocks).
- Diferencia real entre "function calling" y "tool use" — creo que es solo nomenclatura.

## Para profundizar

- Anthropic Tool Use docs: https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview
- Anthropic *Building effective agents* (sección de tools): https://www.anthropic.com/research/building-effective-agents

## Relacionado

- [[Agentes IA — MOC]]
- [[MCP]]
- [[LLM]]
- [[Prompt engineering]]
