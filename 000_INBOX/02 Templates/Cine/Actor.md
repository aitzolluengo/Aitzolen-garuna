---
nombre: <% tp.file.title %>
nacionalidad:
tags:
  - tipo/actor
---

# <% tp.file.title %>

![Foto]()

> [!info] Sobre el actor
> **Nacionalidad:**
> **Conocido por:**

---

## 🎬 Películas vistas con este actor
```dataview
TABLE año, director
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(reparto, [[<% tp.file.title %>]])
SORT año DESC
```

## Relacionado
- [[Dashboard Cine]]