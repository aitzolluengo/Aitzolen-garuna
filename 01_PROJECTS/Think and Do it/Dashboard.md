# Think&DoIT — Dashboard

## Estado general
```dataview
TABLE status, priority
FROM "Think&DoIT/02-Desarrollo"
SORT file.name ASC
```

## Tareas pendientes
```tasks
not done
path includes Think&DoIT
group by path
```

## Última actividad
```dataview
TABLE file.mtime AS "Modificado"
FROM "Think&DoIT"
SORT file.mtime DESC
LIMIT 10
```