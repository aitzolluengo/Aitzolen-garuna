---
nombre: Kevin Bacon
nacionalidad: Estadounidense
tags:
  - tipo/actor
---

# Kevin Bacon

![Foto]()

> [!info] Sobre el actor
> **Nacionalidad:** Estadounidense
> **Conocido por:** Versatilidad para encarnar villanos y personajes moralmente ambiguos. Uno de los actores más prolíficos de Hollywood desde los 80.

---

## 🎬 Películas vistas con este actor
```dataview
TABLE año, director
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(reparto, [[Kevin Bacon]])
SORT año DESC
```

## Relacionado
