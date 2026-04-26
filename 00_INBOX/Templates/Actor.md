---
nombre: <% tp.file.title %>
tags:
  - tipo/actor
---

# <% tp.file.title %>

## Películas vistas
```dataview
TABLE año, director
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(reparto, "[[<% tp.file.title %>]]")
```

## Relacionado
- [[Dashboard Cine]]