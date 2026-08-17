---
nombre: Brad Pitt
nacionalidad: Estadounidense
tags:
  - tipo/actor
---

# Brad Pitt

![Foto]()

> [!info] Sobre el actor
> **Nacionalidad:** Estadounidense
> **Conocido por:** Una de las mayores estrellas de Hollywood desde los 90. Oscar por Once Upon a Time in Hollywood. Destaca en personajes carismáticos con doble fondo.

---

## 🎬 Películas vistas con este actor
```dataview
TABLE año, director
FROM "03_RESOURCES/Cine/Películas"
WHERE contains(reparto, [[Brad Pitt]])
SORT año DESC
```

## Relacionado
