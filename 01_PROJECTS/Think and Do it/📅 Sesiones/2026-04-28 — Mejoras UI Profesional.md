---
fecha: 2026-04-28
tags:
  - tipo/proyecto
  - tfg
  - daily
---

## Think&DoIT — Sesión 28/04/2026

> Sesión dedicada a refactoring visual completo de la interfaz. El objetivo fue elevar el nivel de profesionalidad de la plataforma sin tocar la lógica de negocio.

---

### ✅ Lo que hemos hecho hoy

#### 🏠 Landing page (`index.html`)
- Reescritura completa desde cero (antes era solo un `<h1>`)
- Navbar fija con efecto **glassmorphism** (blur + fondo semitransparente)
- Hero section con título animado en gradiente, badge de IA, y dos CTAs
- Sección de **6 features** en grid responsive
- Sección **"Cómo funciona"** con 3 pasos conectados visualmente
- Sección de **roles** (Profesor / Alumno) con features específicas
- Footer limpio con links a login y registro
- Totalmente responsive (móvil/tablet/escritorio)

#### 🔐 Login (`login.jsp`)
- Eliminado el link "Amaitu sesioa" que aparecía erróneamente en el formulario de login
- Añadido **toggle ojo** para mostrar/ocultar la contraseña

#### 📝 Registro (`registro.jsp`)
- Corregido typo: `erreigstratzeko` → `erregistratzeko`
- Añadidos **toggles de contraseña** en los dos campos de contraseña
- Añadido **indicador de fortaleza de contraseña** (barra de colores + etiqueta textual: Oso ahula / Ahula / Nahikoa / Sendoa)

#### 📋 Panel Profesor (`panel-profesor.jsp`)
- **Toasts auto-dismiss**: los mensajes de éxito/error desaparecen solos a los 4 segundos con animación suave
- **Animación de entrada** escalonada para las tarjetas de clase (`fadeInUp` con delay por índice)

#### 👤 Panel Alumno (`panel-alumno.jsp`)
- Mismas mejoras que el panel profesor (toasts auto-dismiss + animaciones de entrada)

#### 🏫 Detalle de clase (`clase-detalle.jsp`)
- Reparado el **hero border-top**: el método anterior (`border-image` + `border-radius`) no renderizaba bien en todos los browsers → ahora usa un `<div>` separado con gradiente
- Toasts auto-dismiss igual que en los paneles

#### 💬 Detalle de ejercicio / Chat IA (`ejercicio-detalle.jsp`)
- **Renderizado de Markdown** en las respuestas del tutor IA: negritas `**texto**`, cursivas `*texto*`, código inline `` `texto` ``, listas (`-` / `1.`), separadores horizontales (`---`)
- **Preguntas sugeridas** (chips clickables) en la pantalla de bienvenida del chat
  - "Ez dut ulertzen nondik hasi"
  - "Pista bat eman nahi al didazu?"
  - "Adibide bat jarri al diezadakezu?"
  - "Nola antolatuko zenuke zeuk?"
- Los chips desaparecen automáticamente al enviar el primer mensaje
- Al pulsar un chip se envía directamente la pregunta al tutor IA

---

### 📁 Archivos modificados

| Archivo | Tipo de cambio |
|---|---|
| `index.html` | Reescritura completa |
| `login.jsp` | Fix bug + password toggle |
| `registro.jsp` | Fix typo + password toggles + strength meter |
| `panel-profesor.jsp` | Toast auto-dismiss + animaciones |
| `panel-alumno.jsp` | Toast auto-dismiss + animaciones |
| `clase-detalle.jsp` | Fix hero border + toast auto-dismiss |
| `ejercicio-detalle.jsp` | Markdown render + chips sugeridos |

---

### 🔜 Pendiente próxima sesión

- Entregas del alumno (formulario de respuesta final)
- Historial de chat persistente en base de datos
- Estadísticas reales en las stat-cards (ejercicios creados, completados)
- Continuar con la memoria LaTeX del TFG

---

### ⏳ Fechas clave

- **Entrega TFG:** 25 de junio 2026
- **Hoy:** 28 de abril 2026
- **Tiempo restante:** ~58 días
