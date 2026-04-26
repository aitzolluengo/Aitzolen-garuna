# MOC — Cine

> Índice central de todo el conocimiento cinematográfico del vault.
> Punto de entrada para explorar, descubrir y conectar películas.

## 📊 Estado actual
```dataview
TABLE WITHOUT ID
"Vistas: " + length(filter(file.tags, t => t = "cine/vista")) AS " "
FROM "03_Resources/Cine/Películas"
```

```dataview
TABLE WITHOUT ID
length(rows) AS "Total vistas"
FROM "03_Resources/Cine/Películas"
WHERE contains(tags, "cine/vista")
```

## 🎬 Últimas vistas
```dataview
TABLE director, año, puntuacion
FROM "03_Resources/Cine/Películas"
WHERE contains(tags, "cine/vista")
SORT fecha_vista DESC
LIMIT 5
```

## ⭐ Mejores películas
```dataview
TABLE director, año
FROM "03_Resources/Cine/Películas"
WHERE puntuacion = "⭐⭐⭐⭐⭐"
SORT año ASC
```

## 📋 Por ver
```dataview
LIST FROM "03_Resources/Cine/Películas"
WHERE contains(tags, "cine/por-ver")
SORT file.name ASC
```

## 🎯 Top 500 — Progreso
- [[Top 500 - Seguimiento]]

## 🎭 Directores
```dataview
TABLE length(rows) AS "Películas vistas"
FROM "03_Resources/Cine/Películas"
WHERE contains(tags, "cine/vista")
GROUP BY director
SORT length(rows) DESC
```

## 🗂️ Por década
```dataview
TABLE length(rows) AS "Películas"
FROM "03_Resources/Cine/Películas"
WHERE contains(tags, "cine/vista")
GROUP BY string(floor(number(año) / 10) * 10) + "s"
SORT rows.año ASC
```

## 🔗 Índices por director
- [[Stanley Kubrick]]
- [[Andrei Tarkovsky]]
- [[Ingmar Bergman]]
- [[Akira Kurosawa]]

## 📚 Recursos
- [[Cómo analizar una película]]
- [[Géneros cinematográficos]]
- [[Flujo de notas de cine]]

## Relacionado
- [[Flujo de notas de cine]]
- [[Top 500 - Seguimiento]]
- [[Dashboard]]