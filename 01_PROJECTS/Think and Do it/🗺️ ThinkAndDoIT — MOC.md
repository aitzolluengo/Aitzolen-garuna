---
fecha_inicio: 2026-04-20
estado: activo
tags:
  - tipo/proyecto
  - tfg
---

# 🗺️ Think&DoIT — Mapa del Proyecto

> Plataforma educativa con IA integrada para profesores y alumnos. TFG · Entrega: 25 junio 2026.

---

## 📌 Estado rápido

| Campo | Valor |
|---|---|
| Estado | 🟢 Activo |
| Entrega TFG | 25 junio 2026 |
| Tiempo restante | ~2 meses |
| Repo | GitLab |
| Stack | Java 21 · Jakarta EE · MySQL · Bootstrap 5 · Groq API |

---

## 🗂️ Notas del proyecto

### 📅 Sesiones de trabajo
- [[2026-04-26 — Generacion IA y Prompt]] — Generación de ejercicios con IA + mejora del prompt pedagógico
- [[2026-04-28 — Mejoras UI Profesional]] — Refactoring visual completo, landing page, markdown en chat

### 📋 Reuniones
- [[2026-04-28 — Bilera Tutorearekin]] — Tutoría 28/04/2026: Gantt, matrícula, funcionalidades, LaTeX

### 🔧 Referencia técnica
- [[Arquitectura Técnica]] — Stack, estructura de carpetas, flujo de datos
- [[Glosario Técnico]] — JSP, Servlet, DAO, MVC, Groq, BCrypt, OkHttp...

### 🗓️ Planificación
- [[Roadmap — Mejoras Futuras]] — Próximas funcionalidades y mejoras pendientes

---

## ✅ Funcionalidades implementadas

- [x] Autenticación (login, registro, logout) con BCrypt y bloqueo por intentos
- [x] Roles ALUMNO / PROFESOR con filtro de acceso por URL
- [x] Panel profesor: crear, editar, eliminar clases
- [x] Panel alumno: unirse/salir de clases con código de acceso
- [x] Vista detalle de clase con lista de ejercicios y alumnos
- [x] Crear ejercicios manualmente
- [x] Generar ejercicios con IA (Groq API)
- [x] Chat tutor IA por ejercicio (método Socrático)
- [x] Expulsar alumnos de clase
- [x] Landing page profesional
- [x] Toasts auto-dismiss en todos los paneles
- [x] Toggle show/hide contraseña en login y registro
- [x] Indicador de fortaleza de contraseña en registro
- [x] Renderizado Markdown en respuestas del chat IA
- [x] Preguntas sugeridas (chips) en el chat tutor

---

## 🔜 Próximas funcionalidades

- [ ] Entregas del alumno (respuesta final al ejercicio) #tfg 
- [ ] Historial de chat persistente en BD #tfg 
- [ ] Estadísticas reales en las stat-cards (ejercicios creados, completados) #tfg 
- [ ] Perfil de usuario editable #tfg 
- [ ] Notificaciones de nuevos ejercicios #tfg 
- [ ] Panel global de ejercicios (todos sin filtrar por clase) #tfg 

→ Ver detalles en [[Roadmap — Mejoras Futuras]]

---

## ⏳ Fechas clave

```
Hoy:          28/04/2026
Entrega TFG:  25/06/2026
Margen:       ~58 días
```
