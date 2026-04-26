# Markdown completo

> Referencia completa de sintaxis Markdown para Obsidian.

## Encabezados
````markdown
# H1 — Título principal (uno por nota)
## H2 — Sección
### H3 — Subsección
#### H4 — Sub-subsección
````

## Énfasis
````markdown
**negrita**
*cursiva*
~~tachado~~
==resaltado==          ← exclusivo Obsidian
**_negrita y cursiva_**
````

## Listas

### Lista simple
````markdown
- item
- item
  - item anidado
  - item anidado
````

### Lista numerada
````markdown
1. Primero
2. Segundo
3. Tercero
````

### Lista de tareas
````markdown
- [ ] Tarea pendiente
- [x] Tarea completada
- [/] Tarea en progreso    ← Obsidian
- [-] Tarea cancelada      ← Obsidian
````

## Links

### Link interno
````markdown
[[Nombre de nota]]
[[Nombre de nota|texto visible]]
[[Nombre de nota#Sección]]
````

### Link externo
````markdown
[texto visible](https://url.com)
````

### Link a imagen externa
````markdown
![descripción](https://url-imagen.com)
````

### Imagen local
````markdown
![[imagen.png]]
![[imagen.png|300]]     ← con ancho fijo
````


## Citas
````markdown
> Esto es una cita
> puede ocupar varias líneas

> [!NOTE] Nota
> Callout de tipo nota

> [!WARNING] Aviso
> Callout de advertencia

> [!TIP] Consejo
> Callout de consejo

> [!IMPORTANT] Importante
> Callout importante
````

## Callouts (exclusivo Obsidian)
````markdown
> [!NOTE]
> [!TIP]
> [!IMPORTANT]
> [!WARNING]
> [!CAUTION]
> [!ABSTRACT]
> [!TODO]
> [!SUCCESS]
> [!QUESTION]
> [!FAILURE]
> [!BUG]
> [!EXAMPLE]
> [!QUOTE]
````

Versión colapsable:
````markdown
> [!NOTE]- Título colapsado
> Contenido oculto por defecto
````

## Código

### Inline
````markdown
`código inline`
````

### Bloque
````markdown
```javascript
const x = 1;
```

```python
print("hola")
```

```bash
git commit -m "mensaje"
```

```sql
SELECT * FROM notas
```
````

## Tablas
````markdown
| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| dato      | dato      | dato      |
| dato      | dato      | dato      |

| Izquierda | Centro | Derecha |
|:----------|:------:|--------:|
| texto     | texto  | texto   |
````

## Separadores
````markdown
---
***
___
````

## Footnotes
````markdown
Esto tiene una nota al pie.[^1]

[^1]: Contenido de la nota al pie.
````

## Matemáticas (LaTeX)
````markdown
Inline: $E = mc^2$

Bloque:
$$
\sum_{i=1}^{n} x_i = x_1 + x_2 + ... + x_n
$$
````

## Frontmatter YAML
````markdown
---
titulo: Mi nota
fecha: 2026-04-25
tags:
  - tipo/nota
  - area/trabajo
estado: activo
autor: Aitzol
---
````

## Embeds (exclusivo Obsidian)
````markdown
![[Otra nota]]                    ← embed de nota completa
![[Otra nota#Sección]]            ← embed de sección
![[Otra nota#^id-bloque]]         ← embed de bloque
````


## Comentarios (no se renderizan)
````markdown
%% Esto es un comentario %%

%%
Comentario
multilínea
%%
````

## Atajos útiles en el editor

| Atajo | Acción |
|-------|--------|
| `Ctrl+B` | Negrita |
| `Ctrl+I` | Cursiva |
| `Ctrl+K` | Link externo |
| `Ctrl+]` | Indentar |
| `Ctrl+[` | Desindentar |
| `Alt+↑/↓` | Mover línea arriba/abajo |
| `Ctrl+D` | Eliminar línea |

## Relacionado
- [[Conceptos clave]]
- [[01_Templater]]
- [[02_Dataview]]
- [[Callouts]]