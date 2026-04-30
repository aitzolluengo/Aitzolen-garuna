---
fecha: <% tp.date.now("YYYY-MM-DD") %>
semana: <% tp.date.now("WW") %>
tags:
  - tipo/resumen-fitness
---

# Fitness — Semana <% tp.date.now("WW") %>

## Entrenamientos de la semana
```dataview
TABLE tipo, distancia
FROM "02_Areas/Fitness"
WHERE semana = this.semana
SORT fecha ASC
```

## Volumen fuerza
- Sesiones: 
- Grupos trabajados:

## Volumen running
- KM totales:
- Sesión más larga:

## Sensación general
¿Cómo ha ido la semana?

## Foco semana que viene