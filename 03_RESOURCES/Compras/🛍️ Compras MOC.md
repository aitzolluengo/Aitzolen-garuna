---
tags:
  - compras/MOC
---

# 🛍️ Compras & Inventario (MOC)

Este es el centro de control para tus compras. Utiliza los tags `#compras/tecnologia`, `#compras/ropa`, etc., para que los artículos aparezcan aquí automáticamente.

---

## 💻 Tecnología
```dataview
TABLE marca AS "Marca", precio AS "Precio", estado AS "Estado", enlace AS "Link"
FROM #compras/tecnologia
WHERE !contains(file.name, "Plantilla")
SORT estado DESC, file.name ASC
```

---

## 👕 Ropa
```dataview
TABLE marca AS "Marca", precio AS "Precio", estado AS "Estado"
FROM #compras/ropa
WHERE !contains(file.name, "Plantilla")
SORT estado DESC, file.name ASC
```

---

## 📦 Otros / Pendientes
```dataview
TABLE tipo AS "Tipo", precio AS "Precio", estado AS "Estado"
FROM #compras/articulo AND !#compras/tecnologia AND !#compras/ropa
WHERE !contains(file.name, "Plantilla")
SORT file.name ASC
```

---

## ✅ Historial de Compras (Completado)
```dataview
LIST FROM #compras/articulo
WHERE estado = "✅ Comprado" OR estado = "Comprado"
SORT fecha_compra DESC
```

---
**Acciones:** [Add New Item](obsidian://advanced-uri?vault=Aitzolen%20garuna&template=000_INBOX/Plantillas/Compras/Articulo) | [[000_INBOX/Plantillas/Compras/Articulo|📄 Plantilla Artículo]]
