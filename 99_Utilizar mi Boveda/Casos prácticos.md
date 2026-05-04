---
fecha: 2026-04-30
tags:
  - sistema
---

# 🎯 Casos prácticos — Qué hago cuando…

> Manual operativo del vault. Si me pasa **X**, voy a la sección y sigo los pasos. Está pensado para resolver situaciones reales del día a día.
>
> **Tip:** `Ctrl+F` y busca palabra clave (ej. "peli", "entrenamiento", "duda").

---

## Índice

1. [Capturas espontáneas](#1-capturas-espontáneas)
2. [Sesiones de trabajo profundo](#2-sesiones-de-trabajo-profundo)
3. [Documentar lo hecho](#3-documentar-lo-hecho)
4. [Reflexiones y aprendizaje](#4-reflexiones-y-aprendizaje)
5. [Gestión de proyectos](#5-gestión-de-proyectos)
6. [Mantenimiento del sistema](#6-mantenimiento-del-sistema)
7. [Casos de duda](#7-casos-de-duda)
8. [Situaciones del entorno](#8-situaciones-del-entorno)
9. [Casos que rompen el flujo](#9-casos-que-rompen-el-flujo)

---

## 1. Capturas espontáneas

> **Regla:** capturar es libre. Si dudas, va a Inbox. **Nunca te bloquees clasificando.**

### 💡 Se me ocurre una idea (en cualquier momento)
1. Abro `Inbox.md`.
2. Sección **Captura rápida** → escribo `- [ ] idea + tag`.
3. Cierro y sigo.

> Ejemplo: `- [ ] Probar prompt nuevo de RAG en mis notas #tfg`

### 📱 Estoy fuera de casa y se me ocurre algo
1. Abro **Obsidian en el móvil** → Inbox.md.
2. Lo apunto igual: `- [ ] cosa #tag`.
3. Si voy con prisa: ni siquiera tag. Lo pongo el domingo en la revisión.

### 📲 Me llega un mensaje (WhatsApp, email) que tengo que recordar
1. Voy al `Inbox.md`.
2. `- [ ] Llamar a Antonio el sábado 📅 2026-05-04 #personal`
3. (Opcional) Si el mensaje tiene info útil, copio el texto entero a una nota nueva en `000_INBOX/` y desde ahí enlazo: `→ ver [[Mensaje Antonio sábado]]`.

### 📺 Veo un vídeo / artículo / paper interesante
- **Si lo voy a usar pronto:** `- [ ] Ver vídeo Karpathy LLMs 📅 2026-05-03 🔼 #personal` con la URL en la línea.
- **Si es referencia futura:** lo guardo directamente en `03_RESOURCES/<tema>/` como nota con URL + 2-3 líneas de "por qué me interesa".

### ❓ Tengo una pregunta para alguien
1. Inbox: `- [ ] Preguntar a tutor sobre arquitectura del chat 📅 próxima reunión #tfg`
2. Si son varias preguntas para la misma persona, las agrupo en una nota: `📋 Reuniones/2026-05-XX — Bilera tutorearekin.md`.

### 🛒 Necesito comprar algo / hacer un recado
- `- [ ] Cuerdas para el bajo #musica`
- `- [ ] Foto Antonio (sábado abre?) #personal`

---

## 2. Sesiones de trabajo profundo

> Cuando me siento **a producir**. Aquí no capturo — ejecuto.

### 🚀 Empiezo sesión de TFG
1. Abro `01_PROJECTS/Think and Do it/🗺️ ThinkAndDoIT — MOC.md` para ver dónde estoy.
2. Abro `Tareas TFG.md` → miro la sección **Hoy** y elijo qué hago.
3. Creo nota nueva en `📅 Sesiones/YYYY-MM-DD — <tema>.md` y voy apuntando lo que hago.
4. Si me surge una duda, la pongo `- [ ] duda X #tfg` en la propia sesión (no me voy al Inbox).

### 🇬🇧 Voy a estudiar inglés
1. Abro `02_AREAS/Aprendizaje/Ingles B2 - MOC.md`.
2. Decido tipo: gramática (notas de B2), listening, writing, reading.
3. Si es **gramática**: abro la nota correspondiente, leo, marco lo que reviso.
4. Si es **listening**: creo nota `02_AREAS/Aprendizaje/Listenings/YYYY-MM-DD — <tema>.md` con vocabulario nuevo.
5. Si es **writing**: creo nota `02_AREAS/Aprendizaje/Writings/YYYY-MM-DD — <tipo>.md` con el texto y autocrítica al final.

### 🏋️ Voy a entrenar
1. Abro plantilla `Plantillas/Entrenamiento/Entrenamiento Fuerza.md` (o Running).
2. Templater me crea la nota con fecha en `02_AREAS/Kirola/`.
3. Apunto series, RPE, sensaciones.
4. Al acabar, marco `- [ ] Entrenar #kirola` como `[x]` si la tenía.

### 🎸 Voy a tocar el bajo
1. Abro `02_AREAS/BAJO/` o crea nota nueva si voy a aprender un tema concreto.
2. Plantilla `Plantillas/Areas/Música/Canción.md` si trabajo una canción.

### 🎬 Voy a ver una peli
1. Buscador (`Ctrl+O`) → escribo el título.
2. Si **existe**: abro la nota.
3. Si **no existe**: la creo en `03_RESOURCES/Cine/Películas/<título>.md` con la plantilla `Plantillas/Cine/Película.md`.
4. Después de verla: actualizo `puntuacion`, `tags: [cine/vista]`, comentario corto.

---

## 3. Documentar lo hecho

> Capturar **el resultado** de algo que ya pasó. La mitad del valor del vault está aquí.

### ✅ Acabo una sesión de TFG
- En la nota `📅 Sesiones/YYYY-MM-DD — X.md`:
  - **Lo que hemos hecho hoy** (lista corta)
  - **Bloqueadores** si los hay
  - **Siguiente paso** (1 línea)
- Si surgieron tareas pendientes, las muevo al `Tareas TFG.md`.

### 🏁 Acabo un entrenamiento
- Relleno la nota: peso real, RPE real, sensaciones.
- Si descubro algo (ej. "me dolió el lumbar al final") → al final de la nota: `- [ ] Revisar técnica peso muerto con vídeo #kirola`.

### 🎬 He visto una peli
- Voy a la nota de la peli en `03_RESOURCES/Cine/Películas/<título>.md`.
- Pongo `puntuacion: X/5`, cambio tag a `cine/vista`, escribo 3-5 líneas.
- Si es de un director que aún no tengo: creo nota `03_RESOURCES/Cine/Directores/<nombre>.md` y enlazo.

### 📚 Termino de leer un libro / artículo
- Si tiene **valor de referencia**: nota en `03_RESOURCES/Libros/<título>.md` con resumen, ideas clave, citas.
- Si tiene **valor de idea para algo mío**: extrae la idea como **semilla** en `00_JARDIN DIGITAL/01🌱 Semillas/`.

### 🤝 Acabo una reunión (con tutor, profe, etc.)
- Nota en `📋 Reuniones/YYYY-MM-DD — <tema>.md`:
  - Quién, cuándo, duración
  - **Decisiones**
  - **Tareas resultantes** → cada una como `- [ ] cosa 📅 fecha #tfg`
  - Apuntes del flujo de la conversación

---

## 4. Reflexiones y aprendizaje

> Las que cultivan el **Jardín Digital**. Lo que aprendo, no lo que hago.

### 🧠 Aprendo algo nuevo (un concepto técnico)
1. ¿Es algo que voy a usar **muchas veces**? → semilla en `00_JARDIN DIGITAL/01🌱 Semillas/<tema>/<concepto>.md`.
2. ¿Es **muy específico** de un proyecto? → nota dentro del proyecto, no en jardín.

> Ejemplo: aprendo qué es un *embedding* → semilla en `01🌱 Semillas/Agentes IA/Embeddings.md`. Aprendo cómo configurar `pom.xml` del TFG → nota dentro de `01_PROJECTS/Think and Do it/🔧 Tecnica/`.

### 🛠️ Descubro una herramienta nueva
1. Si la voy a probar pronto → tarea `- [ ] Probar X #personal` o `#tfg`.
2. Si es referencia → nota en `03_RESOURCES/<tema>/<herramienta>.md` con: qué es, por qué me interesa, link.

### 💭 Quiero apuntar una opinión / reflexión
- Si es genérica → semilla en jardín con `contexto: personal`.
- Si es sobre un tema concreto del jardín → la añado dentro de la semilla/brote correspondiente como sección "Mi opinión".

### 🌱 → 🌿 Una semilla ya tiene cuerpo (la he ampliado, conectado)
1. Cambio `madurez: 🌱` → `madurez: 🌿` en frontmatter.
2. Cambio tag `jardin/semilla` → `jardin/brote`.
3. Muevo de `01🌱 Semillas/` a `02🌿 Brotes/`.

### 🌿 → 🌳 Un brote ya está terminado (consolidado, conectado)
1. Frontmatter `madurez: 🌳`, tag `jardin/arbol`.
2. Muevo a `03🌳 Arboles/`.
3. Reviso que tenga **al menos 3 enlaces internos** (eso lo hace evergreen).

### ❄️ Una idea me llama pero NO es momento
1. Frontmatter `madurez: ❄️`, tag `jardin/calma`.
2. Muevo a `04❄️ Calma/`.
3. Sección final "Revisar cuando…" con condición concreta para reactivarla.

---

## 5. Gestión de proyectos

### 🚀 Empieza un proyecto nuevo
1. Creo carpeta `01_PROJECTS/<nombre>/`.
2. Decido **tag y color** (ej. `#nuevoproy` → naranja oscuro).
3. Pido que actualicen `task-colors.css` (al asistente o yo a mano).
4. Creo `01_PROJECTS/<nombre>/<nombre> — MOC.md` con: objetivo, deadline, hitos, recursos.
5. Creo `Tareas <nombre>.md` con queries del plugin Tasks filtrando por la nueva tag.
6. Añado sección al `Dashboards/Tareas.md`.

### 📅 Tengo una reunión planificada
1. Creo nota `📋 Reuniones/YYYY-MM-DD — <tema>.md` **antes** de la reunión.
2. Anoto orden del día (qué quiero tratar).
3. Durante: tomo apuntes en la misma nota.
4. Después: marco las tareas resultantes con `#tfg` (o tag del proyecto).

### 📤 Mando un entregable / email importante
1. Tarea: `- [ ] Mandar punto X 📅 deadline ⏫ #tfg`.
2. Cuando lo mando → marco `[x]`.
3. Si el correo es relevante (decisiones, fecha hito), lo copio textualmente en `📋 Reuniones/YYYY-MM-DD — <asunto>.md`.

### 🛑 Un proyecto se cancela / pausa
- **Pausa temporal:** cambio frontmatter `estado: activo` → `estado: pausado`. La carpeta se queda en `01_PROJECTS/`.
- **Cancelado / cerrado:** muevo carpeta entera a `04_ARCHIVE/`. Cambio `estado: terminado`.

---

## 6. Mantenimiento del sistema

### 🌅 Domingo — ritual semanal (15-20 min)
Ya está protocolizado. Ver `Cómo usar este vault.md` §9 o `Flujo de trabajo.md` §3.

Resumen rápido:
1. Abro `Dashboards/Tareas.md` → atrasadas + completadas.
2. Vacío `Inbox.md` línea por línea.
3. Reviso 1-2 semillas del jardín.
4. Marco la "Revisión semanal" como `[x]`.

### 🎨 Quiero cambiar un color de tag
1. Abro `.obsidian/snippets/task-colors.css`.
2. Cambio el valor hex de la variable `--task-<tag>`.
3. Guardo. Obsidian recarga solo.

### ➕ Quiero añadir una etiqueta nueva con su color
1. Decido tag y color hex.
2. Añado la línea en `task-colors.css` (4 lugares: variable, borde modo lectura, borde plugin Tasks, chip).
3. Añado sección al `Dashboards/Tareas.md`.
4. Documento en `Cómo usar este vault.md` §5.

### 📁 Mover muchas notas a la vez
- **Manualmente** desde el explorador de Obsidian (drag & drop) — actualiza wikilinks solo.
- **Nunca** con explorador de Windows — rompe enlaces.

### 💾 Backup
- Plugin **Obsidian Git** está activo → cada cambio se commitea automáticamente al repo.
- Comprueba ocasionalmente: `git status` desde la raíz del vault.

---

## 7. Casos de duda

### 🤷 No sé si esto es proyecto, área o recurso
Pregunta esto en orden:
1. ¿Tiene **deadline** o resultado concreto que terminar? → **proyecto** (`01_PROJECTS/`).
2. ¿Es **continuo** (no termina nunca)? → **área** (`02_AREAS/`).
3. ¿Es **conocimiento de consulta** (no lo produzco yo)? → **recurso** (`03_RESOURCES/`).
4. ¿No lo sé? → **Inbox**. El domingo lo decides.

### 🤔 Esta nota podría ir en dos sitios
**Una sola ubicación, varios links.** La pongo donde más se va a usar y desde el otro sitio enlazo: `Ver [[Nota X]]`.

> Ejemplo: "Cómo configurar Ollama" → va a `03_RESOURCES/IA/Ollama.md` y desde la semilla `Smart connections con Ollama` enlazo.

### 🏷️ Esta tarea no encaja en ninguna tag
Usa `#personal`. Si aparecen muchas con `#personal`, es señal de que necesitas crear una tag nueva (ej. `#casa`, `#salud`).

### 🚫 Olvidé poner tag a varias tareas
Tranquilo. En `Dashboards/Tareas.md` hay sección **❓ Sin etiqueta**. El domingo procesas esa lista.

### ⏳ Llevo dos semanas sin revisar el Inbox
1. Calma. No empieces a procesar todo.
2. Filtra por **lo más urgente** (atrasadas con prioridad alta).
3. Lo demás: o lo borras o le pones fecha nueva.
4. La próxima semana retomas el ritual.

### 🔍 No recuerdo dónde guardé algo
1. `Ctrl+O` → buscar por título.
2. Si no recuerdo el título: `Ctrl+Shift+F` → buscar por contenido.
3. Si tampoco: **Graph view** → si el tema tiene su MOC, veo el cluster y reconozco la nota.

### 📛 He creado una nota duplicada por accidente
1. Mantengo la más completa.
2. Copio cualquier contenido único de la otra.
3. Reemplazo enlaces que apunten a la duplicada (Obsidian te dice cuántos hay).
4. Borro la duplicada.

---

## 8. Situaciones del entorno

### 📵 Estoy sin internet
- Obsidian funciona **100% offline**. Notas locales.
- Lo único que NO va: Smart Connections, plugins que llamen a APIs externas, push de Git.
- Cuando vuelva la conexión, Git sincroniza solo.

### 📱 Estoy en clase / en un bus / en cualquier sitio incómodo
- App de Obsidian en el móvil.
- Vista **Inbox.md** y captura rápida.
- No intentes nada más complejo desde el móvil — apunta y procesa después en el ordenador.

### ✏️ Necesito apuntar algo MUY rápido (5 segundos)
- En el móvil: widget de Obsidian o atajo a Inbox.md.
- En el ordenador: `Ctrl+P` → "QuickAdd: capture" (si tienes QuickAdd configurado).
- Si tampoco: notas del móvil / WhatsApp a ti mismo. **Lo metes en Inbox cuando llegues a casa.**

### 👥 Quiero compartir una nota con alguien
- **Cómo PDF:** abre nota → `Ctrl+P` → "Export to PDF".
- **Como Markdown plano:** copia y pega contenido en email/WhatsApp.
- **NUNCA** des acceso al vault completo — tiene cosas privadas.

### 🔁 Quiero usar el vault en otro ordenador
- Plugin **Obsidian Git** ya hace push/pull. En el otro ordenador:
  1. `git clone <url-repo>`
  2. Abrir carpeta como vault en Obsidian.
- O alternativa: Obsidian Sync (de pago).

---

## 9. Casos que rompen el flujo

### 🔥 Un proyecto explota — todas las tareas son urgentes
1. NO me dejo arrastrar a procesar todas.
2. Abro `Tareas <proyecto>.md` y elijo **las 3 más críticas**.
3. Pospongo lo demás con fechas nuevas.
4. Comunico al stakeholder (tutor, persona) que reorganizo plazos.

### 😴 Estoy quemado y no quiero abrir Obsidian
- **No pasa nada.** El vault aguanta semanas sin que lo toques.
- Cuando vuelvas: abre solo `Inbox.md`. Mira si hay algo crítico (📅 vencido + ⏫). Lo demás lo procesas otro día.

### 🎯 He perdido la motivación con un proyecto
1. Lo paso a `estado: pausado` (no lo elimino).
2. En su MOC, escribo en una sección "Por qué pausé": qué pasó, cuándo retomar, condición.
3. Me centro en otro proyecto. **El sistema no te juzga.**

### 💡 Tengo una idea de proyecto nuevo y me obsesiono
- Aterrízala como **semilla** en jardín, no como proyecto.
- Espera 1-2 semanas. Si sigue allí en mi cabeza, **entonces** la promociono a proyecto.
- Esto evita arrancar 5 proyectos a la vez y abandonarlos todos.

### 🧹 El sistema me parece complicado y quiero simplificar
1. Para empezar: olvídate de TODO menos `Inbox.md` + `Dashboards/Tareas.md`.
2. Captura allí, mira allí. Las demás carpetas existen pero no las uses.
3. Cuando recuperes ritmo, vuelves a usar el resto.

### 🙅 Una funcionalidad del vault me molesta
- Lo desactivo (plugin off, snippet off).
- Si afecta a algo crítico, antes pregunto / busco.
- **Nunca** edito carpetas con explorador del SO — siempre desde Obsidian.

---

## TL;DR — Si solo me acuerdo de una cosa

> **Cuando dudes, va al Inbox. El domingo lo procesas.**

Eso resuelve el 80% de las situaciones.

---

## Notas relacionadas

- [[Cómo usar este vault]] — manual completo del sistema
- [[Flujo de trabajo]] — proceso de tareas y revisión
- [[Inbox]] — punto de captura
- [[000_INBOX/Tareas]] — vista global
- [[CLAUDE]] — contexto del vault para Claude Code
