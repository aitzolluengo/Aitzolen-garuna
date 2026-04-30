---
fecha: 2026-04-30
tags:
  - dashboard
---

# 📋 Tareas — Dashboard

Vista global de todas las tareas marcadas `- [ ]` en cualquier nota del vault, gracias al plugin **Tasks**.

> **`happens`** = el plugin coge la fecha más temprana entre `📅 due`, `⏳ scheduled` y `🛫 start`. Por eso una tarea con start date hoy aparece en "Hoy" sin que tengas que duplicar fechas.

## ⚠️ Hoy

Tareas que tocan hoy o están atrasadas.

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

Sin contar hoy ni mañana.

```tasks
not done
happens after tomorrow
happens before in 8 days
sort by happens
sort by priority
hide backlinks
```

## 🔥 Atrasadas

Lo que se me pasó. Si aparece algo aquí, hoy lo refresco con fecha nueva o lo hago.

```tasks
not done
happens before today
sort by happens
hide backlinks
```

## 🆕 Sin fecha

Tareas capturadas que no tienen ninguna fecha. Procesar el domingo.

```tasks
not done
no due date
no scheduled date
no start date
sort by priority
hide backlinks
```

## 🎯 Prioridad alta (todas)

```tasks
not done
priority is high
sort by happens
hide backlinks
```

## 📂 Agrupadas por carpeta (visión global)

Para revisión semanal. Útil para ver qué tareas viven en qué proyecto/área.

```tasks
not done
sort by happens
group by folder
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

En cualquier nota:

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
| `#tag` | Etiqueta |

### Diferencia entre `📅`, `⏳` y `🛫`

- `📅 due` — **deadline.** Si pasa, está atrasada.
- `⏳ scheduled` — **lo planeo para ese día**, sin compromiso de deadline.
- `🛫 start` — **antes de esa fecha no puedo trabajarla** (depende de algo). Útil para tareas bloqueadas.

Para la mayoría de tareas con `📅` basta. Usa `🛫` solo cuando hay dependencia real.

## Relacionado

- [[Inbox]]
- [[Plan Semanal]]
- [[Flujo de trabajo]]
