# Revisión semanal

> El ritual que mantiene vivo el segundo cerebro.
> Sin revisión semanal, el sistema colapsa en semanas.

## ¿Por qué es crítica?

Capturar sin revisar es acumular basura organizada.
La revisión es el momento donde:
- El inbox se vacía
- Las notas se conectan
- Los proyectos avanzan
- El sistema sigue siendo de confianza

**Sin confianza en el sistema, dejas de usarlo.**

## Cuándo

- Mismo día cada semana (domingo noche o lunes mañana)
- Duración: 20-30 minutos
- No más — si tarda más, el sistema tiene demasiado ruido

## El ritual completo

### 1. Vaciar Inbox (5 min)
Abre `00_Inbox` y para cada nota pregúntate:

- ¿Es accionable? SÍ → ¿Es un proyecto? → 01_Projects 
- ¿Es referencia? → 03_Resources 
- ¿Es área? → 02_Areas NO → ¿Tiene valor futuro? → 03_Resources NO → 04_Archive o borrar

Objetivo: **Inbox = 0** al terminar.

### 2. Revisar proyectos activos (10 min)
Abre cada carpeta de `01_Projects` y comprueba:

- [x]  ¿Hay tareas pendientes sin asignar?
- [x]  ¿Hay algo bloqueado?
- [x]  ¿Algún proyecto ha terminado? → mover a Archive
- [x]  ¿Falta algún proyecto nuevo? → crear nota
### 3. Revisar Dashboard (5 min)

Abre `Dashboard.md` y comprueba:

- [x]  Tareas pendientes sin completar
- [x]  Notas en Inbox que quedaron sin procesar
- [x]  Proyectos activos al sdía
### 4. Mantenimiento del grafo (5 min)
Abre Graph View (`Ctrl+G`) y busca:
- Nodos aislados → notas sin links → conectar o archivar
- Clusters nuevos → ¿merece un MOC?
- Notas huérfanas → revisar si tienen valor

### 5. Captura de reflexión semanal (5 min)
Crea una nota en `02_Areas` o Daily Note con:

```markdown
## Semana {{fecha}}

### ¿Qué fue bien?

### ¿Qué mejorar?

### ¿Qué aprendí?

### Foco de la semana que viene
```

## Checklist completa
Pega esto en tu nota de revisión semanal:

```markdown
## Revisión semanal - {{fecha}}

### Inbox
- [ ] Inbox vaciado completamente

### Proyectos
- [ ] Revisados todos los proyectos activos
- [ ] Proyectos terminados archivados
- [ ] Nuevos proyectos creados si hace falta

### Dashboard
- [ ] Tareas pendientes revisadas
- [ ] Dashboard actualizado

### Grafo
- [ ] Nodos aislados conectados o archivados

### Reflexión
- [ ] Nota de reflexión semanal escrita
```

## Señales de que el sistema funciona
- El inbox llega a 0 cada semana
- Sabes exactamente en qué proyectos estás
- Encuentras notas antiguas relevantes por links
- El grafo crece con sentido

## Señales de que algo falla
- Inbox con más de 20 notas
- Notas duplicadas sobre el mismo tema
- No recuerdas qué hay en `03_Resources`
- Evitas abrir Obsidian

## Relacionado
- [[Sistema PARA]]
- [[Captura rápida]]
- [[Dashboard]]
- [[Graph View]]