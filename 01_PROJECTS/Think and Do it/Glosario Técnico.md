---
fecha_inicio: 2026-04-28
estado: activo
tags:
  - tipo/referencia
  - tipo/proyecto
  - tfg
---

# Glosario Técnico — Think&DoIT

> Definiciones de los términos técnicos usados en el proyecto, orientadas a entender las decisiones de diseño.

---

## Backend

### Servlet
Un **Servlet** es una clase Java que recibe peticiones HTTP y genera respuestas. Es el equivalente a un "controlador" en otros frameworks (como Spring Controller o Express route handler).

```
GET /panel-profesor  →  PanelProfesorServlet.doGet()  →  JSP
POST /crear-clase    →  CrearClaseServlet.doPost()     →  redirect
```

En este proyecto, cada acción de usuario tiene su propio Servlet. No usamos Spring ni ningún framework extra; solo el estándar **Jakarta EE** (antiguo Java EE).

---

### JSP (Java Server Pages)
Una **JSP** es un fichero HTML con código Java embebido entre `<% %>`. El servidor lo compila a un Servlet que genera el HTML dinámico.

```jsp
<% if (usuario != null) { %>
  <div>Kaixo, <%= usuario.getNombre() %>!</div>
<% } %>
```

En este proyecto, las JSPs son las **vistas** (lo que ve el usuario). No contienen lógica de negocio; solo muestran datos que el Servlet ha preparado.

---

### DAO (Data Access Object)
El **patrón DAO** separa la lógica de acceso a la base de datos del resto de la aplicación. Cada entidad tiene su propio DAO con métodos CRUD.

```
UsuarioDAO.buscarPorEmail(email)   → SELECT * FROM usuarios WHERE email=?
ClaseDAO.crearClase(clase)         → INSERT INTO clases ...
EjercicioDAO.getPorClase(claseId)  → SELECT * FROM ejercicios WHERE clase_id=?
```

**Ventaja:** si mañana cambias de MySQL a PostgreSQL, solo cambias los DAOs, no los Servlets.

---

### MVC (Model-View-Controller)
Patrón de arquitectura que separa la aplicación en tres capas:

| Capa | En este proyecto | Responsabilidad |
|---|---|---|
| Model | Clases `model/` + DAOs | Datos y lógica de negocio |
| View | JSPs | Presentación HTML |
| Controller | Servlets | Coordinar model y view |

---

### BCrypt
Algoritmo de **hashing de contraseñas** diseñado específicamente para ser lento (deliberadamente), lo que lo hace resistente a ataques de fuerza bruta.

- Las contraseñas **nunca** se guardan en texto plano en la BD.
- Cada hash es único aunque la contraseña sea la misma (usa un *salt* aleatorio).
- `jBCrypt` es la librería Java que lo implementa.

```java
String hash = BCrypt.hashpw(password, BCrypt.gensalt());
boolean ok   = BCrypt.checkpw(inputPassword, hash);
```

---

### OkHttp
Librería Java para hacer **peticiones HTTP** desde el servidor. Se usa para llamar a la API de Groq.

```
Servidor Java → OkHttp → POST https://api.groq.com/... → respuesta JSON
```

Alternativa más moderna a `HttpURLConnection` (el estándar de Java, que es verboso).

---

### AuthFilter
Un **Filter** de Jakarta EE que se ejecuta **antes** de que llegue la petición al Servlet. En este proyecto, `AuthFilter` comprueba:

1. ¿Está el usuario autenticado (tiene sesión HTTP activa)?
2. ¿Tiene el rol correcto para esa URL?

Si no, redirige a `/login`. Esto evita tener que repetir la comprobación en cada Servlet.

---

### Pool de conexiones (DBConnection)
En vez de abrir una conexión MySQL nueva en cada petición (lento y costoso), un **pool** mantiene un conjunto de conexiones ya abiertas y reutilizables.

`DBConnection.java` gestiona este pool con la librería estándar de MySQL Connector.

---

## Frontend

### Bootstrap 5
Framework CSS de componentes UI. Proporciona el sistema de grid, clases utilitarias, y componentes como modales, badges y botones. En este proyecto se usa la versión CDN (no se instala npm).

---

### CSS Custom Properties (variables CSS)
Definidas en `:root`, permiten reutilizar colores y valores en todo el CSS:

```css
:root {
  --azul-500: #2563eb;
  --verde-500: #10b981;
  --slate-900: #0f172a;
}

.btn { background: var(--azul-500); }
```

Cambiar un color en `:root` lo actualiza en toda la página.

---

### Glassmorphism
Efecto visual donde un elemento parece un cristal difuminado sobre el fondo. Se consigue con:

```css
background: rgba(255, 255, 255, 0.08);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.12);
```

Se usa en la navbar de la landing page.

---

### Método Socrático (en el chat IA)
Técnica pedagógica donde el tutor **no da la respuesta directamente**, sino que guía al alumno a descubrirla mediante preguntas.

En el prompt del `ChatServlet`, esto se implementa con reglas absolutas:
- *Nunca revelar la solución ni dar pasos procedimentales*
- *Preguntar al alumno qué entiende antes de guiar*
- *Respuestas cortas, máximo 2-3 frases*

---

### Groq API
Servicio de inferencia LLM ultra-rápido. Proporciona acceso al modelo **llama-3.3-70b-versatile** (Meta LLaMA 3.3, 70 mil millones de parámetros).

- Se comunica vía HTTP REST con JSON.
- La API key se guarda en `config.properties` (excluido de Git).
- Detecta automáticamente el idioma del alumno (euskera/español/inglés).

---

### Markdown (renderizado en el chat)
El tutor IA responde en texto plano con formato Markdown. El frontend lo convierte a HTML para que se vea bien:

| Markdown | HTML resultante |
|---|---|
| `**texto**` | **texto** (negrita) |
| `*texto*` | *texto* (cursiva) |
| `` `codigo` `` | `codigo` (monospace con fondo) |
| `- elemento` | Lista con viñeta |
| `---` | Línea separadora |

La conversión la hace una función `renderMarkdown()` en JavaScript, sin librerías externas.

---

### Toasts (notificaciones)
Mensajes de feedback temporal que aparecen tras una acción (éxito al crear clase, error al unirse...). En este proyecto son `<div>` con CSS que se auto-eliminan del DOM a los 4 segundos mediante JavaScript:

```js
setTimeout(() => {
  toast.style.opacity = '0';
  setTimeout(() => toast.remove(), 400);
}, 4000);
```

---

## Base de datos

### Código de acceso de clase
Al crear una clase, el sistema genera un código único (basado en UUID truncado) que los alumnos usan para unirse. Similar a los códigos de Google Classroom.

### Fuente del ejercicio (`fuente`)
Campo de la tabla `ejercicios` que indica cómo se creó:
- `MANUAL` → el profesor lo escribió a mano
- `GENERADO_IA` → lo generó la IA de Groq

Esto permite mostrar el badge `IA` en la interfaz.
