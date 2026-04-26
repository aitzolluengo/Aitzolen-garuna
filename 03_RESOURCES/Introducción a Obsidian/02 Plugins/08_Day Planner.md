
> Plugin para planificar el día en bloques de tiempo con vista de timeline y notificaciones. Se integra con Daily Notes y Tasks.

## Instalación
- Settings → Community plugins → 
- Browse Buscar: "Day Planner" 
- Install → Enable

⚠️ Hay dos versiones:
- **Day Planner** → versión nueva, más visual, integra Dataview
- **Day Planner OG** → versión clásica, más simple

**Recomendada: Day Planner** (la nueva)

## Requisitos
Necesita Dataview instalado y activado para funcionar. También necesita Daily Notes o Periodic Notes activado. 

## ¿Qué hace?
Añade dos vistas principales: Week Planner para planificar la semana con drag and drop, y Timeline para ver el día actual en curso con bloques de tiempo. Envía notificaciones cuando cambia el bloque activo. 

## Configuración
Settings → Day Planner

- Show now line: ON
- Show timeline in status bar: ON
- Notifications: ON
- Timeline zoom level: 2 (más compacto)

## Sintaxis en Daily Note
Los bloques de tiempo se escriben directamente en tu Daily Note:

```markdown
## Day Planner

- [ ] 09:00 - 09:30 Revisar tareas del día
- [ ] 09:30 - 11:00 Estudiar TFG
- [ ] 11:00 - 11:15 Descanso
- [ ] 11:15 - 13:00 Gym
- [ ] 14:00 - 15:00 Cine — ver película pendiente
- [ ] 15:00 - 17:00 Proyecto FCB
- [ ] 17:00 - 17:30 Revisión del día
```

## Vistas disponibles

### Timeline
Vista vertical del día con bloques de colores.
Ctrl+P → Day Planner: Show timeline

### Week Planner
Vista semanal con drag and drop.
Ctrl+P → Day Planner: Show week **planner**

## Integración con Tasks
Puedes ver tareas de todo el vault con fechas añadidas por el plugin Tasks directamente en el timeline. 

## Flujo de trabajo

### Cada mañana:
1. Abre Daily Note
2. Añade sección `## Day Planner`
3. Escribe tus bloques de tiempo
4. Abre Timeline → ves el día visual

### Durante el día:
- El bloque activo se resalta automáticamente
- La barra de estado muestra el tiempo restante
- Notificación cuando cambia el bloque

## Template — añadir a Daily Note
Actualiza `_Templates/Daily Note.md` con esta sección:

```markdown
## 🗓️ Day Planner

- [ ] 09:00 - 09:30 
- [ ] 09:30 - 11:00 
- [ ] 11:00 - 11:15 ☕ Descanso
- [ ] 11:15 - 13:00 
- [ ] 14:00 - 15:00 
- [ ] 15:00 - 17:00 
- [ ] 17:00 - 17:15 Revisión del día
```

## Buenas prácticas
- No planifiques cada minuto — deja huecos entre bloques
- Los bloques de 90 min son los más productivos
- Incluye descansos reales — 15 min cada 90 min
- Empieza con 3-4 bloques, no 10

## Relacionado
- [[Daily Notes y Periodic Notes]]
- [[Tasks]]
- [[Revisión semanal]]