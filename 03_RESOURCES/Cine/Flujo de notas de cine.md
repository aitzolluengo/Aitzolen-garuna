# Flujo de trabajo — Cine

> Cómo registro y documento cada película que veo.

## Estructura de carpetas

03_Resources/Cine/ 
├── Dashboard Cine.md ← entrada principal 
├── Películas/ ← una nota por película 
├── Directores/ ← una nota por director 
├── Actores/ ← una nota por actor 
└── Listas/ 
└── Por ver.md

## Flujo completo

### 1. Quiero ver una película
1. `Ctrl+N` → nombre de la película
2. Guarda en `03_Resources/Cine/Películas/`
3. Aplica template `Película`
4. Rellena ficha básica (director, año, reparto)
5. Cambia tag a `cine/por-ver`

### 2. Acabo de verla
1. Abre la nota de la película
2. Cambia tag de `cine/por-ver` a `cine/vista`
3. Rellena **Mi registro** en caliente:
   - Cuándo y dónde
   - Primera reacción
   - La escena que no me puedo quitar
4. Añade el póster:
```markdown
   ![Póster](URL de Google Images)
```

### 3. Conecta con director y actores
Esto es lo que hace el Graph View interesante.

En la ficha de la película enlaza así:
```markdown
| Director | [[Tony Kaye]] |
| Reparto | [[Edward Norton]], [[Edward Furlong]] |
```

Si la nota del director no existe → créala:
1. Click en `[[Tony Kaye]]`
2. Aplica template `Director`
3. Rellena su filmografía vista y pendiente

### 4. Revisión profunda (opcional)
1-2 días después de ver la película:
1. Abre la nota
2. Rellena el resto del registro:
   - ¿De qué trata realmente?
   - Lo que me ha removido
   - ¿A quién se la recomendaría?
3. Conecta con otras películas relacionadas:
```markdown
   ## Relacionado
   - [[Romper Estereotipos]] → tema similar
   - [[Fight Club]] → Edward Norton
```

## Lo que verás en el Graph View
Con el tiempo el grafo te mostrará:

- **Clusters por director** → todas las pelis de Kubrick juntas
- **Clusters por actor** → todas las pelis de Norton conectadas
- **Conexiones inesperadas** → dos pelis de directores distintos
  conectadas por el mismo actor

## Buenas prácticas
- Escribe la primera reacción siempre en caliente — es la más honesta
- No fuerces el análisis profundo en todas — solo las que te marquen
- Enlaza siempre director y al menos 2-3 actores principales
- Si descubres un director nuevo → crea su nota aunque no hayas
  visto más pelis suyas — es una deuda de conocimiento

## Relacionado
- [[Dashboard Cine]]
- [[_Templates/Película]]
- [[_Templates/Director]]
- [[Cómo analizar una película]]