---
fecha: 2026-04-29
madurez: 🌳
contexto: ThinkAndDoIT — desarrollo web
tags:
  - tipo/referencia
---

# CSS compartido — sidebar.css

## Problema

El CSS de la sidebar (variables `:root`, reset `*`, base `body`, y todos los estilos `.sidebar-*`, `.nav-item`, `.user-avatar`, etc.) estaba duplicado en los 4 JSPs con navegación lateral: `panel-profesor.jsp`, `panel-alumno.jsp`, `clase-detalle.jsp` y `ejercicio-detalle.jsp`. Eran ~80 líneas repetidas en cada archivo.

## Solución

Se creó el archivo `src/main/webapp/css/sidebar.css` que centraliza:

- Variables CSS (`:root`) — paleta completa azul, verde, slate
- Reset `*` y base `body`
- Estilos completos de la sidebar (`.sidebar`, `.sidebar-grid`, `.sidebar-glow`, `.sg1/sg2`, `.sidebar-brand`, `.brand-*`, `.role-badge`, `.sidebar-nav`, `.nav-item`, `.sidebar-user`, `.user-avatar`, `.user-info`, `.logout-btn`)
- Toasts flotantes (`.toast-container-fixed`, `.toast-msg`, `.toast-success`, `.toast-danger`)
- Badges de nivel (`.badge-nivel`, `.badge-pill`, `.badge-FACIL`, `.badge-MEDIO`, `.badge-DIFICIL`, `.badge-IA`)
- Clases de modal (`.modal-content`, `.modal-header`, `.modal-body`, `.modal-footer`, `.form-ctrl`, `.btn-modal-submit`, `.btn-modal-cancel`, `.btn-modal-delete`, `.icon-circle`)
- Animaciones (`@keyframes toastIn`, `@keyframes fadeInUp`)
- Media queries para sidebar responsive

## Uso

Incluir en el `<head>` de cada JSP con navegación lateral:

```html
<link href="${pageContext.request.contextPath}/css/sidebar.css" rel="stylesheet">
```

Cada JSP mantiene solo su CSS específico de página en un bloque `<style>`.

## Variante verde (panel alumno)

El `panel-alumno.jsp` usa una variante verde de la sidebar. Se aplican overrides en su bloque `<style>` local:

```css
.sidebar-grid { background-image: linear-gradient(rgba(16,185,129,0.04) 1px, transparent 1px), ... }
.sg1 { background: var(--verde-500); }
.sg2 { background: var(--azul-500); }
.brand-doit { background: linear-gradient(135deg, var(--verde-400), var(--azul-400)); ... }
.role-badge { background: rgba(16,185,129,0.15); border-color: rgba(16,185,129,0.25); color: var(--verde-400); }
.nav-item.active { background: rgba(16,185,129,0.15); color: var(--verde-400); border-color: rgba(16,185,129,0.2); }
.user-avatar { background: linear-gradient(135deg, var(--verde-500), var(--azul-500)); }
```

## Archivos afectados

- `css/sidebar.css` ← nuevo
- `jsp/panel-profesor.jsp` ← actualizado
- `jsp/panel-alumno.jsp` ← actualizado
- `jsp/clase-detalle.jsp` ← actualizado
- `jsp/ejercicio-detalle.jsp` ← actualizado
