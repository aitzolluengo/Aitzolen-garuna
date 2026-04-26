## ¿Para que sirve?

> Plugin para gestionar tareas en todo el vault con fechas,
> prioridades y recurrencia. El estándar profesional en Obsidian.

## Instalación
- Settings → Community plugins → Browse 
- Buscar: "Tasks" 
- Install → Enable

## Configuración inicial
Settings → Tasks
- Global filter: (déjalo vacío)
- Set done date on every completed task: ON
- Recurrence: ON

Cambia el atajo de completar tareas:

Settings → Hotkeys → Tasks: Toggle Done → Ctrl+SPACE

## Sintaxis básica

### Tarea simple
````markdown
- [ ] Ir al médico
````

### Tarea con fecha límite
````markdown
- [ ] Ir al médico con las hojas 📅 2026-04-28
````

### Tarea programada (cuando empezar)
````markdown
- [ ] Estudiar para el examen ⏳ 2026-04-27
````

### Tarea recurrente
````markdown
- [ ] Revisión semanal 🔁 every monday
- [ ] Pagar el gym 🔁 every month
````

### Con prioridad
````markdown
- [ ] ⬆️ Entregar TFG 📅 2026-05-15
- [ ] 🔽 Ordenar el escritorio
````

Simple:

|Situación|Campo|Ejemplo|
|---|---|---|
|**Tengo que hacerla antes del día X**|`Due 📅`|Entregar TFG antes del 15 mayo|
|**Quiero hacerla el día X**|`Scheduled ⏳`|Ir a Foto Antonio el lunes|
|**No puedo hacerla hasta el día X**|`Start 🛫`|Tarea que depende de otra cosa|

## Emojis de Tasks

| Emoji | Significado |
|-------|-------------|
| 📅 | Fecha límite (due) |
| ⏳ | Fecha programada (scheduled) |
| 🛫 | Fecha de inicio (start) |
| 🔁 | Recurrente |
| ⬆️ | Prioridad alta |
| 🔼 | Prioridad media |
| 🔽 | Prioridad baja |

## Estados de tarea

| Sintaxis | Estado |
|----------|--------|
| `- [ ]` | Pendiente |
| `- [x]` | Completada |
| `- [/]` | En progreso |
| `- [-]` | Cancelada |

## Queries — filtrar tareas

Las queries se escriben en bloques ` ```tasks ` y muestran
tareas de todo el vault según los filtros.

### Tareas de hoy
````tasks
not done
due today
sort by priority
````

### Tareas vencidas
````tasks
not done
due before today
sort by due
````

### Esta semana
````tasks
not done
due after today
due before in 7 days
sort by due
````

### Por tag
````tasks
not done
tags include #urgente
````

### Por nota concreta
````tasks
not done
path includes 01_Projects/TFG
````

## Crear tarea con asistente
Ctrl+P → Tasks: Create or edit task

Abre un popup con campos visuales para fecha, prioridad, recurrencia.
Mucho más cómodo que escribir los emojis a mano.

## Archivo global Tareas.md
Crea `Tareas.md` en la raíz con esto:

````markdown
# Tareas

## ⚡ Hoy y mañana
```tasks
not done
due before in 2 days
sort by due
```

## 📅 Esta semana
```tasks
not done
due after today
due before in 7 days
sort by due
```

## 🗓️ Este mes
```tasks
not done
due after in 7 days
due before in 30 days
sort by due
```

## 🌫️ Algún día
```tasks
not done
no due date
sort by description
```

## ✅ Completadas hoy
```tasks
done today
```
````

## Dónde escribir las tareas
Las tareas pueden estar en **cualquier nota** del vault —
Tasks las recoge automáticamente.

Ejemplos:
- En la Daily Note → tareas del día
- En la nota de un proyecto → tareas de ese proyecto
- En `Tareas.md` → tareas generales sin contexto

## Buenas prácticas
- Usa siempre fecha límite para lo urgente — sin fecha se pierde
- Las tareas recurrentes son oro: gym, revisión semanal, pagos
- No pongas fecha a todo — solo lo que tiene deadline real
- Revisa `Tareas.md` cada mañana como primer paso del día

## Relacionado
- [[Dashboard]]
- [[000_INBOX/Templates/W/Revisión semanal]]
- [[Kanban]]
- [[Daily Notes y Periodic Notes]]