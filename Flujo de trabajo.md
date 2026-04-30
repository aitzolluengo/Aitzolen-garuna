---
fecha: 2026-04-30
tags:
  - sistema
---

#  Flujo de trabajo
Como quiero funcionar en mi bóveda es lo principal que tengo que entender. Si a veces no se que hacer , abro esta nota.

> **La regla de oro:** capturar es libre y diario. **Procesar es solo el domingo.**

---

## 1. Día a día 

Para apuntar tareas cotidianas, ideas varias o apuntes que tengo que hacer, abro el archivo [[Inbox]] y escribo de la siguiente manera


```
- [ ] Llamar a X 📅 2026-05-02
- [ ] Comprar cuerdas para el bajo
- [ ] Mirar vídeo de X 🔼
```

 No pienso dónde va ni tampoco si hay que documentar. Solo apunto.

### Para ver tareas pendientes

NO uso `Inbox.md` para ver lo que tengo que hacer. Para eso abro [[Dashboards/Tareas]], que muestra **todas** las tareas de **todo el vault** ordenadas por:
- Hoy
- Esta semana
- Atrasadas
- Sin fecha
- Prioridad alta
- Completadas esta semana

---

## 2. Sintaxis de Tasks

Las tareas se crean de la siguiente forma:  `- [ ]` 
Para apuntar importancia y fecha se utiliza como la siguiente tabla:

| Símbolo | Significado | Ejemplo |
|---|---|---|
| `📅` | Fecha límite | `📅 2026-05-02` |
| `⏳` | Programada | `⏳ 2026-05-01` |
| `🛫` | Empezar | `🛫 2026-05-01` |
| `⏫` | Prioridad alta | |
| `🔼` | Prioridad media | |
| `🔽` | Prioridad baja | |
| `🔁` | Recurrente | `🔁 every Sunday` · `🔁 every 2 weeks` · `🔁 every month` |
| `#tag` | Etiqueta de proyecto/área (ver siguiente sección) | |

Ejemplo completo:

```
- [ ] Mandar correo a la tutora 📅 2026-05-02 ⏫ #tfg
- [ ] Revisión semanal del Inbox 🔁 every Sunday 📅 2026-05-03 #personal
```

### 2.1 Sistema de tags por proyecto/área (con colores)

Cada tarea lleva **una tag fija** según a qué pertenece. El snippet CSS `task-colors.css` pinta el borde lateral con su color y el chip del tag con fondo de color. Activa el snippet en *Settings → Appearance → CSS snippets*.

| Tag | Categoría | Color |
|---|---|---|
| `#tfg` | Think&DoIT (TFG) | 🔵 Azul |
| `#rowing` | Rowing Fantasy | 🟣 Morado |
| `#ingles` | Aprendizaje / B2 | 🟢 Verde |
| `#musica` | Bajo / Música | 🟡 Amarillo |
| `#kirola` | Deporte | 🟠 Naranja |
| `#cine` | Cine / ocio | 🔴 Rojo |
| `#personal` | Casa, recados, otros | ⚪ Gris |

**Regla:** una sola tag por tarea. Si dudas, elige la del *output* (qué área genera valor al hacerla). Si una tarea no encaja en ninguna, usa `#personal`.

Para ver tareas filtradas por proyecto, abre la nota del proyecto:
- [[Tareas TFG]] — solo tareas con `#tfg`
- [[Tareas Rowing]] — solo tareas con `#rowing`

Para verlas todas agrupadas por proyecto, abre [[Dashboards/Tareas]].

---

## 3. Domingo — la única vez que toca repasar

El propio Inbox me avisa: aparece la tarea **Revisión semanal**. Cuando llegue ese domingo, sigo estos pasos en orden.

### Paso 1 · Abro `Dashboards/Tareas.md`

- **Atrasadas** → ¿qué se me pasó? Lo refresco con fecha nueva o lo hago ya.
- **Completadas esta semana** → repaso lo que hice (borrar o posible archivo histórico).

### Paso 2 · Abro `Inbox.md` y proceso línea por línea

Por cada tarea, **una de estas 4 acciones**:

| Estado de la tarea | Acción |
|---|---|
| `- [x]` Completada | **Borrar la línea** (o copiar a `04_ARCHIVE/2026-MM Tareas completadas.md` si tiene valor histórico) |
| Pendiente y es de un proyecto | **Cortar y pegar** en la nota correspondiente de `01_PROJECTS/` |
| Pendiente y es de un área | **Cortar y pegar** en la nota correspondiente de `02_AREAS/` |
| Ya no me importa | **Borrar** |

Al terminar, `Inbox.md` queda casi vacío. Solo queda la captura fresca de la semana siguiente.

### Paso 3 · Marco la "Revisión semanal" como `[x]`

El plugin Tasks crea automáticamente la siguiente para el domingo siguiente.

---

## 4. ¿Y dónde va cada cosa cuando proceso?

| Tipo de cosa | Carpeta destino |
|---|---|
| 💡 Idea sin desarrollar | `00_JARDIN DIGITAL/01🌱 Semillas/` (con subcarpeta de tema si hay 3+) |
| 🌿 Idea en desarrollo | `00_JARDIN DIGITAL/02🌿 Brotes/` |
| 🌳 Conocimiento maduro | `00_JARDIN DIGITAL/03🌳 Arboles/` |
| ❄️ Idea aparcada | `00_JARDIN DIGITAL/04❄️ Calma/` |
| 🚀 Proyecto activo (con resultado concreto) | `01_PROJECTS/` |
| 🔁 Responsabilidad continua | `02_AREAS/` |
| 📖 Conocimiento de referencia | `03_RESOURCES/` |
| 🎬 Película | `03_RESOURCES/Cine/Películas/` |
| 🎤 Director / Actor | `03_RESOURCES/Cine/{Directores,Actores}/` |
| 🤖 Tema técnico de IA | `03_RESOURCES/IA/` |
| 🗄️ Material inactivo | `04_ARCHIVE/` |

**Si dudo → Inbox. Siempre.** Lo procesaré el domingo.

---

## 5. Casos especiales

### Tarea recurrente
Marcar `🔁 every X` y al completar, el plugin crea la siguiente automáticamente. No hay que tocarla a mano.

Ejemplos: `🔁 every Sunday`, `🔁 every 2 weeks`, `🔁 every month on the 1st`.

### Tarea con contexto largo
Si no es una línea sino un texto con apuntes, no es tarea — es **nota** con un checkbox dentro:

```markdown
# Listening 29 abril

Notas mientras escucho el podcast XYZ:
- ...

- [ ] Repasar lo apuntado mañana 📅 2026-04-30
```

La nota va a `02_AREAS/Aprendizaje/`. La tarea `- [ ]` aparece igualmente en el [[Dashboards/Tareas]] gracias al plugin Tasks.

### Tarea recurrente diaria que solo aplica un día
Mejor sin recurrencia. Las recurrencias son para cosas estables.

### Salto la revisión un domingo
No pasa nada. Al siguiente recojo lo de las dos semanas. Lo grave es pasar de **dos** semanas — entonces pierdo contexto de qué era importante.

---

## Relacionado

- [[Inbox]] — punto de captura
- [[Dashboards/Tareas]] — vista global de tareas
- [[Dashboards/Plan Semanal]] — qué hacer esta semana
- [[CLAUDE]] — contexto para la IA
