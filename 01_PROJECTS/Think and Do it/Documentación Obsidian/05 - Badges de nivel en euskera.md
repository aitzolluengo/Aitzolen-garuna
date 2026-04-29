---
fecha: 2026-04-29
madurez: 🌳
contexto: ThinkAndDoIT — desarrollo web
tags:
  - tipo/referencia
---

# Badges de nivel en euskera

## Problema

Los badges de nivel de ejercicio mostraban el valor interno de la base de datos directamente en la UI: `FACIL`, `MEDIO`, `DIFICIL`. La interfaz es en euskera pero estas etiquetas aparecían en castellano.

```jsp
<span class="badge-pill badge-<%= ejercicio.getNivel() %>">
    <%= ejercicio.getNivel() %>
</span>
```

## Solución

Se añade una traducción al euskera antes de renderizar el badge. La clase CSS sigue usando el valor interno (para el color), pero el texto visible es el traducido:

```jsp
<%
  String nivelLabel = "FACIL".equals(ejercicio.getNivel()) ? "Erraza"
                    : "DIFICIL".equals(ejercicio.getNivel()) ? "Zaila" : "Ertaina";
%>
<span class="badge-pill badge-<%= ejercicio.getNivel() %>">
    <%= nivelLabel %>
</span>
```

## Tabla de traducción

| Valor BD | Texto mostrado | Color |
|---|---|---|
| `FACIL` | Erraza | Verde (`#d1fae5 / #065f46`) |
| `MEDIO` | Ertaina | Amarillo (`#fef3c7 / #92400e`) |
| `DIFICIL` | Zaila | Rojo (`#fee2e2 / #991b1b`) |

## Archivos afectados

- `clase-detalle.jsp` — lista de ejercicios de la clase
- `ejercicio-detalle.jsp` — topbar del ejercicio individual

## Nota

El valor almacenado en la base de datos permanece en inglés/castellano (`FACIL`, `MEDIO`, `DIFICIL`). Solo cambia el texto visible. Esto evita migrar datos y mantiene compatibilidad con la lógica de backend.
