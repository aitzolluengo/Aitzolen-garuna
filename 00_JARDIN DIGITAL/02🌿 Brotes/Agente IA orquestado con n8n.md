---
fecha: 2026-07-01
madurez: 🌿
contexto: IA
tags:
  - jardin/brote
---

# Agente IA orquestado con n8n

> Brainstorming de un agente de IA "super tocho" (no del vault), montado con **n8n** como cerebro orquestador + varias herramientas. Idea abierta, para elegir dirección.

## La idea

No un chat suelto, sino un **sistema**: n8n conecta un LLM (Claude) con muchas herramientas (Telegram, APIs, scraping, base de datos, calendario…) y automatiza flujos con triggers programados y webhooks. El agente *hace cosas en el mundo*, no solo responde.

## ¿Por qué n8n?

- **Visual**: montas flujos arrastrando nodos, ves qué pasa en cada paso.
- **400+ integraciones** listas (Telegram, Gmail, Google Sheets/Calendar, Notion, HTTP…).
- **Triggers**: por horario (cron), por webhook, por evento → agentes que trabajan solos.
- **Nodos de IA / LangChain** integrados → agentes con herramientas y memoria.
- **Self-host gratis** → control y coste bajo.

---

## 🧠 Menú de ideas (de más a menos "tocho")

### 1. 🥇 Asistente personal orquestador (Telegram + n8n)
Le escribes por Telegram cualquier cosa y n8n **enruta** a sub-flujos: apuntar en el calendario, guardar nota, resumir un enlace, buscar en la web, añadir a la compra, registrar gasto o entreno.
- **Herramientas:** Telegram Bot · Claude API · Google Calendar · Web search · Supabase/Sheets · (Obsidian vía Git/REST).
- **Por qué tocho:** es el "mando único" de tu vida digital. Un cerebro, muchas manos.

### 2. 🥈 Cazador de gangas para revender
n8n rastrea Wallapop/Vinted por horario, el LLM **valora** si está infravalorado y te **pinga** por Telegram las oportunidades.
- **Herramientas:** HTTP/scraping · Claude (valoración) · Telegram · BBDD para histórico.
- **Por qué tocho:** dinero real + scraping + IA + alertas. La versión honesta de "ganar con un bot".

### 3. 🥉 Agente buscatrabajo
Rastrea ofertas (InfoJobs/LinkedIn), filtra por tu perfil, **adapta CV y carta** con el LLM y lleva seguimiento en una tabla.
- **Herramientas:** scraping/API de empleo · Claude · Notion/Sheets · Telegram/email.
- **Por qué útil:** justo al acabar el TFG.

### 4. Digest diario de IA/noticias
Cada mañana junta RSS/newsletters de temas tuyos, los **resume** y te manda un boletín a Telegram/email.
- **Herramientas:** RSS · Claude · Telegram/Gmail · cron.

### 5. Máquina de contenido de cine
Detecta estrenos (API de TMDB), genera reseñas con tu criterio y las **programa** en redes/Notion.
- **Herramientas:** TMDB · Claude · Buffer/redes · Notion.

### 6. Ingest al "segundo cerebro"
Artículos guardados, vídeos de YouTube "ver más tarde", notas de voz → **transcribe/resume** → archiva en Obsidian.
- **Herramientas:** webhooks · Whisper/transcripción · Claude · Obsidian (Git).

### 7. Equipo multi-agente
Un orquestador delega en agentes especializados (investigador, redactor, crítico) vía n8n.
- **Por qué tocho:** máximo flex técnico y oro para el portfolio.

---

## 🧰 Herramientas que suelen entrar

- **Cerebro:** n8n + Claude API
- **Cara / entrada:** Telegram (lo más usado por accesibilidad), webhooks
- **Datos:** Supabase / Google Sheets / Notion
- **Acciones:** Calendar, Gmail, scraping HTTP, APIs varias
- **Programación:** cron / triggers

## ❓ Preguntas abiertas
- ¿Objetivo: que me ahorre curro diario, que dé dinero, o que luzca en el CV?
- ¿Dónde alojo n8n (local en el PC vs nube/n8n Cloud)?
- ¿Empezamos por UN flujo simple (MVP) y crecemos, o diseñamos el sistema entero?

---

## 💡 Ideas extra (inspiradas en artículos, 2026-07-01)

De [DataCamp – Top AI agent projects](https://www.datacamp.com/es/blog/top-ai-agent-projects) y [AgenteOpenClaw – ejemplos](https://agenteopenclaw.com/agentes-ia/ejemplos-agentes-ia/), remezcladas a mi perfil:

- **🇬🇧 Tutor de inglés B2 personalizado** *(de "Language Tutor con Langflow")* — genera textos de lectura a mi nivel de vocabulario, me corrige y sube dificultad sola. Uso diario, objetivo B2 claro. → Claude + BBDD de vocabulario + Telegram.
- **🥗 Coach de nutrición con foto del plato** *(de "Nutrition Coach con Mistral")* — registra comidas, calcula calorías, sugiere y genera la imagen del plato. Se enchufa a [[Nutrición]] y [[Recetas para Ama]].
- **🛠️ Agente que arregla mi propio código** *(de "SWE-agent / Devin")* — lo apunto a mi repo (ej. `recetas-ama`), le pido una feature/bug y hace el PR. Práctico + oro para el CV.
- **📚 Resumidor + "leer más tarde" a Obsidian** *(de "Web Summarizer / Deep Research")* — le paso un artículo/vídeo, lo resume y lo archiva en el vault. Alimenta el segundo cerebro.
- **🎸 Coach de bajo/música** — el patrón del tutor de idiomas aplicado a teoría musical y entrenamiento de oído. Nicho total.

## 🔜 Tarea
- [ ] Revisar estas ideas de agentes y elegir cuál montar 📅 2026-07-02 #personal

## Relacionado
- [[Agente de cine (n8n + Letterboxd)]]
- [[RAG de mi vault]]
- [[IA bot nutrición y deporte]]
- [[Recetas para Ama]]
- [[🌱 Jardinero — procesar el Inbox con IA|Jardinero]]
- [[Inbox]]
