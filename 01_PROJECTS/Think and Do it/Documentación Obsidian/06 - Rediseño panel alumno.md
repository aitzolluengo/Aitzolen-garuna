---
fecha: 2026-04-29
madurez: 🌳
contexto: ThinkAndDoIT — desarrollo web
tags:
  - tipo/referencia
---

# Rediseño panel alumno

## Cambios aplicados

### 1. CSS compartido

Se eliminó todo el CSS duplicado de la sidebar (~80 líneas) y se añadió el `<link>` a `sidebar.css`. Se mantiene un bloque `<style>` local solo con overrides verdes y CSS específico de página.

### 2. Tema verde de la sidebar

El panel alumno usa verde como color primario (en contraste con el azul del panel profesor). Los overrides se aplican como:

```css
.sidebar-grid { background-image: linear-gradient(rgba(16,185,129,0.04) ...) }
.sg1 { background: var(--verde-500); }      /* swap con profesor */
.sg2 { background: var(--azul-500); }
.brand-doit { background: linear-gradient(135deg, var(--verde-400), var(--azul-400)); }
.role-badge { color: var(--verde-400); border-color: rgba(16,185,129,0.25); }
.nav-item.active { background: rgba(16,185,129,0.15); color: var(--verde-400); }
.user-avatar { background: linear-gradient(135deg, var(--verde-500), var(--azul-500)); }
```

### 3. Stat cards con icono gradiente

Antes: icono plano con fondo de color plano.

```html
<div class="stat-icon green"><i class="bi bi-collection-fill"></i></div>
```

Después: icono con fondo gradiente.

```html
<div class="stat-icon-wrap green"><i class="bi bi-collection-fill"></i></div>
```

```css
.stat-icon-wrap.green { background: linear-gradient(135deg, var(--verde-500), var(--verde-400)); color: white; }
.stat-icon-wrap.slate { background: linear-gradient(135deg, var(--slate-600), var(--slate-500)); color: white; }
```

### 4. Toasts flotantes

Se movieron los toasts JSP fuera del topbar y dentro de `<div class="toast-container-fixed">` (fixed top-right). Ver [[04 - Toasts flotantes unificados]].

### 5. Modales con clases compartidas

Los modales "Unirse a clase" y "Confirmar salir" se reescribieron usando las clases CSS de `sidebar.css` en lugar de estilos inline. El modal de salir usa `.modal-alert.modal-alert-danger` para el mensaje de confirmación.

### 6. Seguridad XSS

Se añadió el helper `esc()` y se escaparon todos los campos de usuario. El botón "salir" pasó de interpolación JS inline a `data-*` attributes:

```html
<!-- Antes — riesgo de XSS en el onclick -->
<button onclick="confirmarSalir(<%= clase.getId() %>, '<%= nombreEsc %>')">

<!-- Después — seguro -->
<button data-id="<%= clase.getId() %>" data-nombre="<%= esc(clase.getNombre()) %>"
        onclick="confirmarSalir(this)">
```

```js
function confirmarSalir(btn) {
    const id = btn.dataset.id;
    const nombre = btn.dataset.nombre;
    // ...
}
```

### 7. Botón "Unirse" con color verde

El botón primario del panel alumno usa verde en hover para consistencia con el tema:

```css
.btn-unirse:hover { background: var(--verde-600); box-shadow: 0 4px 12px rgba(16,185,129,0.3); }
```
