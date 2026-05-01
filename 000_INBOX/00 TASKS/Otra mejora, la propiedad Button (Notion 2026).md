
Si por algún motivo no quieres usar rollups (ej. quieres distinguir "tocada en serio" vs "tocada de pasada"), puedes usar **Buttons**.

### Cómo

1. En **🎸 Songs**, añade una propiedad nueva:
    
    - Tipo: **Button**
    - Nombre: `🎯 Quick log`
2. Configurar acción:
    
    - **Edit pages**:
        - Set `Last practiced` to `Now`
        - Set `Times practiced` to `Times practiced + 1`
3. Resultado: cada canción tiene un botón. Le das un click y se actualiza. Pero **no registra una sesión** — es un atajo "marcar como practicada".
    

**Cuándo usar buttons en vez de rollups:** si solo tocas 1-2 canciones al día y no quieres molestarte con sesiones. Pero te pierdes los datos agregados (minutos por semana, etc.).

**Mi recomendación:** rollups. Sesiones siempre. Los datos son oro.

---

## 📊 Más sugerencias (las 7 que más valor te van a dar)

### 1. **Días sin practicar** — alarma visual

Añade una propiedad **Formula** llamada `Days since` con esta fórmula:

```
dateBetween(now(), prop("Last practiced"), "days")
```

Te muestra "5", "12", "47" días sin tocarla. La vista **🔥 Repasar** puedes filtrar por `Days since > 30`. Si añades formato condicional con CSS (en plantillas avanzadas) lo puedes pintar en rojo cuando pasa de 30. En Notion estándar, basta con ordenar por ese campo.

### 2. **Streak de días practicando** — gamificación

En la DB **Practice Sessions**, mira tu vista calendar. Configúrala para mostrar un punto por sesión. **Ver 5 días seguidos coloreados motiva más que cualquier app.**

Bonus: si quieres el contador exacto, una formula más compleja en una página separada cuenta días consecutivos. Pero el calendar visual ya hace el 80% del trabajo.

### 3. **Total minutos por semana / mes** — métrica de progreso

En **Practice Sessions**, añade una vista nueva tipo **Table**:

- Group by: `Date` → Group by week
- Calculate (al final de cada grupo): suma de `Duration (min)`

Ves: _"Esta semana: 145 min. Anterior: 90 min. Vas mejorando."_

### 4. **Goal del mes** — DB pequeña

Crea una DB ligera **🎯 Goals**:

- Name (Title): ej. "Aprender Master of Puppets entera"
- Month (Date)
- Songs (Relation → Songs)
- Status (Select: En curso / Conseguido / Aplazado)

Cada mes te marcas 1-2 objetivos concretos. Al final del mes los revisas.

### 5. **Daily note de práctica** — captura rápida adicional

A veces durante el día se te ocurren cosas: _"recordar trabajar el cambio de afinación rápido"_. En vez de meterlas en cualquier sitio, crea una DB **🧠 Practice notes**:

- Date (auto today)
- Tag (multi-select: técnica, repertorio, gear, teoría)
- Note (text)

Las pillas en 10 segundos. El domingo las revisas y mueves a la canción/teoría que toque.

### 6. **Gear** — qué guitarra/ampli usaste

DB ligera **🎸 Gear**:

- Name
- Type (Guitarra / Ampli / Pedal / Cable)
- Active (checkbox)

En Practice Sessions añade una relation a Gear. Después de 3 meses ves: _"Toco más con la Tele que con la Strato"_ o _"Cuando uso el ampli X, las sesiones son ⭐⭐⭐⭐ más a menudo"_.

Solo si te importa el equipo. Si tocas siempre lo mismo, salta esto.

### 7. **Vista "Próximo ensayo" — lista predecida**

Crea una vista de Songs llamada **🎯 Próximo ensayo**:

- Filter: `Days since > 7` AND `Status = Aprendiendo OR Mantener`
- Sort: `Days since` desc
- Limit: 5

Cuando te sientes a tocar y no sabes por dónde empezar, abres esa vista. Te dice **las 5 que más necesitan amor**. Eliges 2-3, las tocas, registras sesión.

Adiós a la decisión paralizante de "¿qué practico hoy?".