---
fecha: 2026-04-29
tags:
  - dashboard
---

# 📋 Tareas — Dashboard

Vista global de todas las tareas marcadas `- [ ]` en cualquier nota del vault, gracias al plugin **Tasks**. Para crear tareas, ve a [[Inbox]] o métela en cualquier nota con el formato `- [ ] cosa 📅 YYYY-MM-DD`.

## ⚠️ Hoy

```tasks
not done
(due on or before today) OR (scheduled on or before today)
sort by priority
sort by due
hide backlinks
```

## 📅 Esta semana

```tasks
not done
(due after today) AND (due before in 7 days)
sort by due
sort by priority
hide backlinks
```

## 🔥 Atrasadas

```tasks
not done
due before today
sort by due
hide backlinks
```

## 🆕 Sin fecha

```tasks
not done
no due date
no scheduled date
sort by priority
hide backlinks
```

## 🎯 Por prioridad alta

```tasks
not done
priority is high
sort by due
hide backlinks
```

## ✅ Completadas esta semana

```tasks
done
done after 7 days ago
sort by done reverse
hide backlinks
```

## Cómo añadir tareas

Plugin Tasks usa un formato simple. En cualquier nota:

```
- [ ] Mandar correo a la tutora 📅 2026-05-02 ⏫ #tfg
```

Iconos:
- `📅 fecha` — fecha límite (due)
- `⏳ fecha` — programada (scheduled)
- `🛫 fecha` — empezar (start)
- `⏫` alta · `🔼` media · `🔽` baja — prioridad
- `🔁 every week` — recurrente
- `#tag` — etiqueta normal

## Relacionado

- [[Inbox]]
- [[Plan Semanal]]
