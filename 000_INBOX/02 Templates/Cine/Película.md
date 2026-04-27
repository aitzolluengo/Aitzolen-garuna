---
fecha_vista: <% tp.date.now("YYYY-MM-DD") %>
titulo: <% tp.file.title %>
director: 
año: 
genero: 
reparto:
  - "[[]]"
  - "[[]]"
  - "[[]]"
puntuacion: 
tags:
  - tipo/pelicula
  - cine/<% tp.system.suggester(["vista", "por-ver"], ["vista", "por-ver"]) %>
---

# <% tp.file.title %>

> [!info] Ficha técnica
> **Director:** [[]]
> **Año:** 
> **País:** 
> **Género:** 
> **Duración:** 
> **Reparto:** [[]], [[]], [[]]

![Póster]()

---

> [!quote] Primera reacción
> *Escribe aquí nada más terminarla*

---

## 🎬 La escena que no me puedo quitar

## 🧠 ¿De qué trata realmente?
> No el argumento — el tema de fondo.

## 💥 Lo que me ha removido

## 👥 ¿A quién se la recomendaría?

## 🔗 Conexiones
- [[]]

## ⭐ Puntuación
> [!success] <% tp.system.prompt("Puntuación (1-5 estrellas)") %>

## Relacionado
- [[Dashboard Cine]]