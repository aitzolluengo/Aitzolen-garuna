---
tags:
  - compras/MOC
---

# 🛍️ Compras — Panel de control

> Viabilidad calculada con tu [[💰 Finanzas|ahorro mensual]]. Rellena ese archivo primero.

---

## 🔴 Alta prioridad

```dataview
TABLE
  precio AS "€",
  plazo_objetivo AS "Plazo",
  marca AS "Marca",
  tipo AS "Tipo"
FROM #compras/articulo
WHERE estado = "⏳ Pendiente"
  AND prioridad = "🔴 Alta"
  AND !contains(file.name, "Plantilla")
SORT plazo_objetivo ASC
```

---

## 🟡 Media prioridad

```dataview
TABLE
  precio AS "€",
  plazo_objetivo AS "Plazo",
  marca AS "Marca",
  tipo AS "Tipo"
FROM #compras/articulo
WHERE estado = "⏳ Pendiente"
  AND prioridad = "🟡 Media"
  AND !contains(file.name, "Plantilla")
SORT plazo_objetivo ASC
```

---

## 🟢 Caprichos / largo plazo

```dataview
TABLE
  precio AS "€",
  plazo_objetivo AS "Plazo",
  marca AS "Marca",
  tipo AS "Tipo"
FROM #compras/articulo
WHERE estado = "⏳ Pendiente"
  AND prioridad = "🟢 Baja"
  AND !contains(file.name, "Plantilla")
SORT plazo_objetivo ASC
```

---

## ✅ Historial

```dataview
TABLE
  precio AS "€",
  fecha_compra AS "Comprado",
  marca AS "Marca"
FROM #compras/articulo
WHERE estado = "✅ Comprado"
  AND !contains(file.name, "Plantilla")
SORT fecha_compra DESC
```

---

**Acciones:** [[000_INBOX/Plantillas/Compras/Articulo|➕ Nueva compra]] · [[💰 Finanzas|💰 Ver finanzas]]
