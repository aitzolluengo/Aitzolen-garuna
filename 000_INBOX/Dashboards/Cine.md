---
cssclasses:
  - cards
  - cards-16-9
  - cards-align-bottom
---

# 🎬 Filmoteca Personal

> [!abstract] Estadísticas Rápidas
> - 🍿 **Vistas:** `$=dv.pages('"03_RESOURCES/Cine/Películas"').where(p => p.tags.includes("cine/vista")).length` películas.
> - ⏳ **Pendientes:** `$=dv.pages('"03_RESOURCES/Cine/Películas"').where(p => p.tags.includes("cine/por-ver")).length` películas.

---
## ⏳ Lista de Seguimiento (Pendientes)
```dataview
TABLE WITHOUT ID
	poster AS "Póster",
	file.link AS "Título",
	director AS "Director",
	año AS "Año"
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(tags, "cine/por-ver")
SORT file.name ASC
```
---

## 🍿 Últimas Películas Vistas
```dataview
TABLE WITHOUT ID
	file.link AS "Título",
	director AS "Director",
	año AS "Año",
	puntuacion AS "⭐"
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(tags, "cine/vista")
SORT fecha_vista DESC
LIMIT 8
```

---



---

> [!multi-column]
>
>> [!info] 🎭 Directores Favoritos
>> ```dataview
>> LIST 
>> FROM "03_RESOURCES/Cine/Películas"
>> WHERE contains(tags, "cine/vista")
>> GROUP BY director
>> SORT length(rows) DESC
>> LIMIT 5
>> ```
>
>> [!user] 👤 Actores
>> ```dataview
>> LIST FROM "03_RESOURCES/Cine/Actores"
>> SORT file.name ASC
>> LIMIT 10
>> ```

---
**Enlaces:** [[000_INBOX/Inbox|📥 Inbox]] | [[03_RESOURCES/Cine/00_Tareas_Cine|📋 Tareas Cine]]