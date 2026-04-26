# 🎬 Dashboard Cine

## 🎬 Últimas vistas
```dataview
TABLE director AS director, año, puntuacion AS "⭐"
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(tags, "cine/vista")
SORT fecha_vista DESC
LIMIT 5
```

## 📋 Por ver
```dataview
TABLE director, año
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(tags, "cine/por-ver")
SORT file.name ASC
```

## 🎭 Directores
```dataview
TABLE length(rows) AS "Películas vistas"
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(tags, "cine/vista")
GROUP BY director
SORT length(rows) DESC
```

## 👤 Actores
```dataview
LIST FROM "03_RESOURCES/Cine/Actores"
SORT file.name ASC
```