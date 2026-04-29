---
fecha: 2026-04-29
madurez: 🌳
contexto: ThinkAndDoIT — desarrollo web
tags:
  - tipo/referencia
---

# Seguridad XSS — helper `esc()`

## Problema

Los JSPs renderizaban contenido generado por el usuario directamente en el HTML sin escapar:

```jsp
<%= clase.getNombre() %>
<%= ejercicio.getEnunciado() %>
<%= alumno.getEmail() %>
```

Si un usuario introduce `<script>alert('xss')</script>` como nombre de clase, ese código se ejecutaría en el navegador de todos los que vean la página. Vulnerabilidad OWASP Top 10 — A3: Injection (XSS).

## Solución

Se añade una declaración JSP al inicio de cada archivo:

```jsp
<%! private static String esc(String s) {
    if (s == null) return "";
    return s.replace("&", "&amp;")
            .replace("<", "&lt;")
            .replace(">", "&gt;")
            .replace("\"", "&quot;");
} %>
```

Y se aplica a **todo contenido de usuario** en el HTML:

```jsp
<%= esc(clase.getNombre()) %>
<%= esc(ejercicio.getEnunciado()) %>
<%= esc(alumno.getEmail()) %>
<%= esc(ejercicio.getPromptLlm()) %>
```

## Dónde se aplica

| JSP | Campos escapados |
|---|---|
| `panel-profesor.jsp` | clase.getNombre(), clase.getMateria(), clase.getDescripcion() |
| `clase-detalle.jsp` | clase.getNombre(), clase.getDescripcion(), ej.getTitulo(), alumno.getNombre(), alumno.getEmail() |
| `ejercicio-detalle.jsp` | ejercicio.getTitulo(), ejercicio.getEnunciado(), ejercicio.getPromptLlm(), clase.getNombre(), clase.getMateria() |
| `panel-alumno.jsp` | clase.getNombre(), clase.getCursoEscolar(), clase.getMateria(), clase.getDescripcion(), clase.getCodigoAcceso(), usuario.getNombre(), usuario.getEmail() |

## Importante

- El helper Java se usa para contenido en **HTML** (atributos y texto).
- Para contenido en **JavaScript** (p.ej. variables JS), usar `data-*` attributes o el método `escapeHtml()` en JS.
- En `panel-alumno.jsp` el botón "salir" usaba interpolación de string en `onclick`:
  ```html
  onclick="confirmarSalir(<%= clase.getId() %>, '<%= nombreEsc %>')"
  ```
  Se reemplazó por `data-*` attributes para evitar inyección JS:
  ```html
  data-id="<%= clase.getId() %>"
  data-nombre="<%= esc(clase.getNombre()) %>"
  onclick="confirmarSalir(this)"
  ```
