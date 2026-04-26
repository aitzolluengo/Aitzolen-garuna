---

kanban-plugin: list

---

## Panel Alumno

- [ ] Ver clases en las que está inscrito
- [ ] panel-alumno.jsp — diseño y estructura


## Ejercicios / Tareas

- [ ] Modelo Ejercicio.java
- [ ] EjercicioDAO — CRUD
- [ ] Ver ejercicios asignados (alumno)
- [ ] Fecha límite de entrega


## Entregas

- [ ] Modelo Entrega.java
- [ ] EntregaDAO
- [ ] Subir entrega (alumno)
- [ ] Ver entregas recibidas (profesor)


## Calificaciones

- [ ] Modelo Calificacion.java
- [ ] CalificacionDAO
- [ ] Poner nota a una entrega (profesor)
- [ ] Ver mis calificaciones (alumno)


## Chat

- [ ] Modelo Mensaje.java
- [ ] MensajeDAO
- [ ] Chat por clase (profesor ↔ alumnos)
- [ ] Vista de mensajes en tiempo real o polling


## Notificaciones

- [ ] Modelo Notificacion.java
- [ ] NotificacionDAO
- [ ] Generar notificación al publicar ejercicio
- [ ] Generar notificación al calificar entrega
- [ ] Vista de notificaciones en panel


## Integración LLM / IA

- [ ] Caso de uso 1: corrección automática sugerida
- [ ] Caso de uso 2: asistente para el alumno
- [ ] Servlet proxy para llamadas al LLM


## 🔴 Pendiente



## 🟡 En progreso

- [ ] Elegir proveedor API (OpenAI / Anthropic)


## 🟢 Hecho

- [ ] Unirse a una clase por código


***

## Archive

- [ ] Configurar API key en config.properties
- [x] Autenticación completa (Login / Registro / Logout)
- [ ] Crear/editar ejercicio (profesor)
- [x] AuthFilter con normalización de roles
- [x] BCrypt password hashing
- [ ] PanelAlumnoServlet
- [x] Gestión de clases — CRUD completo (profesor)
- [x] Reorganización de paquetes por dominio
- [x] Contador de alumnos en tiempo real

%% kanban:settings
```
{"kanban-plugin":"list","list-collapse":[null]}
```
%%