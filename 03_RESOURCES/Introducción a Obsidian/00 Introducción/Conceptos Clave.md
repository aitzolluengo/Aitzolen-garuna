# Conceptos clave de Obsidian

> Los bloques fundamentales que necesitas entender antes de empezar.

## Vault

Es la carpeta raíz donde viven todas tus notas. Obsidian apunta a esa carpeta y trata todo su contenido como tu base de conocimiento.

- Puedes tener varios vaults (uno personal, uno trabajo)
- Es simplemente una carpeta normal en tu ordenador
- Haz backup de esta carpeta = backup (copia de seguridad) de todo tu cerebro

## Nota
Cada archivo `.md` es una nota. Sin límite de tamaño ni cantidad.
Una nota puede ser desde una idea de 2 líneas hasta documentación 
técnica completa.

## Markdown
El lenguaje con el que escribes en Obsidian. Texto plano con símbolos 
que dan formato:

| Sintaxis         | Resultado                |
| ---------------- | ------------------------ |
| `**texto**`      | **negrita**              |
| `*texto*`        | *cursiva*                |
| `# Título`       | Título H1 (Encabezado 1) |
| `## Sección`     | Título H2 (Encabezado 2) |
| `- item`         | Lista                    |
| ` ```código``` ` | Bloque de código         |

## Links y Backlinks
La característica más importante de Obsidian.

**Link:** `[[Nombre de nota]]` — conecta esta nota con otra
**Backlink:** lista automática de todas las notas que apuntan a la actual

Ejemplo: si en 5 notas distintas escribes `[[Otra nota]]`, 
la nota Spring Boot mostrará esas 5 notas en sus backlinks.

## Tags
Etiquetas para agrupar notas por tema: `#obsidian` `#proyecto` `#idea`
Se pueden usar en búsquedas y filtros.

## Graph View
Visualización en forma de grafo de todas tus notas y sus conexiones.
Cuanto más usas links, más útil y revelador se vuelve.

## Plugins

Extensiones que amplían Obsidian. Hay dos tipos:
- **Core plugins** → vienen incluidos, actívalos en Settings
- **Community plugins** → instalados manualmente, miles disponibles

## Relacionado
- [[Qué es obsidian]]
- [[Instalación y configuración]]
- [[Links y Backlinks]]
- [[Graph View]]