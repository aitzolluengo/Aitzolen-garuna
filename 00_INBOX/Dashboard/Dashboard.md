# Dashboard

> Punto de entrada diario al segundo cerebro.

## 📥 Inbox pendiente
```dataview
LIST FROM "00_Inbox"
SORT file.ctime ASC
```

## 🚀 Proyectos activos
```dataview
TABLE fecha_inicio, estado
FROM "01_Projects"
WHERE estado = "activo"
SORT fecha_inicio DESC
```

## ✅ Tareas pendientes
```dataview
TASK FROM ""
WHERE !completed
GROUP BY file.link
LIMIT 20
```

## 📅 Últimas notas creadas
```dataview
TABLE file.ctime AS "Creada", file.folder AS "Carpeta"
FROM ""
WHERE file.folder != "00_Inbox"
AND file.name != "Dashboard"
SORT file.ctime DESC
LIMIT 7
```

## 📚 Notas de aprendizaje recientes
```dataview
TABLE fecha
FROM #area/aprendizaje
SORT fecha DESC
LIMIT 5
```

## 🔄 Revisiones semanales
```dataview
LIST FROM #tipo/daily
SORT file.ctime DESC
LIMIT 5
```