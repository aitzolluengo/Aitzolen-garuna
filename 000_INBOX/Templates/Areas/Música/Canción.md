---
fecha: <% tp.date.now("YYYY-MM-DD") %>
titulo: <% tp.file.title %>
estado: <% tp.system.suggester(["idea", "en progreso", "completa"], ["idea", "en progreso", "completa"]) %>
tags:
  - tipo/cancion
  - musica/<% tp.system.suggester(["idea", "letra", "completa"], ["idea", "letra", "completa"]) %>
---

# <% tp.file.title %>

## Inspiración
¿De dónde viene esta idea?

## Feeling / Mood
¿Qué sensación transmite?

## Letra
### Intro

### Estrofa 1

### Estribillo

### Estrofa 2

### Puente

### Outro

## Notas musicales
Tempo, acordes, estilo...

## Relacionado
- [[]]