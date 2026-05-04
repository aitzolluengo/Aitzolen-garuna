# ThinkAndDoIT — Roadmap hacia el 10


## Estado actual



| Modulo                                       | Estado        |
| -------------------------------------------- | ------------- |
| Auth (login/registro/logout/filtro)          | #hecho        |
| Panel Profesor                               | #hecho        |
| ==Gestión ejercicios==                       | ==#progreso== |
| Sistema de entregas — alumno entrega / edita | #hecho        |
| Vista lista de entregas en panel profesor    | #hecho        |
| **Corrección de entregas con IA**            |               |
| **Modal detalle entrega (profesor)**         |               |
| **Migrar IA de Groq → Claude**               |               |
| **Panel alumno — resumen de notas**          |               |
| **Estadísticas de clase (profesor)**         |               |


---

  

## Bloque 1 — Migrar Groq → Claude API / Open AI⚡ PRIORITARIO


**Por qué:** Groq no te convence. Claude (Anthropic) da mejor calidad en razonamiento pedagógico, tiene SDK estable y respuestas más consistentes en formato JSON.

  
**Qué cambiar:**

- `ChatServlet.java` — reemplazar `llamarGroq()` por `llamarClaude()`
- `GenerarEjercicioServlet.java` — lo mismo
- `config.properties` — cambiar `groq.api.key` → `claude.api.key`


**Endpoint Claude:** `https://api.anthropic.com/v1/messages`  

**Modelo recomendado:** `claude-haiku-4-5-20251001` (barato, rápido) para chat tutor; `claude-sonnet-4-6` para generación de ejercicios (mejor calidad JSON).  

**Headers necesarios:** `x-api-key`, `anthropic-version: 2023-06-01`, `Content-Type: application/json`

  

**Formato request:**

```json

{

  "model": "claude-haiku-4-5-20251001",

  "max_tokens": 1024,

  "system": "...",

  "messages": [{"role": "user", "content": "..."}]

}

```

  
**Formato response:** `response.content[0].text`

  

---
## Bloque 2 — Corrección de entregas con IA ⚡ PRIORITARIO


Esta es la funcionalidad más valorable que falta. `EntregaDAO.corregir()` ya existe — solo falta el servlet y la UI.

### 2a. `CorregirEntregaServlet.java`

- Ruta: `POST /corregir-entrega`
- Solo accesible por PROFESOR
- Recibe: `entregaId`
- Lógica:
  1. Cargar entrega de BD
  2. Cargar ejercicio asociado
  3. Llamar Claude con el enunciado + la respuesta del alumno
  4. Parsear JSON de respuesta: `{ "nota": 7.5, "feedback": "..." }`
  5. Llamar `EntregaDAO.corregir(id, nota, feedback)`
  6. Devolver JSON `{ "ok": true, "nota": 7.5, "feedback": "..." }`

  
**Prompt para Claude (corrección):**

```

Eres un corrector pedagógico experto. Evalúa la respuesta del alumno al ejercicio dado.

Devuelve SOLO un JSON con exactamente estos campos:

{ "nota": <número decimal 0.0–10.0>, "feedback": "<texto constructivo de 2-4 frases>" }

  

El feedback debe:

- Indicar qué ha hecho bien

- Señalar qué puede mejorar (sin dar la solución)

- Ser motivador y constructivo

- Estar en el mismo idioma que la respuesta del alumno

```

  
### 2b. Modal de detalle de entrega (`ejercicio-detalle.jsp`)

El `verEntrega()` actual solo hace expand/collapse. Necesita un modal real:

```
	Entrega de: Aitor Gonzalez                
	Fecha: 03/05/2026 14:23
	[contenido completo del alumno...]

  [ Corregir con IA ]   [ Cerrar ]           

 (si ya corregida: muestra nota + feedback) 


```

  
- Botón "Corregir con IA" hace `fetch POST /corregir-entrega`
- Muestra spinner mientras la IA procesa
- Actualiza el badge de estado en la lista sin recargar página

  

---

## Bloque 3 — Panel alumno con resumen de notas


Actualmente el alumno solo ve su entrega dentro de cada ejercicio. Falta una vista global.

### 3a. `EntregaDAO.obtenerPorAlumno(int alumnoId)` (nuevo método)

```sql

SELECT e.*, ej.titulo, ej.nivel, c.nombre AS clase_nombre

FROM entregas e

JOIN ejercicios ej ON e.ejercicio_id = ej.id

JOIN clases c ON ej.clase_id = c.id

WHERE e.alumno_id = ?

ORDER BY e.fecha_entrega DESC

```


### 3b. `PanelAlumnoServlet.java` — añadir entregas al modelo

Pasar al JSP la lista de entregas del alumno.


### 3c. `panel-alumno.jsp` — sección "Mis entregas"

Tarjetas con:
- Nombre del ejercicio y clase
- Estado: ENTREGADA / CORREGIDA
- Nota (si corregida)
- Enlace al ejercicio

  

---
## Bloque 4 — Estadísticas de clase (profesor)

  
En `clase-detalle.jsp`, las 3 stat-cards muestran alumnos y ejercicios. Añadir una cuarta o mejorar las existentes:

SQL para `contarPorClase`:

```sql

SELECT COUNT(*) FROM entregas e

JOIN ejercicios ej ON e.ejercicio_id = ej.id

WHERE ej.clase_id = ?

```

  

---

## Bloque 5 — Mejoras de UX que suman nota

### 5a. Badge "GENERADO_IA" en ejercicios

`Ejercicio.fuente` ya tiene `GENERADO_IA` / `MANUAL`. Mostrar un chip visual en las tarjetas de ejercicio para que se vea que la IA lo generó.

### 5b. Fecha límite — alertas visuales

Si `ejercicio.fechaLimite` ha pasado, mostrar badge rojo "Caducado" en lugar del badge de nivel.

### 5c. Toast de confirmación al corregir

Cuando el profesor corrige con IA, mostrar un toast verde con la nota asignada sin recargar la página.

  
### 5d. Contador de entregas pendientes en sidebar

En el sidebar del profesor, el badge de "Ariketak" podría mostrar el número de entregas sin corregir.

  

---
## Bloque 6 — Seguridad básica (si se valora en la evaluación)

Los formularios no tienen protección CSRF. Para añadirla:

1. En el login, generar un token en sesión: `session.setAttribute("csrf", UUID.randomUUID().toString())`
2. Incluir `<input type="hidden" name="csrf" value="...">` en todos los forms POST
3. Validar en cada servlet POST antes de procesar


---

## Orden de implementación recomendado

  

```

1. Migrar Groq → Claude          (1-2h) — impacto inmediato, sin romper nada

2. CorregirEntregaServlet         (1h)  — el corazón del sistema

3. Modal detalle entrega          (1h)  — UI del profesor completa

4. Panel alumno con notas         (1h)  — cierra el ciclo alumno

5. Stats de clase                 (30m) — visual, fácil

6. UX mejoras (badges, toasts)    (1h)  — pulido final

7. CSRF (opcional)                (30m) — si la evaluación lo tiene en cuenta

```
