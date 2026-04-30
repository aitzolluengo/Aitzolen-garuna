---
nombre: <% tp.file.title %>
nacionalidad:
tags:
  - tipo/director
---

# <% tp.file.title %>

![Foto]()

> [!info] Sobre el director
> **Nacionalidad:**
> **Años activo:**
> **Estilo:**

---

## 🎬 Películas vistas
```dataview
TABLE año, puntuacion AS "⭐"
FROM "03_RESOURCES/Cine/Películas"
WHERE director = [[<% tp.file.title %>]]
SORT año DESC
```

## 🎥 Películas pendientes
- [ ] 

## Relacionado