> Plugin que convierte tu vault en una base de datos consultable. > Puedes listar, filtrar y ordenar notas como si fuera SQL (SQL es el lenguaje de programación que se utiliza para consultar datos).
> 
## Instalación
- Settings → Community plugins → 
- Browse Buscar: "Dataview" 
- Install → Enable

## Configuración Inicial

Settings → Dataview

- Enable JavaScript Queries: ON
- Enable Inline Queries: ON
- Date Format: YYYY-MM-DD

## ¿Cómo funciona?
Dataview lee el **frontmatter** de tus notas (el bloque `---`)
y lo trata como campos de base de datos.

Si tus notas tienen esto:
```yaml
---
fecha: 2026-04-25
estado: activo
tags:
  - tipo/proyecto
---
```

Dataview puede consultarlo así:
```sql
LIST FROM #tipo/proyecto WHERE estado = "activo"
```

## Tipos de consulta

### LIST — lista simple
```sql
LIST FROM #tipo/proyecto
```
Devuelve lista de todas las notas con ese tag.

### TABLE — tabla con columnas
```sql
TABLE fecha, estado FROM #tipo/proyecto
SORT fecha DESC
```

### TASK — tareas pendientes
```sql
TASK FROM #tipo/daily
WHERE !completed
```
Lista todas las tareas sin completar de tus daily notes.

### CALENDAR — vista calendario
```sql
CALENDAR fecha FROM #tipo/daily
```
Muestra tus daily notes en un calendario.

## Consultas útiles para tu vault

### Proyectos activos
```sql
TABLE fecha_inicio, estado 
FROM "01_Projects"
WHERE estado = "activo"
SORT fecha_inicio DESC
```

### Notas sin tag
```sql
LIST FROM ""
WHERE !tags
```

### Últimas notas creadas
```sql
TABLE file.ctime AS "Creada"
FROM ""
SORT file.ctime DESC
LIMIT 10
```

### Todo lo que hay en Inbox
```sql
LIST FROM "00_Inbox"
SORT file.ctime ASC
```

### Notas de aprendizaje por fecha
```sql
TABLE fecha, file.folder AS "Carpeta"
FROM #area/aprendizaje
SORT fecha DESC
```

### Tareas pendientes de toda la vault
```sql
TASK FROM ""
WHERE !completed
GROUP BY file.link
```

## Dashboard — nota índice con Dataview
Crea una nota `Dashboard.md` en la raíz con esto:

```markdown
# Dashboard

## 📁 Proyectos activos
'''dataview
TABLE fecha_inicio, estado
FROM "01_Projects"
WHERE estado = "activo"
'''

## 📥 Inbox pendiente
'''dataview
LIST FROM "00_Inbox"
SORT file.ctime ASC
'''

## ✅ Tareas pendientes
'''dataview
TASK FROM ""
WHERE !completed
LIMIT 20
'''

## 📅 Últimas notas
'''dataview
TABLE file.ctime AS "Creada"
FROM ""
WHERE file.folder != "00_Inbox"
SORT file.ctime DESC
LIMIT 5
'''
```


## Buenas prácticas
- El frontmatter es la clave — sin él, Dataview no tiene datos
- Usa siempre los mismos nombres de campo (`estado` no `Status`)
- Empieza con consultas simples — LIST antes que TABLE
- El Dashboard es tu punto de entrada diario al vault

## Relacionado
- [[01_Templater]]
- [[Tags]]
- [[Sistema PARA]]
- [[Dashboard EXAMPLE]]