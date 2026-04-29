---
fecha: 2026-04-29
madurez: 🌱
contexto: agentes-ia / cine
tags:
  - jardin/semilla
---

# Recomendador de Cine

## La idea original

Tienes el sistema de cine montado: 3 películas, 3 directores, 8 actores, dashboard Dataview. Una tarea pendiente apunta a "Ver Trainspotting 2" — claramente sigues el rastro de directores que te gustan. Un agente que mire qué directores/actores ya has visto, qué puntuaciones les pones, y proponga las próximas con metadatos rellenos.

## Objetivo

Que cada vez que abras Obsidian sin saber qué ver, haya 3-5 propuestas alineadas con tus gustos, y al ver una, la nota se cree sola con todo el frontmatter.

## Inputs

- `03_RESOURCES/Cine/Películas/*.md` con frontmatter (`puntuacion`, `director`, `genero`, `tags`).
- `03_RESOURCES/Cine/Directores/*.md` y `Actores/*.md` para conocer el grafo.
- `Dashboard Cine.md` para ver lo que tú ya consideras tu canon.
- (Opcional) MCP de TMDB para metadatos reales y posters.

## Outputs

Nota `03_RESOURCES/Cine/Próximas recomendaciones YYYY-MM-DD.md`:

```markdown
## Top 5 propuestas

### 1. Trainspotting 2 (2017) — Danny Boyle
**Por qué:** Continuación de [[Trainspotting]] (puntuaste 5/5). Mismo director y reparto.
**Género:** Drama · Comedia negra
**Dónde:** Filmin, Movistar+

### 2. ...
```

**Bonus:** comando `python cinema.py --new "Título"` que crea la nota completa de la película con frontmatter relleno desde TMDB y enlaces al director y actores (creando esas notas si no existen).

## Stack sugerido

- **LLM:** Cualquier modelo pequeño local — la lógica de "directores que te gustan" es determinista, el LLM solo redacta el "por qué".
- **MCP TMDB:** opcional pero potente para datos reales (sinopsis, poster, año, duración, reparto).
- **Lenguaje:** Python con `python-frontmatter` + `requests` para TMDB.

## Pasos de implementación

1. Indexar tus películas → calcular ranking de directores y actores por puntuación media ponderada.
2. Para cada director top, consultar TMDB sus filmografías → filtrar las que no has visto.
3. Pedir al LLM redactar las recomendaciones con estilo conversacional.
4. Crear nota de propuestas.
5. Comando `--watched <título>` que actualiza la nota de película con `cine/vista` y `puntuacion`.

## Prioridad

🟡 **Media.** Bajo en utilidad práctica pero alto en disfrute y ejemplo de agente con MCP externo. Buen segundo proyecto para aprender integraciones.

## Variante

Conectado al [[Google Calendar + Obsidian]]: si pones un evento "Cine sábado", el agente te propone 3 películas en función de quién va contigo (si las anotas en el evento) — humor, duración disponible.

## Relacionado

- [[Dashboard Cine]]
- [[03_RESOURCES/Cine]]
- [[00 - Ideas Agentes IA — MOC]]
