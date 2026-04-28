---
fecha: 2026-04-28
tags:
  - tipo/referencia
  - area/obsidian
---

# Cómo usar Claude Code en mi Vault

Claude Code es una IA que vive en el terminal y tiene acceso directo a los archivos de tu vault. Puede leer, crear y editar notas respetando tu sistema.

---

## Qué puede hacer por ti

### Crear notas directamente
Pídeselo con lenguaje natural y Claude creará el archivo en la carpeta correcta con el frontmatter adecuado:

> "Crea una nota de película para *Mulholland Drive* de David Lynch, la vi hoy y le doy un 5"

> "Añade una semilla al jardín digital sobre la idea de que el aburrimiento es creativo"

> "Crea un nuevo proyecto llamado 'Aprender euskera' con estado activo"

### Buscar y consultar notas
> "¿Qué películas tengo por ver?"

> "Muéstrame todas las semillas del jardín digital"

> "¿Qué proyectos están activos ahora mismo?"

### Editar y desarrollar ideas
> "Abre mi semilla sobre el aburrimiento y desarróllala como brote"

> "Añade al proyecto Rowing Fantasy la tarea de diseñar el logo"

### Organizar y limpiar
> "Revisa qué notas del inbox llevan más de una semana sin procesar"

> "Mueve esta nota de semilla a brote y actualiza el frontmatter"

---

## Comandos útiles para el terminal

Abre el terminal en la carpeta del vault (Claude Code ya sabe dónde está todo):

```bash
# Ver las películas vistas
grep -rl "cine/vista" 03_RESOURCES/Cine/Películas/

# Ver proyectos activos
grep -rl "estado: activo" 01_PROJECTS/

# Ver semillas del jardín
ls "00_JARDIN DIGITAL/01🌱 Semillas/"
```

---

## Cómo pedirle cosas (buenas prácticas)

### Se específico con el tipo de nota
En lugar de: *"crea una nota sobre Bach"*
Mejor: *"crea una semilla en el jardín sobre la estructura de las Variaciones Goldberg de Bach"*

### Dile qué template usar si lo sabes
> "Usa el template de Película para añadir *Oppenheimer*"

### Pídele que respete tu sistema
Claude Code ya conoce tu estructura gracias al archivo CLAUDE.md, pero si en algún momento no lo hace bien, corrígele:
> "Las películas van en `03_RESOURCES/Cine/Películas/`, no en la raíz"

---

## Flujos de trabajo con Claude

### Añadir una película que acabas de ver
1. Dile el título, director, año, actores principales y puntuación
2. Claude crea la nota en `03_RESOURCES/Cine/Películas/`
3. Crea o actualiza la nota del director si no existe
4. Enlaza todo con `[[]]`

### Capturar una idea rápida
1. Cuéntale la idea en lenguaje natural
2. Claude crea la semilla en `00_JARDIN DIGITAL/01🌱 Semillas/`
3. Rellena el frontmatter y la estructura del template

### Revisión semanal asistida
> "Ayúdame con la revisión semanal: lista las tareas sin completar, los proyectos activos y las semillas sin desarrollar"

### Desarrollar una idea del jardín
> "Tengo una semilla llamada 'X'. Léela y ayúdame a expandirla como brote con más desarrollo"

---

## Lo que Claude NO debe hacer sin pedirlo

- Borrar o mover notas existentes
- Cambiar la configuración de Obsidian (`.obsidian/`)
- Hacer commits de git (salvo que lo pidas explícitamente)
- Cambiar el nombre de archivos ya existentes

---

## Dónde está cada cosa

| Qué busco | Dónde está |
|---|---|
| Plantillas | `000_INBOX/02 Templates/` |
| Dashboards | `000_INBOX/01 Dashboard/` |
| Tareas sueltas | `000_INBOX/00 TASKS/Tareas/` |
| Películas | `03_RESOURCES/Cine/Películas/` |
| Ideas en desarrollo | `00_JARDIN DIGITAL/` |
| Proyectos | `01_PROJECTS/` |
| Áreas de vida | `02_Areas/` |

---

## Relacionado
- [[CLAUDE.md]] — contexto técnico que lee Claude Code
- [[Dashboard Cine]] — vista de todas las películas
- [[Dashboard Tareas]] — vista de tareas pendientes
