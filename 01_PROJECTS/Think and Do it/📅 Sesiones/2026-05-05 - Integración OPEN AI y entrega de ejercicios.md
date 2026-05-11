---
fecha: 2026-05-05
tags:
  - tipo/proyecto
  - tfg
---
# Sesión 05/05/2026 — ThinkAndDoIT

## Lo que hemos hecho

### 1. Corrección IA — idioma euskera + criterios de puntuación

**Archivo:** `CorregirEntregaServlet.java`

- El feedback ahora se genera **siempre en euskera**, independientemente del idioma del alumno.
- Añadidos criterios de puntuación explícitos al prompt:
  - 9-10 → respuesta completa con proceso
  - 7-8 → correcto con pequeños errores
  - **5-6 → resultado correcto pero sin proceso** (antes daba un 2, injusto)
  - 3-4 → enfoque correcto pero errores importantes
  - 1-2 → respuesta incorrecta o casi vacía

---  
### 2. Confirmación antes de guardar la corrección IA

**Archivos:** `CorregirEntregaServlet.java`, `ejercicio-detalle.jsp`

Flujo anterior: profesor pulsa "Corregir con IA" → se guarda directamente en BD.

Flujo nuevo:

1. Profesor pulsa **"IA-rekin zuzendu"** → la IA genera nota + feedback (sin guardar)
2. Se muestra el resultado en el modal
3. Profesor decide:
   - **"Gorde zuzenketa"** → guarda en BD
   - **"Utzi"** → descarta y puede volver a intentarlo
  

El servlet distingue dos modos por el campo `confirmar` en el body JSON:
- Sin `confirmar`: llama a la IA, devuelve `{ preview: true, nota, feedback }`
- Con `confirmar: true`: recibe nota+feedback del frontend y guarda en BD (sin segunda llamada a la IA)

  

---

### 3. Panel alumno — sección "Nire entregak" + stats reales

**Archivos modificados:**

- `Entrega.java` — campos enriquecidos añadidos: `ejercicioTitulo`, `ejercicioNivel`, `claseNombre`, `claseId`
- `EntregaDAO.java` — nuevo método `obtenerPorAlumno(int alumnoId)` con JOIN a ejercicios y clases
- `PanelAlumnoServlet.java` — pasa `entregas` y `entregasCorregidas` al JSP
- `panel-alumno.jsp` — stats reales + sección nueva

  

**Stats cards** (antes mostraban `—`):

- Klase aktiboak
- Egindako entregak (total entregas enviadas)
- Zuzendutako entregak (entregas corregidas)

  

> Se descartó "Batez besteko nota" porque hay varias asignaturas y mezclar notas no tiene sentido.

  

**Sección "Nire entregak":** lista de todas las entregas del alumno con:

- Icono de estado (enviada / corregida)
- Título del ejercicio + clase + nivel + fecha
- Badge de nota si está corregida
- Link directo al ejercicio (`/ejercicio?id=X`)

---
## Documentación — Punto 3: Antecedentes (LaTeX)

Redactado y entregado en LaTeX con tres subsecciones:

1. **Situación actual** — contexto post-pandemia, OCDE Education at a Glance 2023 (65% centros con LMS), estadística Turnitin 2023 (11-22% trabajos con IA), referencia UNESCO 2023.

2. **Alternativas existentes** — análisis de Moodle, Google Classroom, Khan Academy/Khanmigo, ChatGPT directo, Edmodo. Tabla comparativa con columnas: IA nativa / Ejercicios personalizables / Corrección automática / Euskera / Coste.

3. **Enfoques posibles** — tres opciones analizadas:
   - Extender Moodle (descartada: arquitectura no apta para flujos conversacionales)
   - Capa sobre API de IA sin BD propia (descartada: no viable operativamente)
   - Plataforma propia con IA integrada desde el diseño ✅ (opción adoptada)


---

## Siguiente sesión

Según el ROADMAP_10.md, queda pendiente:

- [x] Migrar Groq → Claude en `ChatServlet.java` y `GenerarEjercicioServlet.java` ✅ 2026-05-10
- [x] Estadísticas de clase para el profesor (Bloque 4) ✅ 2026-05-10
- [x] UX mejoras: badges IA generado, alertas fecha límite, toast al corregir (Bloque 5) ✅ 2026-05-10