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

# MCP

**Model Context Protocol** — estándar abierto creado por Anthropic en 2024 para que cualquier agente IA pueda conectarse a cualquier servicio externo sin reinventar la integración.

## Por qué existe

Antes de MCP: si quería que mi agente leyera Gmail, escribía un cliente de Gmail. Si quería que tocara Notion, escribía otro cliente. Y otro para GitHub, Calendar, Slack… Cada agente reinventaba todas las integraciones.

MCP estandariza la interfaz: **un servidor MCP expone un servicio (Gmail, Notion, mi vault de Obsidian) en un protocolo común; cualquier cliente MCP (Claude Desktop, Claude Code, Cursor…) puede conectarse y usarlo automáticamente**.

Es a los agentes lo que USB fue a los periféricos: conectas, funciona.

## Cómo encaja con [[Tools y function calling]]

Tools = funciones que mi agente expone al [[LLM]] dentro del mismo proceso.

MCP = protocolo para que un servicio **externo** exponga sus tools, recursos y prompts a cualquier agente compatible.

Detrás del telón, MCP también acaba siendo function calling — pero el agente no tiene que conocer cada servicio de antemano: descubre las tools al conectar.

## Servidores MCP que ya existen (2026)

- **Filesystem** — leer/escribir archivos locales
- **Git / GitHub** — repos, PRs, issues
- **Gmail, Calendar, Drive** — Google Workspace
- **Slack** — mensajes y canales
- **Notion** — bases de datos y páginas
- **Obsidian** — varios proyectos comunitarios exponen el vault como servidor MCP
- **Postgres / SQLite** — consultar bases de datos
- **TMDB, Spotify, YouTube** — APIs públicas

## Idea para mi vault

Si convierto mi vault en servidor MCP, puedo hablar con él desde Claude Desktop / Claude Code sin construir un agente desde cero. Las tools del servidor serían:
- `crear_nota(carpeta, titulo, contenido, frontmatter)`
- `buscar_notas(query)` (con [[RAG]] detrás)
- `obtener_dataview(query)`
- `mover_nota(origen, destino)`

## ¿Qué me falta por entender?

- Cómo se autentica un servidor MCP (¿auth tokens? ¿solo local?).
- Diferencia entre servidor MCP local (stdio) y remoto (HTTP/SSE).
- Cómo se versionan las tools cuando un servidor evoluciona.

## Para profundizar

- Spec oficial MCP: https://modelcontextprotocol.io/
- Repo con servidores MCP de referencia: https://github.com/modelcontextprotocol/servers
- Anthropic MCP launch: https://www.anthropic.com/news/model-context-protocol

## Relacionado

- [[Tools y function calling]]
- [[Agentes IA — MOC]]
- [[Recursos agentes IA]]
