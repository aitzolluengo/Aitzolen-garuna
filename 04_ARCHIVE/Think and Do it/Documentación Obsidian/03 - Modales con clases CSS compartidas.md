---
fecha: 2026-04-29
madurez: 🌳
contexto: ThinkAndDoIT — desarrollo web
tags:
  - tipo/referencia
revisado: false
---
> [!warning] Pendiente de revisión
> Nota generada el 2026-04-29. Cambia `revisado: true` cuando la hagas tuya.


# Modales con clases CSS compartidas

## Problema

Los modales Bootstrap en `clase-detalle.jsp` y `panel-alumno.jsp` usaban estilos inline repetitivos:

```html
<div class="modal-content" style="border-radius:14px;border:1px solid var(--slate-200);">
  <div class="modal-header" style="border-bottom:1px solid var(--slate-100);padding:1.25rem 1.5rem;">
    <h5 class="modal-title" style="font-size:16px;font-weight:700;color:var(--slate-900);">
      <i class="bi bi-plus-circle-fill me-2" style="color:var(--azul-500);"></i>Título
    </h5>
  </div>
  <div class="modal-body" style="padding:1.5rem;">
    <input style="width:100%;padding:11px 14px;border:1.5px solid var(--slate-200);border-radius:10px;...">
  </div>
  <div class="modal-footer" style="border-top:1px solid var(--slate-100);padding:1rem 1.5rem;gap:8px;">
    <button style="font-size:14px;color:var(--slate-600);border:1px solid ...">Cancelar</button>
    <button style="background:var(--azul-500);...">Guardar</button>
  </div>
</div>
```

## Solución

Se añadieron clases de modal a `sidebar.css` y se reescribieron los modales:

```html
<div class="modal-content">
  <div class="modal-header">
    <h5 class="modal-title-custom">
      <div class="icon-circle blue"><i class="bi bi-plus-circle-fill"></i></div>
      Título
    </h5>
    <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
  </div>
  <div class="modal-body">
    <div class="form-group">
      <label class="form-label-custom">Campo</label>
      <input class="form-ctrl" type="text" name="campo">
    </div>
  </div>
  <div class="modal-footer">
    <button type="button" class="btn-modal-cancel" data-bs-dismiss="modal">Cancelar</button>
    <button type="submit" class="btn-modal-submit blue">
      <i class="bi bi-check-lg"></i> Guardar
    </button>
  </div>
</div>
```

## Clases disponibles en sidebar.css

| Clase | Uso |
|---|---|
| `.modal-content` | Contenedor del modal con border-radius y sombra |
| `.modal-header` | Cabecera del modal |
| `.modal-title-custom` | Título con flex y gap |
| `.icon-circle.blue/.red/.green` | Icono circular coloreado para el título |
| `.modal-body` | Cuerpo del modal (fondo slate-50) |
| `.modal-footer` | Pie del modal |
| `.form-group` | Grupo de campo con margin-bottom |
| `.form-label-custom` | Etiqueta del campo |
| `.form-ctrl` | Input/textarea/select con estilos compartidos |
| `.form-ctrl.select` | Select con flecha personalizada |
| `.form-row-2` | Grid de 2 columnas para campos en paralelo |
| `.modal-alert.modal-alert-danger` | Alerta roja dentro del body del modal |
| `.btn-modal-cancel` | Botón cancelar |
| `.btn-modal-submit` | Botón submit (fondo slate-900 por defecto) |
| `.btn-modal-submit.blue` | Botón submit azul |
| `.btn-modal-delete` | Botón acción destructiva (rojo) |