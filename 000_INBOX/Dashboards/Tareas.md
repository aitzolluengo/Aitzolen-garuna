---
fecha: 2026-04-30
tags:
  - dashboard
---

# 📋 Tareas — Dashboard

Vista global de todas las tareas marcadas `- [ ]` en cualquier nota del vault, con el plugin **Tasks**.

> **Sistema de colores por tag** (snippet `task-colors.css`):
> 🔵 `#tfg` · 🟣 `#rowing` · 🟢 `#ingles` · 🟡 `#musica` · 🟠 `#kirola` · 🔴 `#cine` · ⚪ `#personal`

## ⚠️ Hoy

```tasks
not done
happens on or before today
sort by priority
sort by happens
hide backlinks
```

## 🔜 Mañana

```tasks
not done
happens on tomorrow
sort by priority
hide backlinks
```

## 📅 Próximos 7 días

```tasks
not done
happens after tomorrow
happens before in 8 days
sort by happens
sort by priority
hide backlinks
```

## 🔥 Atrasadas

```tasks
not done
happens before today
sort by happens
hide backlinks
```

---

# 🗂️ Por proyecto / área

Mismas tareas pero agrupadas por su tag. Lo que no tiene tag aparece en *(Sin etiqueta)*.

## 🔵 TFG (Think&DoIT)

```tasks
not done
tag includes #tfg
sort by happens
sort by priority
hide backlinks
```

## 🟣 Rowing Fantasy

```tasks
not done
tag includes #rowing
sort by happens
hide backlinks
```

## 🟢 Aprendizaje (inglés)

```tasks
not done
tag includes #ingles
sort by happens
hide backlinks
```

## 🟡 Bajo / Música

```tasks
not done
tag includes #musica
sort by happens
hide backlinks
```

## 🟠 Kirola

```tasks
not done
tag includes #kirola
sort by happens
hide backlinks
```

## 🔴 Cine

```tasks
not done
tag includes #cine
sort by happens
hide backlinks
```

## ⚪ Personal

```tasks
not done
tag includes #personal
sort by happens
hide backlinks
```

## ❓ Sin etiqueta (procesar)

Estas necesitan tag — añádeles una para que se coloreen y aparezcan en el grupo correcto.

```tasks
not done
no tags
sort by happens
hide backlinks
```

---

## 🆕 Sin fecha

```tasks
not done
no due date
no scheduled date
no start date
sort by priority
hide backlinks
```

## 🎯 Prioridad alta

```tasks
not done
priority is high
sort by happens
hide backlinks
```

## ✅ Completadas esta semana

```tasks
done
done after 7 days ago
sort by done reverse
hide backlinks
```

---

## Cómo añadir tareas

```
- [ ] Mandar correo a la tutora 📅 2026-05-02 ⏫ #tfg
```

### Iconos

| Símbolo | Significado |
|---|---|
| `📅` | Fecha límite (due) |
| `⏳` | Programada (scheduled) |
| `🛫` | Empezar (start) |
| `⏫ / 🔼 / 🔽` | Prioridad alta / media / baja |
| `🔁` | Recurrente — `every Sunday`, `every 2 weeks`, `every month` |
| `#tag` | Etiqueta de proyecto/área (ver tabla arriba) |

## Relacionado

- [[Inbox]]
- [[Plan Semanal]]
- [[Flujo de trabajo]]
- [[Tareas TFG]]
- [[Tareas Rowing]]
