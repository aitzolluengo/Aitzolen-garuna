
> Plugin para gestionar proyectos con tableros visuales
> de columnas y tarjetas dentro de Obsidian.

## Instalación

Settings → Community plugins → Browse Buscar: "Kanban" Install → Enable

## ¿Qué es un tablero Kanban?
Un tablero con columnas que representan estados.
Las tarjetas (tareas) se mueven entre columnas según avanzan.

Por hacer → En progreso → Revisión → Completado

## Crear un tablero

Ctrl+P → Kanban: Create new board

O click derecho en carpeta → New Kanban board.

Se crea un archivo `.md` especial con sintaxis Kanban.

## Estructura básica
```markdown
---
kanban-plugin: basic
---

## 📋 Por hacer

## 🔄 En progreso

## 👁️ Revisión

## ✅ Completado
```

## Operaciones básicas

### Añadir tarjeta
Click en `+` bajo cualquier columna.

### Mover tarjeta
Drag & drop entre columnas.

### Añadir fecha límite a tarjeta
Click en tarjeta → icono calendario → selecciona fecha.
Las tarjetas vencidas aparecen en rojo automáticamente.

### Archivar tarjetas completadas

Configuración del tablero → Archive completed cards
Las tarjetas completadas desaparecen del tablero pero quedan archivadas y consultables.

## Tablero por proyecto
Crea un Kanban por cada proyecto activo:

01_Projects/ ├── TFG - ThinkAndDoIt/ │ ├── TFG - Kanban.md ← tablero del proyecto │ └── notas del proyecto... ├── FCB - AppAlmacenes/ │ ├── FCB - Kanban.md │ └── ...

## Tablero semanal
Un tablero general para el día a día:

```markdown
---
kanban-plugin: basic
---

## 🗓️ Lunes

## 🗓️ Martes

## 🗓️ Miércoles

## 🗓️ Jueves

## 🗓️ Viernes

## 📥 Sin asignar

## ✅ Completado
```

## Tablero PARA
Vista general de todos tus proyectos:

```markdown
---
kanban-plugin: basic
---

## 🔴 Urgente

## 🟡 Esta semana

## 🟢 Este mes

## ⚪ Algún día

## ✅ Completado
```

## Configuración del tablero
Click en los tres puntos del tablero:

- Lane width: 270px
- Maximum card count per lane: sin límite
- Hide tags in card titles: OFF
- Link dates to daily notes: ON ← muy útil
- Archive completed cards: ON
**Link dates to daily notes:** las fechas en las tarjetas
se convierten en links a la Daily Note de ese día.

## Sintaxis markdown del tablero
El Kanban es un `.md` normal por debajo:

```markdown
## 📋 Por hacer

- [ ] Tarea sin fecha
- [ ] Tarea con fecha @{2026-04-30}
- [ ] Tarea con tag #urgente

## ✅ Completado

- [x] Tarea completada
```

Puedes editarlo en modo texto si prefieres.

## Buenas prácticas
- Un tablero por proyecto activo
- Máximo 5-7 tarjetas en "En progreso"
- Revisa el tablero en la revisión semanal
- Archiva completadas regularmente — el ruido visual mata la productividad
- Usa fechas límite solo para lo realmente importante

## Relacionado
- [[Sistema PARA]]
- [[Revisión semanal]]
- [[Daily Notes y Periodic Notes]]
- [[02_Dataview]]

