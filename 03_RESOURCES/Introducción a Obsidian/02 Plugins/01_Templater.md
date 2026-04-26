> Plugin para crear plantillas dinámicas y reutilizables > en Obsidian. El core Templates es estático Templater > tiene lógica real. 
> 
> Es decir, con este plugin instalado Obsidian nos permite crear nuestras plantillas para que a la hora de por ejemplo, crear una nota sobre tareas pendientes, en vez de escribir todo, nosotros tenemos una plantilla ya creada. Asi solo tenemos que rellenar lo que queriamos escribir con todos los titulos ya escritos.
## Instalación

Settings --> Community Plugin --> Browse
Search : Templater
Install : Enable

![[Pasted image 20260425131259.png|293]]
## Configuración inicial

Settings → Templater
- Template folder location: 00_Inbox/Templates (o crea una carpeta _Templates en la raíz)
- Trigger Templater on new file creation: ON
- Auto jump to cursor: ON

## Diferencia con Core Templates

| | Core Templates | Templater |
|--|---------------|-----------|
| Fecha actual | `{{date}}` estático | `<% tp.date.now() %>` dinámico |
| Lógica | No | Sí (if, loops) |
| Input del usuario | No | Sí (prompts) |
| Potencia | Básica | Alta |

## Sintaxis básica

### Fecha y hora
```javascript
<% tp.date.now("YYYY-MM-DD") %>         // 2026-04-25
<% tp.date.now("DD/MM/YYYY") %>         // 25/04/2026
<% tp.date.now("HH:mm") %>              // 14:32
<% tp.date.tomorrow("YYYY-MM-DD") %>    // mañana
```

### Datos del archivo
```javascript
<% tp.file.title %>          // nombre de la nota actual
<% tp.file.creation_date() %> // fecha de creación
<% tp.file.folder() %>       // carpeta donde está
```

### Input del usuario
```javascript
<% tp.system.prompt("¿Título del proyecto?") %>
<% tp.system.suggester(["Trabajo", "Personal", "Estudio"], 
                        ["trabajo", "personal", "estudio"]) %>
```

## Plantillas esenciales

Para ello en la carpeta 00_INBOX, creamos una carpeta llamada templates y ahi crearemos nuestras plantillas para distinta ocasión.
### Nota genérica
```markdown
---
fecha: <% tp.date.now("YYYY-MM-DD") %>
tags:
  - tipo/nota
---

# <% tp.file.title %>

## Contexto

## Contenido

## Relacionado
```

### Nota de proyecto
```markdown
---
fecha_inicio: <% tp.date.now("YYYY-MM-DD") %>
estado: activo
tags:
  - tipo/proyecto
---

# <% tp.file.title %>

## Objetivo

## Tareas
- [ ] 

## Notas y decisiones

## Relacionado
```

### Daily Note
```markdown
---
fecha: <% tp.date.now("YYYY-MM-DD") %>
dia: <% tp.date.now("dddd") %>
tags:
  - tipo/daily
---

# <% tp.date.now("DD MMM YYYY") %>

## 🎯 Foco del día

## 📋 Tareas
- [ ] 

## 📝 Notas del día

## 🔗 Links del día
```

### Nota de aprendizaje
```markdown
---
fecha: <% tp.date.now("YYYY-MM-DD") %>
tags:
  - tipo/referencia
  - area/aprendizaje
---

# <% tp.file.title %>

## ¿Qué es?

## ¿Cómo funciona?

## ¿Cómo se usa?

## Notas personales

## Relacionado
```

## Cómo usar una plantilla

1. Crea una nota nueva (`Ctrl+N`)
2. `Ctrl+P` → `Templater: Open Insert Template Modal`
3. Selecciona la plantilla
4. Templater ejecuta el código y rellena los campos

## Atajo recomendado

Settings → Templater → Template Hotkeys Asigna Alt+T → tu plantilla más usada

## Relacionado
- [[Instalación y configuración]]
- [[Daily Notes]]
- [[02_Dataview]]