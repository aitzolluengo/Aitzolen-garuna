---
fecha: 2026-05-24
tags:
  - tipo/proyecto
  - tfg
---

# Sesión 24/05/2026 — Think&DoIT

## Código (semana 18-24 mayo)

### Historial de chat persistente
- Creada tabla `chat_mensajes` en BD
- Modificado `ChatServlet.java` — guarda mensajes en BD al enviar
- `ejercicio-detalle.jsp` carga el historial previo al abrir el ejercicio
- Flujo completo probado: abrir ejercicio → ver historial previo ✅

### Bug fixes
- Toast login auto-dismiss añadido
- `favicon.ico` añadido en `webapp/`
- Redirect `/` si el usuario ya tiene sesión activa

### Perfil de usuario editable
- `PerfilServlet.java` implementado
- `perfil.jsp` creada

---

## Documentación (semana 18-24 mayo)

### 4.3 — Antecedentes
- Redactado y entregado ✅

### 4.4 — Datu-eredua + Sistema-arkitektura
**4.4 Datu-eredua:**
- 8 tablas documentadas con estructura: deskribapena · eremuak · erlazioak
- Tablas: `erabiltzaileak`, `klasea`, `klase_ikasle`, `ariketak`, `entregak`, `iragarkiak`, `konbertsazioak`, `mezuak`
- Diagrama ER generado en Mermaid → pendiente exportar `er_diagrama.png`

**4.4 Sistema-arkitektura:**
- 4.4.1 Zerbitzuen eskema — arquitectura MVC, AuthFilter, capas, OpenAI dependency
- 4.4.2 Frontend osagaia — JSP + Bootstrap, todas las páginas, pendiente pantallazos
- Diagrama de arquitectura pendiente → `arkitektura.png`
- Pendiente: 4.4.3 Autentifikazioa, 4.4.4 Irakasle, 4.4.5 Ikasle, 4.4.6 IA

### 4.5 — Empezada ✅

---

## Inglés
- Test 1 completo del libro **B2 First Trainer 2** realizado ✅
- Wishes & Regrets repasados ✅
- Use of English / Writing arrancado ✅

---

## Bullet Journal
- Organizado el cuaderno con índice, log mensual y log diario ✅
- Implementando hábito de pasar resumen diario a Claude

---

## Siguiente sesión
- Continuar documentación: 4.4.3 Autentifikazioa en adelante
- Pantallazos de la app para figuras del 4.4.2
- `arkitektura.png` y `er_diagrama.png` pendientes
- Búsqueda en listas (JS puro) pendiente
- Datos de demo realistas pendiente
