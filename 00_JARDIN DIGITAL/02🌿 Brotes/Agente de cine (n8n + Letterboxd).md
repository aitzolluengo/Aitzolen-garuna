---
fecha: 2026-07-01
madurez: 🌿
contexto: cine
tags:
  - jardin/brote
---

# Agente de cine (n8n + Letterboxd)

## La idea

No un chat de recomendaciones, sino un **sistema de cine personal** que:
1. Sabe lo que veo (Letterboxd),
2. Me mantiene al día de lo que viene (estrenos),
3. Me hace mejor espectador (aprendizaje guiado).

---

## 🎬 Módulos

### 1. Auto-registro desde Letterboxd
n8n lee mi **RSS de Letterboxd**; cuando marco una peli vista, coge el título → busca ficha en **TMDB** (director, reparto, año, género) → crea/actualiza la **nota de película** en el vault y enlaza director/actores.
- Mata la tarea de "Registrar pelis" para siempre.
- **Herramientas:** Letterboxd RSS · TMDB API · Obsidian (Git/REST) · Claude (para redactar la nota).

### 2. Radar de estrenos a medida
Cron semanal → **TMDB** estrenos en España → filtra por **mis gustos** (deducidos de mi historial de Letterboxd) → me manda a Telegram los que me pegan, con dónde verlos.
- **Herramientas:** TMDB (upcoming + watch providers) · Claude (matching de gustos) · Telegram · cron.

### 3. Escuela de cine (aprendizaje)
Cada X días, una **píldora**: un director, una técnica (montaje, planos, iluminación, color), un actor o un movimiento, con ejemplos concretos de pelis (mías si las he visto). Currículo progresivo, con mini-quiz opcional.
- Contenido **generado por Claude** (original, no copio reseñas/textos con copyright); datos de TMDB/Wikipedia.
- **Herramientas:** Claude · TMDB · Telegram · (nota de apuntes en el vault).

### 4. Watchlist inteligente
Cruza mi **watchlist de Letterboxd** con estrenos y disponibilidad en plataformas → me avisa cuando algo de mi lista se puede ver ya.
- **Herramientas:** Letterboxd RSS (watchlist) · TMDB watch providers · Telegram.

### 5. "¿Qué veo hoy?"
Le digo el mood y el tiempo, y cruza mi watchlist + lo disponible → me propone.

---

## 🧰 Stack

- **Cerebro:** n8n + Claude API
- **Mis datos:** Letterboxd (vía **RSS**, que es lo público — no hay API abierta oficial)
- **Fichas y estrenos:** **TMDB API** (gratis, muy completa, con reparto, estrenos y plataformas)
- **Cara:** Telegram (avisos) + el vault (registro y apuntes)
- **Programación:** cron (estrenos, píldoras) + trigger por nueva peli vista

## ⚠️ Notas honestas
- **Letterboxd no tiene API abierta** (la suya está en lista de espera). Se tira de **RSS público** (diario y watchlist) + export CSV. Suficiente.
- El contenido de aprendizaje lo **genera el agente** (original) apoyándose en datos/factuales; no reproducimos reseñas ni textos con derechos.

## ❓ Preguntas abiertas
- ¿Empezamos por el **auto-registro** (el más útil ya) o por la **escuela de cine** (el más molón)?
- ¿Avisos por **Telegram**, dentro del **vault**, o ambos?
- Mi usuario de Letterboxd para conectar el RSS.

## Relacionado
- [[Agente IA orquestado con n8n]]
- [[RAG de mi vault]]
- [[Inbox]]
- [[🌿 Jardin de Ideas]]
