---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / personal
tags:
  - jardin/semilla
---

# Ideas Agentes IA — MOC

Mapa de propuestas de agentes de IA sobre tu vault. Todas parten de patrones reales que ya tienes y pretenden quitarte trabajo manual.

> **Origen:** brote [[Segundo cerebro]] (pendiente "Cómo integrar IA local cuando sea posible") + semilla en calma [[Aprender Flowise]] + [[Smart connections con Ollama]].

## Resumen rápido

| # | Agente | Qué automatiza | Prioridad |
|---|---|---|---|
| 1 | [[01 - Curador del Jardín Digital]] | Mover semillas → brotes → árboles, detectar notas estancadas, sugerir links | 🟢 Alta |
| 2 | [[02 - Generador del Plan Semanal]] | Crear el `Plan Semanal YYYY-MM-DD` cada lunes con encoding correcto | 🟢 Alta |
| 3 | [[03 - Tutor de Inglés B2]] | Genera práctica semanal de writing + mini-test gramatical | 🟢 Alta |
| 4 | [[04 - Asistente de TFG (Think&DoIT)]] | Resumen para reuniones con tutor desde sesiones diarias | 🟢 Alta |
| 5 | [[05 - Procesador del INBOX (GTD)]] | Clasifica notas sueltas a la carpeta PARA correcta | 🟡 Media |
| 6 | [[06 - Recomendador de Cine]] | Sugiere películas basándose en directores/actores que ya te gustan | 🟡 Media |
| 7 | [[07 - Coach de Kirola]] | Microciclo semanal a partir de Periodización y entrenamientos | 🔵 Baja |

## Cómo elegir cuál hacer primero

- **Si quieres alivio inmediato y aprender la mecánica de un agente sencillo** → empieza por #2 (plan semanal). Es 1 prompt + 1 cron, sin RAG.
- **Si quieres lo más útil a largo plazo** → #1 (curador del jardín). Es donde tienes más fricción manual.
- **Si quieres demostrar que el sistema funciona y escalar a TFG** → #4 (asistente TFG). Reutilizable como caso de éxito en la memoria.

## Stack común propuesto

- **LLM:** Ollama local (gpt-oss, qwen2.5, llama3.1) o API gratuita (OpenRouter — ya lo tienes en INBOX como tarea).
- **Embeddings (cuando haya RAG):** `nomic-embed-text` o `bge-m3` vía Ollama.
- **Orquestación:** scripts Python sueltos al principio. [[Aprender Flowise]] cuando varios agentes compartan herramientas.
- **Lectura/escritura del vault:** filesystem directo (todo es Markdown + frontmatter).
- **Disparadores:** cron, Obsidian QuickAdd, o comando manual `python agents/<nombre>.py`.

## Convenciones para todos los agentes

1. **Nunca tocan notas con frontmatter `agente: false`.** Permite vetar manualmente.
2. **Cada cambio del agente añade `agente: <nombre>` y `agente_fecha: YYYY-MM-DD` al frontmatter.** Auditoría.
3. **Los agentes proponen en una nota nueva, no editan notas existentes** — salvo el #1 que mueve archivos entre carpetas (con confirmación previa por consola).
4. **Idioma de salida:** mismo idioma de la nota fuente (castellano por defecto, euskera si está en `area/aprendizaje-euskera`).

## Relacionado

- [[🌿 Jardin de Ideas]]
- [[Segundo cerebro]]
- [[Aprender Flowise]]
- [[Smart connections con Ollama]]
- [[Cómo usar este vault]]
