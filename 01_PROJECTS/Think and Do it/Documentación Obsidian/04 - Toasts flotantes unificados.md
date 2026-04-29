---
fecha: 2026-04-29
madurez: 🌳
contexto: ThinkAndDoIT — desarrollo web
tags:
  - tipo/referencia
---

# Toasts flotantes unificados

## Problema

Los mensajes de feedback (éxito/error) estaban incrustados dentro del flujo del DOM, generalmente dentro del `<div class="topbar">`, lo que les hacía empujar el contenido de la página y tenían estilos inline diferentes en cada JSP:

```html
<div class="topbar">
  <div>
    <% if ("creada".equals(request.getParameter("ok"))) { %>
    <div class="toast-msg toast-success" style="margin-bottom:1rem;">...</div>
    <% } %>
    <div class="page-title">...</div>
  </div>
</div>
```

## Solución

Se unificó el patrón de toasts con posicionamiento fijo:

### CSS (en sidebar.css)

```css
.toast-container-fixed {
  position: fixed; top: 1.5rem; right: 1.5rem;
  z-index: 9999; display: flex; flex-direction: column;
  gap: 8px; pointer-events: none;
}
.toast-msg {
  display: flex; align-items: center; gap: 10px;
  padding: 13px 18px; border-radius: 12px; font-size: 14px; font-weight: 500;
  box-shadow: var(--shadow-md);
  animation: toastIn 0.35s cubic-bezier(0.34,1.56,0.64,1) both;
  min-width: 260px; pointer-events: all;
}
.toast-success { background: white; border: 1px solid #a7f3d0; color: #065f46; }
.toast-success i { color: var(--verde-500); }
.toast-danger  { background: white; border: 1px solid #fecaca; color: #991b1b; }
.toast-danger  i { color: #ef4444; }
```

### HTML (patrón en cada JSP)

```html
<div class="toast-container-fixed">
  <% if ("creada".equals(request.getParameter("ok"))) { %>
  <div class="toast-msg toast-success">
    <i class="bi bi-check-circle-fill"></i> Klasea sortu da!
  </div>
  <% } %>
</div>
```

### JavaScript (auto-dismiss a los 4 segundos)

```js
document.querySelectorAll('.toast-msg').forEach(function(t) {
    setTimeout(function() {
        t.style.transition = 'opacity 0.4s ease, transform 0.4s ease';
        t.style.opacity = '0';
        t.style.transform = 'translateX(12px) scale(0.95)';
        setTimeout(function() { t.remove(); }, 400);
    }, 4000);
});
```

## Beneficios

- Los toasts aparecen superpuestos sobre el contenido sin desplazarlo
- Animación de entrada elástica (`toastIn`) y salida deslizante
- Máximo 1 toast visible a la vez (por lógica JSP: solo un parámetro `ok`/`error` activo)
- Estilo consistente en todos los JSPs (blanco con borde coloreado)

## Archivos actualizados

`panel-profesor.jsp`, `clase-detalle.jsp`, `panel-alumno.jsp`
