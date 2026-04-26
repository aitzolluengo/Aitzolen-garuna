---
nombre: <% tp.file.title %>
tags:
  - tipo/director
---

# <% tp.file.title %>

## Películas vistas
```dataview
TABLE año, puntuacion AS "⭐"
FROM "03_RESOURCES/Cine/Películas"
WHERE director = [[<% tp.file.title %>]]
```

## Relacionado
- [[Dashboard Cine]]