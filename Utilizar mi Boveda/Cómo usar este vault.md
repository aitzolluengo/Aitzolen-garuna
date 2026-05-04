---
fecha: 2026-04-30
tags:
  - sistema
---

# 🧠 SISTEMA — Guía de mi bóveda

> Este documento explica cómo funciona mi vault de Obsidian. Si llevo tiempo sin abrirla, o si quiero explicárselo a alguien, leo esto primero. Es la **referencia definitiva**.

---

## 1. ¿Para qué existe esta bóveda?

El objetivo es construir un **segundo cerebro**: un lugar donde ninguna idea se pierda, donde el conocimiento se conecte solo, y donde cada proyecto tenga un hilo del que tirar cuando vuelva a él.

Mi vida no es lineal. Llevo varios proyectos en paralelo (TFG, deporte, música, inglés…) y mi energía cambia según la semana. Obsidian no me obliga a ser constante — me permite **retomar cualquier proyecto exactamente donde lo dejé** sin perder contexto.

- *Sin este sistema:* proyectos abandonados, ideas perdidas, sensación de no avanzar.
- *Con este sistema:* cada idea tiene su lugar, cada proyecto tiene su historia, todo se puede retomar.

---

## 2. ¿Qué hay en la bóveda?

La bóveda cubre cuatro tipos de contenido:

- **Proyectos académicos y profesionales** → núcleo del momento actual: el **TFG (Think&DoIT)**
- **Aprendizaje continuo** → inglés B2, conocimiento técnico (IA, agentes, programación), apuntes que nunca caducan.
- **Vida personal con disciplina** → entrenamientos (Kirola), bajo y música, cine, gestión semanal.
- **Sistema y procesos** → cómo funciona la propia bóveda. Este documento.

---

## 3. Cómo funciona el flujo

Todo lo que entra a la bóveda sigue **cuatro pasos**. No hace falta hacerlos todos el mismo día.

```
RECOPILAR → CURAR → ORDENAR → CLASIFICAR
```

**1. Recopilar** — Capturo sin filtro. Todo lo interesante entra al `Inbox.md`. No hay reglas aquí. Lo importante es no perder ideas por dudar dónde van.

**2. Curar** — En la revisión semanal del domingo, miro lo capturado y me quedo solo con lo que voy a usar. El resto se descarta o se archiva.

**3. Ordenar** — Si la nota merece la pena, la convierto en algo limpio y estructurado: con frontmatter, título claro, secciones.

**4. Clasificar** — Le pongo su tag de proyecto/área (color) y la muevo a su carpeta correcta. A partir de aquí ya está integrada.

---

## 4. Estructura de carpetas

```
📥 000_INBOX/             ← TODO lo nuevo entra aquí
🌱 00_JARDIN DIGITAL/     ← Ideas con nivel de madurez (Wikipedia personal)
🚀 01_PROJECTS/           ← Proyectos activos con resultado concreto
🌿 02_AREAS/              ← Responsabilidades continuas (deporte, música, inglés…)
📚 03_RESOURCES/          ← Material de referencia (cine, IA, técnico…)
📦 04_ARCHIVE/            ← Lo inactivo o cerrado
```

Más tres archivos en la raíz:
- **`Cómo usar este vault.md`** — este documento.
- **`Flujo de trabajo.md`** — guía del proceso día a día y semanal.
- **`CLAUDE.md`** — contexto del sistema para Claude Code (IA).

### 📥 000_INBOX — Captura rápida

Punto de entrada de todo. Estructura interna:

- `Inbox.md` — el archivo donde apunto las tareas y notas sueltas. **Una sola página**.
- `Dashboards/` — vistas globales que no tengo que mantener a mano:
  - `Tareas.md` — todas las tareas del vault, agrupadas por día y por proyecto.
  - `Plan Semanal.md` — qué hacer esta semana.
  - `Cine.md` — dashboard de películas con Dataview.
- `Plantillas/` — plantillas Templater organizadas por tema.
- `Adjuntos/` — imágenes y archivos que pego.

### 🌱 00_JARDIN DIGITAL — Conocimiento que crece

Donde viven las **ideas que evolucionan**. Cada nota tiene un nivel de madurez (ver §6):

```
01🌱 Semillas/   ← idea recién plantada
02🌿 Brotes/     ← idea en desarrollo
03🌳 Arboles/    ← conocimiento maduro y conectado
04❄️ Calma/      ← idea aparcada temporalmente
```

Cuando un tema acumula 3+ semillas, se agrupan en una **subcarpeta del tema**. Ejemplo: `01🌱 Semillas/Agentes IA/` con LLM, RAG, Embeddings, etc. Es el sistema de Maps of Content (MOC) — un hub por tema en lugar de jerarquías profundas.

### 🚀 01_PROJECTS — Proyectos activos

Cosas con **deadline o resultado concreto**. Ahora mismo:

- **Think and Do it/** — TFG. Subcarpetas: `📅 Sesiones/`, `📋 Reuniones/`, `📄 Documentos/`, `🔧 Tecnica/`, `Documentación Obsidian/`. La nota índice es `🗺️ ThinkAndDoIT — MOC.md`.
- **Rowing Fantasy/** — proyecto secundario con prioridad baja.

Cada proyecto tiene además su propia **nota de tareas filtrada** (ver §7):
- `Tareas TFG.md` — solo tareas con `#tfg`.
- `Tareas Rowing.md` — solo tareas con `#rowing`.

### 🌿 02_AREAS — Responsabilidades continuas

Lo que **no termina nunca** pero requiere atención:
- **Aprendizaje/** — inglés B2, gramática, listenings, writing.
- **BAJO/** — bajo eléctrico, teoría aplicada.
- **Kirola/** — entrenamientos, periodización, deporte.
- **Música/** — composición, canciones, ideas musicales.

### 📚 03_RESOURCES — Material de referencia

Conocimiento que **consulto, no produzco**:
- **Cine/** — sistema de películas, directores, actores.
- **IA/** — notas técnicas (OpenRouter, Claude Code, modelos…).
- **Obsidian/** — cómo se usa el propio Obsidian.
- **Diagramas/** — flujogramas del TFG.

### 📦 04_ARCHIVE — Histórico

Todo lo cerrado o inactivo. **No se borra, se archiva** — siempre puedo recuperar el contexto del pasado. Ejemplo: `2026-04 Tareas completadas.md`.

---

## 5. Sistema de colores

Aquí difiero del modelo "colores por tipo de nota" — yo uso **colores por proyecto/área en las tareas**. Cada tarea lleva una tag fija que la identifica visualmente:

| Tag | Categoría | Color |
|---|---|---|
| `#tfg` | Think&DoIT (TFG) | 🔵 Azul |
| `#rowing` | Rowing Fantasy | 🟣 Morado |
| `#ingles` | Aprendizaje / B2 | 🟢 Verde |
| `#musica` | Bajo / Música | 🟡 Amarillo |
| `#kirola` | Deporte | 🟠 Naranja |
| `#cine` | Cine / ocio | 🔴 Rojo |
| `#personal` | Casa, recados, otros | ⚪ Gris |

**Regla:** una sola tag por tarea. El snippet `task-colors.css` (en `.obsidian/snippets/`) pinta automáticamente el borde lateral de cada tarea con el color de su tag y convierte el `#tag` en una pastilla coloreada.

> Si quiero también colorear notas por **tipo** (concepto, guía, trabajo de clase…) podría añadirlo encima sin romper este sistema. De momento mantengo solo colores en tareas porque es donde más impacto visual aporta.

---

## 6. Niveles de madurez del Jardín Digital

Cada nota del jardín lleva un emoji que indica **cómo de desarrollada está**:

| Emoji | Estado | Significado |
|---|---|---|
| 🌱 | Semilla | Idea capturada, sin desarrollar. Recién salida del Inbox. |
| 🌿 | Brote | En proceso. Tiene contenido pero no está completa ni conectada. |
| 🌳 | Árbol | Conocimiento consolidado. Conectado con otras notas. Terminada. |
| ❄️ | Calma | Idea válida pero aparcada. La retomaré cuando sea momento. |

El emoji va en el **frontmatter** de la nota como campo `madurez`. Una idea puede subir niveles (semilla → brote → árbol) o aparcarse en calma. Lo importante es que **el sistema invita a cultivar** ideas, no a abandonarlas.

---

## 7. Frontmatter de las notas

El frontmatter es el bloque amarillo arriba de cada nota. Estandariza qué tipo de nota es y dónde encaja.

### Para notas del jardín digital

```yaml
---
fecha: 2026-04-30
madurez: 🌱
contexto: agentes-ia
tags:
  - jardin/semilla
---
```

### Para notas de proyecto

```yaml
---
fecha_inicio: 2026-01-15
estado: activo
tags:
  - tipo/proyecto
  - tfg
---
```

### Para notas de área (referencia continua)

```yaml
---
fecha: 2026-04-30
tags:
  - tipo/referencia
  - area/aprendizaje
---
```

### Para tareas

Las tareas **NO** son notas independientes — son líneas con checkbox dentro de cualquier nota. Sintaxis (plugin Tasks):

```
- [ ] Mandar correo a la tutora 📅 2026-05-02 ⏫ #tfg
```

Iconos:
- `📅` fecha límite · `⏳` programada · `🛫` empezar
- `⏫` alta · `🔼` media · `🔽` baja
- `🔁 every Sunday` · `🔁 every 2 weeks` — recurrente
- `#tag` — proyecto/área (ver §5)

---

## 8. Vistas globales y dashboards

El Inbox y los Dashboards son **lo único que abro a diario** para saber el estado del sistema.

### `Inbox.md`
El archivo donde **apunto sin pensar**. Las tareas migradas y la captura rápida. Tiene la tabla de tags arriba como recordatorio. NO se usa para mirar pendientes.

### `Dashboards/Tareas.md`
La vista principal. Contiene queries del plugin Tasks que muestran automáticamente:
- ⚠️ Hoy · 🔜 Mañana · 📅 Próximos 7 días · 🔥 Atrasadas
- 🗂️ Por proyecto/área (cada tag tiene su sección)
- 🆕 Sin fecha · 🎯 Prioridad alta · ✅ Completadas esta semana

### `Dashboards/Plan Semanal.md`
Plan concreto de la semana. Generado los lunes (a futuro, con un agente IA).

### Notas de proyecto con tareas filtradas
- `01_PROJECTS/Think and Do it/Tareas TFG.md`
- `01_PROJECTS/Rowing Fantasy/Tareas Rowing.md`

Cada una muestra solo las tareas de su proyecto. Útil cuando estoy concentrado en uno solo.

---

## 9. Ritual semanal — la única disciplina del sistema

Una vez por semana, **el domingo**, abro la bóveda con un único objetivo: **recuperar la visión global y vaciar el Inbox**. No es trabajo profundo, es orientación.

**Duración:** 15-20 minutos máximo.

El propio Inbox me avisa: aparece la tarea recurrente **"Revisión semanal del Inbox"**. Pasos:

1. **Abrir `Dashboards/Tareas.md`** *(3 min)*
   - Mirar **Atrasadas**: las refresco con fecha nueva o las hago ya.
   - Mirar **Completadas esta semana**: las que tengan valor histórico, las copio a `04_ARCHIVE/2026-MM Tareas completadas.md`.

2. **Vaciar `Inbox.md`** *(8 min)* — para cada tarea:
   - Si está completada → la borro.
   - Si es de un proyecto → la corto y pego en su nota de proyecto.
   - Si es de un área → la corto y pego en la nota del área.
   - Si ya no me importa → la borro.
   - Si le falta tag → le pongo el tag adecuado.

3. **Revisar 1-2 semillas del jardín** *(5 min)*
   - Las que tengan más energía esta semana, las desarrollo un poco o las conecto con otras notas.

4. **Marcar la "Revisión semanal" como `[x]`** *(1 min)*
   - El plugin Tasks crea automáticamente la del domingo siguiente.

Si un domingo no puedo, no pasa nada. **Lo grave es saltarse dos seguidos** — pierdo el contexto.

---

## 10. Plugins activos

| Plugin | Para qué |
|---|---|
| **Tasks** | Motor de tareas con queries y recurrencias (lo central) |
| **Templater** | Plantillas dinámicas (`<% tp.* %>`) |
| **Dataview** | Queries sobre frontmatter (dashboards de cine, semillas…) |
| **Calendar** | Vista de daily notes |
| **Kanban** | Tableros tipo Trello cuando los necesite |
| **QuickAdd** | Captura ultrarrápida con atajos |
| **Excalidraw** | Diagramas a mano |
| **Banners** | Cabeceras visuales en notas importantes |
| **Editing toolbar** | Barra de formato |
| **Icon folder** | Iconos en carpetas |
| **Style settings** | Ajustes del tema |
| **Obsidian Git** | Backup automático del vault |

**Plugins que NO uso:** TaskNotes (lo abandoné — convertía cada tarea en una nota entera; demasiada fricción).

---

## 11. ¿Y si quiero…?

### …añadir un proyecto nuevo
1. Creo carpeta en `01_PROJECTS/<nombre>/`.
2. Decido tag y color (`#nombre` → color hex).
3. Pido que actualicen el snippet `task-colors.css` con el color nuevo.
4. Añado sección al `Dashboards/Tareas.md`.
5. Creo `Tareas <nombre>.md` dentro del proyecto.

### …promocionar una semilla a brote
1. Cambio `madurez: 🌱` → `madurez: 🌿` en el frontmatter.
2. Cambio el tag `jardin/semilla` → `jardin/brote`.
3. Muevo el archivo de `01🌱 Semillas/` a `02🌿 Brotes/`.

### …archivar un proyecto cerrado
1. Muevo la carpeta entera de `01_PROJECTS/` a `04_ARCHIVE/`.
2. (Opcional) Actualizo `estado: activo` → `estado: terminado` en su nota MOC.

### …saltarme la revisión un domingo
Nada. Lo recojo el siguiente. Pero dos seguidos no.

### …explicárselo a alguien
Lee este documento de arriba abajo. Está pensado para eso.

---

## 12. Filosofía en una frase

> **Captura libre toda la semana → procesa todo el domingo → mira los dashboards a diario.**

Si entiendo eso, el resto es decoración.

---

## Notas relacionadas

- [[Casos prácticos]] — **manual operativo "qué hago cuando…"** (situaciones reales)
- [[Flujo de trabajo]] — la versión corta de §3, §5 y §9
- [[Inbox]] — punto de captura
- [[000_INBOX/Tareas]] — vista global
- [[Tareas TFG]] · [[Tareas Rowing]] — vistas por proyecto
- [[CLAUDE]] — contexto del vault para Claude Code
