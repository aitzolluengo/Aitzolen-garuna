---
fecha_inicio: 2026-04-28
estado: activo
tags:
  - tipo/proyecto
  - tfg
---

# Roadmap — Mejoras Futuras · Think&DoIT

> Lista priorizada de funcionalidades y mejoras pendientes, organizada por impacto y dificultad.

---

## 🔴 Alta prioridad (antes de la entrega TFG)

### Entregas del alumno
- **Qué es:** formulario donde el alumno puede escribir y enviar su respuesta final a un ejercicio
- **Por qué:** cierra el ciclo pedagógico completo (ejercicio → trabajo → entrega)
- **Dónde:** nueva sección en `ejercicio-detalle.jsp` + `EntregaServlet` + tabla `entregas` en BD
- **Complejidad:** media

### Historial de chat persistente en BD
- **Qué es:** guardar los mensajes del chat tutor en la base de datos para recuperarlos al volver al ejercicio
- **Por qué:** ahora el historial se pierde al recargar la página
- **Dónde:** nueva tabla `chat_mensajes` + modificar `ChatServlet` + `ejercicio-detalle.jsp`
- **Complejidad:** media

### Estadísticas reales en las stat-cards
- **Qué es:** las tarjetas de "Sortutako ariketak" y "Egindako ariketak" muestran `—` porque no están conectadas a datos reales
- **Por qué:** el panel queda incompleto visualmente y funcionalmente
- **Dónde:** `PanelProfesorServlet` y `PanelAlumnoServlet` → queries adicionales al DAO
- **Complejidad:** baja

---

## 🟡 Media prioridad (deseable antes de la entrega)

### Perfil de usuario editable
- Cambiar nombre, apellidos, email, contraseña
- Nuevo servlet `PerfilServlet` + formulario en vista nueva `perfil.jsp`
- Los nav-items "Perfila" ya están en el sidebar (marcados como "Laster")

### Vista global de ejercicios del alumno
- Panel que muestre todos los ejercicios de todas las clases del alumno, con estado (pendiente/entregado)
- Los nav-items "Ariketak" del sidebar ya están preparados (marcados como "Laster")

### Vista global de ejercicios del profesor
- Panel que liste todos los ejercicios creados por el profesor a través de todas sus clases
- Filtros por clase, dificultad, fuente (manual / IA)

### Búsqueda en la lista de alumnos/ejercicios
- Input de búsqueda en tiempo real para filtrar alumnos o ejercicios en clase-detalle
- Implementable con JavaScript puro sin servidor

---

## 🟢 Baja prioridad / Post-TFG

### Notificaciones de nuevos ejercicios
- El alumno recibe una notificación (toast o badge en sidebar) cuando el profesor publica un nuevo ejercicio
- Requiere polling o WebSockets

### Modo oscuro
- Toggle en el sidebar para alternar entre modo claro y oscuro
- Implementable con CSS variables + `localStorage`

### Exportar historial de chat a PDF
- El alumno puede descargar su conversación con el tutor como PDF
- Librería server-side: iText o similar

### Dashboard de analíticas para el profesor
- Gráficos de participación: cuántos alumnos han abierto cada ejercicio, tiempo medio en el chat, etc.
- Requiere registrar eventos en BD (tabla `actividad`)

### Soporte multiidioma completo
- Actualmente la UI mezcla español y euskera
- Implementar i18n con archivos de propiedades `.properties` en Java

### Autenticación con Google / Microsoft
- Inicio de sesión con cuenta del centro educativo (OAuth 2.0)
- Relevante para un despliegue real en un ikastetxe

---

## 🐛 Bugs conocidos / Deuda técnica

| Problema | Descripción | Solución propuesta |
|---|---|---|
| CSS inline en modales | Los modales usan `style="..."` inline en vez de clases CSS | Extraer a clases en el `<style>` del JSP |
| Opciones de materia inconsistentes | Modal "Crear clase" tiene materias en español; "Editar clase" las tiene en euskera | Unificar en un único idioma |
| `border-image` ignorado en Safari | Ya resuelto con el fix del hero en clase-detalle | ✅ Resuelto el 28/04 |
| Toast en login no auto-dismiss | Los mensajes de error en login.jsp no desaparecen solos | Añadir el mismo script de auto-dismiss |
| Favicon no configurado | El browser muestra el icono genérico del servidor | Añadir `favicon.ico` en `webapp/` |
| `index.html` no protegido por AuthFilter | Un usuario logueado puede ver la landing page yendo directamente a `/` | Redirigir a su panel si ya tiene sesión |

---

## 💡 Ideas para demostración TFG

- Preparar **datos de prueba** realistas (3 clases, 10 alumnos, 15 ejercicios)
- Demo guiada: flujo profesor (crear clase → generar ejercicio con IA) + flujo alumno (unirse → usar chat tutor)
- Capturas de pantalla de cada pantalla para la memoria LaTeX
- Vídeo de demostración (screencast) del chat tutor en acción
