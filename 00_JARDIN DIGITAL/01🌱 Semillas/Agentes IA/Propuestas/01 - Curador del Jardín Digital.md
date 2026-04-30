---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / jardin-digital
tags:
  - jardin/semilla
---

# Curador del Jardín Digital

## La idea original

Tu jardín está descompensado: 2 semillas, 1 brote, 0 árboles, 5 en calma. Algunas notas en `04❄️ Calma/` llevan parados desde el 2026-04-26 sin moverse. Un agente que cuide el jardín haciendo lo que tú harías en una revisión semanal: mover de etapa, detectar estancadas, y proponer enlaces que se te escapan.

## Objetivo

Mantener el jardín vivo automáticamente — que las ideas progresen sin requerir disciplina manual de revisión.

## Inputs (qué leerá)

- Todas las notas de `00_JARDIN DIGITAL/` con su frontmatter (`fecha`, `madurez`, `tags`).
- Fechas de modificación del filesystem para detectar estancamiento (>30 días sin tocar).
- Contenido completo de cada nota para sugerir links semánticos cruzados con el resto del vault.

## Outputs

1. **Nota `00_JARDIN DIGITAL/🌿 Jardin de Ideas.md`** actualizada con tabla Dataview de estado (esto ya lo puedes hacer sin IA, pero el agente añade comentarios de "esta semilla podría pasar a brote porque...").
2. **Nota nueva `000_INBOX/Revisión Jardín YYYY-MM-DD.md`** semanal con:
   - Semillas que tienen suficiente desarrollo para promocionar a brote
   - Brotes con 3+ revisiones para promocionar a árbol
   - Notas en calma con >60 días → propuesta de archivar
   - Top 5 pares de notas que deberían enlazarse (con cita de fragmento que justifica el link)
3. **No mueve nada solo** — propone, tú confirmas con un toque en checkboxes.

## Stack sugerido

- **LLM:** Ollama local (`qwen2.5:7b` o `llama3.1:8b`) — privacidad sobre tus notas personales.
- **Embeddings:** `nomic-embed-text` vía Ollama para detectar similitud semántica entre notas (sustituye Smart Connections Pro).
- **Vector store:** ChromaDB local o `sqlite-vec` (cero dependencias).
- **Lenguaje:** Python con `ollama` + `chromadb` + librería `python-frontmatter`.

## Pasos de implementación

1. Script `index_vault.py` que recorre todo `*.md`, parsea frontmatter, extrae cuerpo, calcula embeddings con Ollama y los guarda en Chroma. Indexar incremental por mtime.
2. Script `gardener.py` que:
   - Lista notas del jardín con su madurez y mtime
   - Para cada semilla: pide al LLM "¿esta nota tiene >3 secciones desarrolladas? ¿está conectada a otras?" → propuesta de promoción
   - Para cada nota: query top-5 vecinos en Chroma → propuesta de links
3. Salida formateada como Markdown a `000_INBOX/Revisión Jardín YYYY-MM-DD.md`.
4. Cron semanal (domingo noche) o disparador manual desde QuickAdd.

## Prioridad

🟢 **Alta.** Es el caso que tu propio brote [[Segundo cerebro]] reconoce como pendiente ("Cómo integrar IA local cuando sea posible"). Resuelve el problema concreto que [[Smart connections con Ollama]] dejó aparcado.

## Riesgos / matices

- Coste de embeddings inicial: ~30s para 134 notas, después incremental.
- El LLM puede alucinar enlaces — mostrar siempre la cita textual que justifica el link.
- No tocar notas con `agente: false` en frontmatter.

## Relacionado

- [[Segundo cerebro]]
- [[Smart connections con Ollama]]
- [[🌿 Jardin de Ideas]]
- [[00 - Ideas Agentes IA — MOC]]
