# ¿Para qué sirve?

> Plugin para crear diagramas, mapas mentales y bocetos
> directamente dentro de Obsidian.

## Instalación

- Settings → Community plugins → Browse 
- Buscar: "Excalidraw" 
- Install → Enable
## ¿Qué es?

Excalidraw es una herramienta de dibujo vectorial con
estilo de boceto a mano. Dentro de Obsidian los diagramas
viven como archivos `.excalidraw` en tu vault.

## Crear un diagrama

Ctrl+P → Excalidraw: Create new drawing

O click derecho en carpeta → New Excalidraw drawing.

## Interfaz básica

### Herramientas
| Herramienta | Atajo | Para qué |
|-------------|-------|----------|
| Selección | `S` | Seleccionar y mover |
| Rectángulo | `R` | Cajas |
| Elipse | `E` | Círculos |
| Flecha | `A` | Conexiones |
| Línea | `L` | Líneas simples |
| Texto | `T` | Añadir texto |
| Lápiz | `P` | Dibujo libre |

### Navegación
| Atajo | Acción |
|-------|--------|
| `Ctrl+Scroll` | Zoom |
| `Space+drag` | Mover canvas |
| `Ctrl+A` | Seleccionar todo |
| `Ctrl+Z` | Deshacer |
| `Ctrl+D` | Duplicar |

## Editar como markdown
Si el diagrama no se ve bien o quieres pegarlo desde fuera:

Tres puntos ⋮ → Edit as markdown

Pegas el contenido y guardas con `Ctrl+S`.

## Embeds en notas
Incrustar un diagrama dentro de cualquier nota:
```markdown
![[nombre-diagrama.excalidraw]]
![[nombre-diagrama.excalidraw|600]]   ← con ancho fijo
```

## Organización recomendada

03_Resources/ 
		└── _Diagramas/ 
					├── Flujo PARA.excalidraw 
					└── ...

O dentro de cada proyecto:

01_Projects/ 
		└── TFG/ 
		└── TFG - Arquitectura.excalidraw

## Casos de uso
- Flujos de decisión
- Arquitecturas de sistemas
- Mapas mentales
- Bocetos de UI

## Exportar

Tres puntos ⋮ → Export → PNG / SVG

## Relacionado
- [[Links y backlinks]]
- [[Sistema PARA]]
- [[Flujo PARA.excalidraw]]