---
estado: pendiente
tags:
  - tipo/referencia
  - pendiente
---
# Obsidian Git

> Plugin para hacer backup automático de tu vault en GitHub.
> Sin pagar Obsidian Sync. Tus notas versionadas y seguras.

## ¿Por qué?
- Backup automático cada X minutos
- Historial completo de cambios
- Recupera cualquier versión anterior
- Gratis con GitHub privado

## Requisitos previos
1. Tener **Git** instalado en Windows
2. Tener cuenta en **GitHub**

### Instalar Git
Descarga desde [git-scm.com](https://git-scm.com)
Instalación por defecto, sin cambiar nada.

Verifica en terminal:
```bash
git --version
# git version 2.x.x
```

## Crear repositorio en GitHub
1. Ve a [github.com](https://github.com) → **New repository**
2. Nombre: `SecondBrain` (o el que quieras)
3. **Private** ← importante
4. No inicialices con README
5. Copia la URL: `https://github.com/tuusuario/SecondBrain.git`

## Inicializar Git en tu vault
Abre terminal en la carpeta de tu vault:

Tienes que ir a la carpeta. 
Poniendo `ls` en la terminal te muestra que carpetas estas. Puedes hacer ``cd nombre de la carpeta`` y ahí pondrías los siguientes comandos: 

```bash
git init
git remote add origin https://github.com/tuusuario/SecondBrain.git
git add .
git commit -m "Initial commit"
git push -u origin master
```

## Instalación del plugin

Settings → Community plugins → Browse Buscar: "Obsidian Git" 
Install → Enable

## Configuración

Settings → Obsidian Git

klkljkl
- Vault backup interval: 10 ← backup cada 10 minutos
- Auto pull interval: 10 ← sync desde GitHub cada 10 min
- Commit message: vault backup {{date}}
- Auto backup after stop editing: ON
- Pull updates on startup: ON
- Push on backup: ON

## Comandos manuales
Desde `Ctrl+P`:

| Comando | Acción |
|---------|--------|
| `Obsidian Git: Create backup` | Commit + push manual |
| `Obsidian Git: Pull` | Traer cambios de GitHub |
| `Obsidian Git: Open history` | Ver historial de cambios |
| `Obsidian Git: Open diff view` | Ver qué cambió |

## Recuperar una nota borrada
1. `Ctrl+P` → `Obsidian Git: Open history`
2. Busca el commit donde existía
3. Restaura el archivo

## Sincronización entre dispositivos
Con esto tienes sync entre PC y móvil gratis:

**PC → GitHub → Móvil**

En móvil instala **Obsidian Git** también y configura 
las mismas credenciales. Cada vez que abres Obsidian 
hace pull automático.

## Buenas prácticas
- Backup cada 10 minutos es suficiente
- No metas archivos grandes (imágenes pesadas) en el vault
- Añade `.obsidian/workspace` al `.gitignore` para no 
  versionar el estado de la UI

### `.gitignore` recomendado

- .obsidian/workspace 
- .obsidian/workspace.json 
- .obsidian/plugins/obsidian-git/data.json 
- .trash/ 
- .DS_Store
## Relacionado
- [[Instalación y configuración]]
- [[02_Dataview]]