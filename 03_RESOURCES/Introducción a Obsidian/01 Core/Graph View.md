
> Visualización de todas tus notas y sus conexiones en forma de grafo.

## ¿Qué es?

Un mapa visual de tu vault. Cada nota es un nodo, cada link es una línea que los conecta. Cuantas más notas y links tengas, más revelador se vuelve.

**Atajo:** `Ctrl+G`

## Tipos de grafo

### Global 

Muestra **todas** las notas del vault y sus conexiones. Útil para ver el estado general de tu segundo cerebro.

### Local Graph

Muestra **una nota concreta** y sus conexiones directas. Se abre desde el panel derecho de cualquier nota. Mucho más útil en el día a día.

## Qué te dice el grafo

| Lo que ves | Lo que significa |
|------------|-----------------|
| Nodo grande | Nota muy enlazada — concepto central |
| Nodo aislado | Nota sin conexiones — huérfana |
| Cluster de nodos | Área temática densa |
| Líneas cruzando clusters | Conexión inesperada entre temas |

## Controles del grafo

- Filters → filtrar por carpeta, tag, o texto 
- Groups → colorear nodos por criterio 
- Display → tamaño de nodos, flechas, etiquetas 
- Forces → física del grafo (separación, atracción)

## Configuración recomendada

### Colorear por carpeta (Groups):

- 01_Projects → rojo 
- 02_Areas → azul 
- 03_Resources → verde 
- 04_Archive → gris

De un vistazo ves de qué tipo es cada nodo.

### Filtros útiles:

- 00_Inbox → ocultar inbox (suele ser ruido)
- 04_Archive → ocultar archivados tag:#moc → mostrar solo mapas de contenido

## MOC — Map of Content

Cuando un nodo se vuelve muy grande (muchos links entrantes), es candidato a convertirse en un **MOC**: una nota índice que organiza y enlaza todas las notas de ese tema.

Ejemplo: `MOC - Cine.md` enlaza todas tus notas de Cine.

## Para qué usarlo realmente
- **Revisión semanal** → detectar notas huérfanas que necesitan conexión
- **Exploración** → navegar el grafo para redescubrir ideas olvidadas
- **Validación** → si una área tiene pocos nodos, está poco desarrollada

## Lo que NO es
No es para organizar. No es para navegar el día a día.
Es una **herramienta de reflexión**, no de trabajo.

## Relacionado
- [[Links y Backlinks]]
- [[Tags]]
- [[03_RESOURCES/Introducción a Obsidian/03 Flujos de trabajo/Revisión semanal]]