---
fecha_inicio: 2026-07-01
estado: activo
tags:
  - tipo/proyecto
---

# 🗺️ Recetas para Ama — Mapa del Proyecto

> App de recetas para mi ama: le dice **qué cocinar** (sencillo y saludable) con lo que tiene, y le explica la receta **en vídeo**. El usuario final es ella, no yo.

---

## 📌 Estado rápido

| Campo | Valor |
|---|---|
| Estado | 🟡 Enfoque / discovery |
| Fase actual | Responder el plan de preguntas |
| Implementación | Sin empezar |
| Plazo | ~1,5 meses |

---

## 💡 La idea

Una **app propia** (PWA instalable en el móvil, no WhatsApp) donde mi ama:
- Pide idea de comida ("qué ceno hoy", "tengo esto en la nevera").
- Recibe una receta **sencilla y saludable**, paso a paso.
- Puede ver un **vídeo** explicando cómo se hace.

Cocinar se cocina todos los días → uso altísimo, y encima es medio regalo.

---

> [!warning] La decisión que lo cambia todo: el vídeo
> "Que salga un vídeo explicando la receta" es la parte **más difícil y cara**. Antes de nada hay que decidir de dónde sale ese vídeo, porque marca el presupuesto y el alcance del MVP. Ver bloque 3.

---

## 📋 El plan de preguntas

Esto es lo que tenemos que responder **antes** de escribir código. Vamos bloque a bloque; cuando uno esté claro, lo marco.

### 1. 👩 La usuaria (tu ama)
- [ ] ¿Qué móvil tiene (iPhone / Android)? ¿Se maneja bien o cero técnica? Tiene un android y no se maneja muy bien ajjajaja
- [ ] ¿Cómo cocina ahora — improvisa, sigue recetas, repite los mismos platos? Repite los mismos aunque yo a veces le ayudo. Asi para tener variedad servira esto
- [ ] ¿Para cuántos cocina normalmente? 3-4 suele variar
- [ ] ¿Alergias / intolerancias / algo médico (azúcar, colesterol, sal…)? Ninguna
- [ ] ¿Qué le gusta y qué odia cocinar/comer? TOdo para dentro menos el pepino jajaajjaja
- [ ] ¿Cuánto tiempo suele tener para cocinar entre semana? 1h peor bueno eso para las recetas diria tiempo estimado hoy para cocinar 30 mins y luego el bot sugiere

### 2. 🥗 Recetas y "saludable"
- [ ] ¿Qué significa "saludable" aquí — equilibrado general, bajar peso, algo concreto? Equlibrado. 
- [ ] ¿Estilo de cocina? (mediterránea, casera de siempre, etc.) Un poco de todo pero con alimentos accesibles en cualquier supermercado
- [ ] **¿De dónde salen las recetas?** ¿La IA las inventa libremente, o partimos de un recetario curado/validado? *(Riesgo: la IA puede inventar cantidades raras o combinaciones malas.)* Partimos de Karlos Arguiñano jajajajaajajajaj
- [ ] ¿Nivel de dificultad e ingredientes: fáciles, baratos y de super normal? Dificultad facil pero yo haria que se pueda elegir y que se  uestre que dificutlad tienene. Baratos y super aunque compramos en fruteria y carniceria ciertas cosas
- [ ] ¿Debe proponer según **lo que ya tiene en casa**, o da igual?
   Segun lo que haya en casa
### 3. 🎬 El vídeo (crítico — decidir primero)
- [ ] ¿Qué es "el vídeo" exactamente? Opciones, de más fácil a más difícil:
  - **A)** Enlazar a un vídeo real de YouTube de esa receta. *(Gratis, fácil, no es "nuestro".)*
  - **B)** Animación de los pasos con fotos + voz IA (TTS). *(Media, hacible.)*
  - **C)** Vídeo generado por IA de verdad. *(Caro, aún inmaduro, lento.)*
- [ ] ¿Vale con voz + imágenes, o ella quiere ver a alguien cocinando?
- [ ] ¿Presupuesto para esto? (la generación de vídeo/voz cuesta dinero por uso)
 Aqui no se que sugieres pero mejor video de youtube

### 4. 📱 La app (funciones y UX)
- [ ] Funciones de la v1: *¿Qué cocino hoy? · Por ingredientes · Favoritos · Lista de la compra* sii , todo lo que se te ocurra sera bienvenido
- [ ] ¿Guardar recetas favoritas y su historial? sii
- [ ] ¿Genera **lista de la compra**? (aquí enlaza con [[🗺️ Shopping List Recorder — MOC|Shopping List Recorder]]) sii
- [ ] UX para ella: letra grande, botones grandes, en castellano, mínimo escribir. sii que sea facil de manejar

### 5. ⚙️ Técnico y coste
- [ ] ¿Tengo API key de Anthropic? ¿Presupuesto/mes asumible? sii tengo
- [ ] Stack: web (¿React o HTML simple?) + PWA.
- [ ] Hosting gratis/sencillo (Vercel/Netlify) → un link que ella instala.
- [ ] ¿Quién lo mantiene y actualiza (yo)? yo y ella

### 6. 🎯 Alcance MVP (mes y medio)
- [ ] ¿Qué es lo **mínimo** que le sirve a ella y podemos enseñar pronto? voy decidiendo
- [ ] ¿Qué dejamos para "más adelante" (v2)?

### 7. 🔒 Privacidad
- [ ] ¿Guardamos datos de ella? ¿Dónde? ¿Hace falta? noo

---

## ✅ Decisiones cerradas (2026-07-01)

- **Recetas curadas, no inventadas:** recetario real (base Karlos Arguiñano), cada receta con su vídeo de YouTube. La IA elige/ordena/adapta, **no inventa**.
- **Vídeo:** enlace a YouTube (opción A).
- **Flujo:** ama **selecciona lo que tiene** → el bot sugiere recetas que encajan.
- **Comensales:** selector, por defecto **4**.
- **Dificultad:** Fácil / Media / Difícil, visible y filtrable.
- **Tiempo de hoy:** selector (15/30/45 min) que filtra recetas.
- **Datos:** sí habrá **base de datos** (favoritos, historial, lista de la compra). Mínimos, sin datos sensibles.
- **Extras aprobados:** Sorpréndeme · Aprovecha las sobras · Menú semanal · filtro comida/cena.
- **Fuente de recetas:** **recetario propio** (contenido original en español, fácil, para 4) + **vídeo oficial de YouTube** enlazado. Nada copiado del libro (copyright); el libro solo es referencia para elegir platos.
- **Crecimiento del catálogo:** la base **se llena sola con el uso** — si se pide una receta que no existe, Claude la genera al vuelo y se **guarda en Supabase** (generada una vez, cacheada para siempre). Complementos: **panel de admin** para revisar/enganchar vídeos, y **registro de recetas pedidas**.

---

> [!important] Realización clave: esto se junta con Shopping List Recorder
> La lista de la compra que quiere es **familiar y compartida** ("saber cuándo se termina algo") → eso **es** [[🗺️ Shopping List Recorder — MOC|Shopping List Recorder]]. Los dos proyectos **convergen**. Implica **backend + base de datos compartida**, no solo local.
> **Decisión pendiente:** ¿la lista compartida entra en el MVP o va a v2?

---

## 🧱 Stack propuesto

- **Front:** React + PWA (instalable en el móvil de ama)
- **Backend/BD:** Supabase (base de datos + tiempo real + gratis para empezar)
- **IA:** API de Claude (key ya disponible)
- **Hosting:** Vercel/Netlify → un link que ella instala

---

## 🎯 MVP v1

Pantalla simple, letra grande, castellano:
1. Ama selecciona **qué tiene** + **tiempo de hoy** + **comensales**.
2. La IA propone **2-3 recetas** del recetario, con vídeo, pasos, dificultad y tiempo.
3. Botones: **Guardar favorito** · **Sorpréndeme** · **Generar lista de la compra**.

## 🔮 v2 (más adelante)

- Lista de la compra **familiar compartida** en tiempo real (merge completo con Shopping List Recorder)
- Menú semanal · entrada por voz · "aprovecha las sobras"

---

## 🔜 Próximos pasos

**Hecho el 2026-07-01**
- [x] Responder plan de preguntas ✅ 2026-07-01
- [x] Decidir vídeo (YouTube) ✅ 2026-07-01
- [x] Decidir alcance de la lista compartida → simple compartida en MVP ✅ 2026-07-01
- [x] Recetario inicial arrancado (8 recetas, sin tortilla) ✅ 2026-07-01
- [x] Montar esqueleto React + PWA (UI, auth, lista de la compra) ✅ 2026-07-01

**🌅 Para mañana (2026-07-02)**
- [ ] Crear proyecto gratis en Supabase (supabase.com) 📅 2026-07-02 ⏫
- [ ] Ejecutar `supabase/schema.sql` en el SQL Editor de Supabase 📅 2026-07-02 ⏫
- [ ] Copiar `.env.example` → `.env` con la URL y la anon key 📅 2026-07-02 ⏫
- [ ] (Opcional) Desactivar "Confirm email" en Authentication para que ama entre fácil 📅 2026-07-02
- [ ] Probar: registro + añadir a la lista + ver cambios en tiempo real 📅 2026-07-02
- [ ] Revisar recetas/colores y ajustar a gusto 📅 2026-07-02

**🔜 Cuando esto funcione**
- [ ] Enchufar la API de Claude para autogenerar recetas que no existan
- [ ] Selección "qué tengo en casa" → sugerencias
- [ ] Panel de admin para enganchar el vídeo oficial concreto

---

## 🗂️ Relacionado
- [[Nutrición]]
- [[IA bot nutrición y deporte]]
- [[🗺️ Shopping List Recorder — MOC|Shopping List Recorder]]
- [[Inbox]]
