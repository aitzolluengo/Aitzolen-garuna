
> Sistema de etiquetado para clasificar y filtrar notas de forma transversal a las carpetas.

## ¿Qué es un Tag?
Una etiqueta que puedes añadir a cualquier nota.  Se escribe con `#` delante.

## Diferencia entre Tags y Links

|          | Tags                         | Links                  |
| -------- | ---------------------------- | ---------------------- |
| Para qué | Clasificar por estado o tipo | Conectar por contenido |
| Ejemplo  | `#pendiente`                 | `[[Tarea]]`            |
| Relación | Nota → categoría             | Nota ↔ nota            |
| Navegar  | Panel de tags                | Click directo          |

**Regla práctica:**
- Usa **links** para conectar conceptos y conocimiento
- Usa **tags** para marcar estado, tipo o contexto

## Tipos de tags que funcionan

### Por estado

#estado/borrador 
#estado/revisando  
#estado/completado

### Por tipo de nota

#tipo/idea #tipo/proyecto #tipo/referencia #tipo/reflexion

### Por área

#area/trabajo #area/personal #area/aprendizaje

### Tags de acción

#pendiente #revisar #archivar

## Tags anidados

Obsidian soporta jerarquía con `/`:

#trabajo/oracle #trabajo/iese #trabajo/fcb

En el panel de tags aparecen agrupados bajo `trabajo`.

## Cómo ver todos tus tags
- Panel derecho → **Tags pane**
- Muestra todos los tags con contador de notas
- Click en un tag → filtra todas las notas con ese tag

## Frontmatter (la forma pro)
En lugar de poner tags en el cuerpo de la nota, 
ponlos en el **frontmatter** — bloque YAML al inicio:

```yaml
---
tags:
  - tipo/referencia
  - area/aprendizaje
  - obsidian
fecha: 2026-04-25
---
```

Ventajas:
- Dataview puede consultarlos como base de datos
- No ensucian el contenido de la nota
- Más fácil de mantener

## Buenas prácticas
- Pocos tags, consistentes — mejor 10 bien usados que 50 caóticos
- Usa siempre la misma nomenclatura (`#pendiente` no `#Pendiente`)
- Tags para lo que no tiene nota propia — si merece nota, usa link
- Revisa tus tags cada mes y limpia los que no uses

## Relacionado
- [[Links y Backlinks]]
- [[Graph View]]
- [[02_Dataview]]