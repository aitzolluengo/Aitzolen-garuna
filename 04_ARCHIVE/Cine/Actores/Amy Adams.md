---
nombre: Amy Adams
nacionalidad: Estadounidense
tags:
  - tipo/actor
---

# Amy Adams

![Foto]()

> [!info] Sobre el actor
> **Nacionalidad:** Estadounidense
> **Conocido por:** Una de las actrices más versátiles de Hollywood. Seis nominaciones al Oscar. Su Louise en Arrival es probablemente su mejor trabajo.

---

## 🎬 Películas vistas con este actor
```dataview
TABLE año, director
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(reparto, [[Amy Adams]])
SORT año DESC
```

## Relacionado
