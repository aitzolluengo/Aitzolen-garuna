---
fecha_inicio: 2026-04-28
estado: activo
tags:
  - tipo/proyecto
  - tipo/referencia
  - tfg
---

# Arquitectura Técnica — Think&DoIT

> Documento de referencia técnica del proyecto. Stack, estructura de carpetas, flujo de datos y decisiones de arquitectura.

---

## Stack tecnológico

| Capa | Tecnología | Versión |
|---|---|---|
| Lenguaje backend | Java | 21 |
| Framework web | Jakarta EE Servlets | 6.0 |
| Build tool | Maven | 4.0.0 |
| Base de datos | MySQL | 8.0 |
| Hashing contraseñas | jBCrypt | 0.4 |
| HTTP cliente (API) | OkHttp3 | 4.12.0 |
| JSON | org.json | 20231013 |
| LLM API | Groq (llama-3.3-70b-versatile) | — |
| Frontend CSS | Bootstrap | 5.3.3 |
| Frontend íconos | Bootstrap Icons | 1.11.3 |
| Tipografías | Google Fonts (DM Sans, Space Mono) | — |
| Vistas | JSP (Java Server Pages) | — |

---

## Estructura de carpetas del proyecto

```
src/main/
├── java/com/thinkanddoit/
│   ├── dao/              ← Acceso a base de datos (UsuarioDAO, ClaseDAO, EjercicioDAO...)
│   ├── model/            ← Entidades: Usuario, Clase, Ejercicio
│   ├── servlets/
│   │   ├── auth/         ← LoginServlet, LogoutServlet, RegistroServlet
│   │   ├── alumno/       ← PanelAlumnoServlet, UnirseClaseServlet, SalirClaseServlet
│   │   ├── profesor/     ← PanelProfesorServlet, CrearClaseServlet, EditarClaseServlet...
│   │   ├── ejercicio/    ← CrearEjercicioServlet, EjercicioDetalleServlet, GenerarEjercicioServlet
│   │   ├── chat/         ← ChatServlet (tutor IA)
│   │   └── filter/       ← AuthFilter (protección de rutas)
│   └── util/
│       ├── DBConnection.java     ← Pool de conexiones MySQL
│       └── PasswordUtil.java     ← Hash/verificación BCrypt
└── webapp/
    ├── index.html                ← Landing page pública
    ├── jsp/
    │   ├── login.jsp
    │   ├── registro.jsp
    │   ├── panel-alumno.jsp
    │   ├── panel-profesor.jsp
    │   ├── clase-detalle.jsp
    │   └── ejercicio-detalle.jsp
    └── WEB-INF/web.xml           ← Configuración de la app web
```

---

## Patrón arquitectónico: MVC con Servlets

```
Petición HTTP
    ↓
AuthFilter (¿está autenticado? ¿tiene el rol correcto?)
    ↓
Servlet (Controller) → llama al DAO
    ↓
DAO (Model) → consulta MySQL
    ↓
Servlet → setea atributos en request
    ↓
JSP (View) → genera el HTML
    ↓
Respuesta HTML al navegador
```

- Los **Servlets** actúan de controladores: reciben la petición, llaman al DAO y redirigen a la vista.
- Los **DAOs** encapsulan toda la lógica SQL; los Servlets nunca tocan JDBC directamente.
- Las **JSPs** solo muestran datos; no tienen lógica de negocio.

---

## Mapa de rutas (URL → Servlet)

| URL | Servlet | Rol requerido |
|---|---|---|
| `/login` | LoginServlet | Público |
| `/registro` | RegistroServlet | Público |
| `/logout` | LogoutServlet | Autenticado |
| `/panel-alumno` | PanelAlumnoServlet | ALUMNO |
| `/panel-profesor` | PanelProfesorServlet | PROFESOR |
| `/clase` | ClaseDetalleServlet | Ambos |
| `/crear-clase` | CrearClaseServlet | PROFESOR |
| `/editar-clase` | EditarClaseServlet | PROFESOR |
| `/eliminar-clase` | EliminarClaseServlet | PROFESOR |
| `/unirse-clase` | UnirseClaseServlet | ALUMNO |
| `/salir-clase` | SalirClaseServlet | ALUMNO |
| `/expulsar-alumno` | ExpulsarAlumnoServlet | PROFESOR |
| `/ejercicio` | EjercicioDetalleServlet | Ambos |
| `/crear-ejercicio` | CrearEjercicioServlet | PROFESOR |
| `/eliminar-ejercicio` | EliminarEjercicioServlet | PROFESOR |
| `/api/generar-ejercicio` | GenerarEjercicioServlet | PROFESOR |
| `/api/chat` | ChatServlet | ALUMNO |

---

## Flujo de las dos funcionalidades IA

### Generación de ejercicios (profesor)

```
Profesor escribe descripción en textarea
    ↓ fetch POST /api/generar-ejercicio (JSON)
GenerarEjercicioServlet
    ↓ construye prompt con materia, nivel, descripción
OkHttp → Groq API (llama-3.3-70b-versatile)
    ↓ respuesta JSON: { titulo, enunciado, promptLlm }
Frontend rellena el formulario automáticamente
    ↓ POST /crear-ejercicio (formulario normal)
CrearEjercicioServlet → ClaseDAO → MySQL
```

### Chat tutor IA (alumno)

```
Alumno escribe mensaje
    ↓ fetch POST /api/chat (JSON: ejercicioId, mensaje, historial)
ChatServlet → EjercicioDAO → obtiene enunciado + promptLlm del profesor
    ↓ construye system prompt pedagógico (método Socrático)
OkHttp → Groq API
    ↓ respuesta: { respuesta: "texto del tutor" }
Frontend renderiza la respuesta con Markdown
```

---

## Seguridad implementada

| Mecanismo | Dónde |
|---|---|
| Hashing BCrypt | PasswordUtil + UsuarioDAO |
| Bloqueo por intentos (5 intentos → 15 min) | LoginServlet + UsuarioDAO |
| Control de sesión HTTP | AuthFilter + todos los Servlets |
| Control de rol por URL | AuthFilter |
| Código de acceso único por clase | CrearClaseServlet (UUID truncado) |

---

## Configuración sensible

El archivo `config.properties` (ignorado en Git) contiene:
```properties
db.url=jdbc:mysql://localhost:3306/thinkanddoit
db.username=...
db.password=...
groq.api.key=...
```
Existe `config.properties.example` en el repo como plantilla.
