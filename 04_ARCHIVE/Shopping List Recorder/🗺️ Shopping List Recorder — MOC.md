---
fecha_inicio: 2026-05-16
estado: activo
tags:
  - tipo/proyecto
---

# 🗺️ Shopping List Recorder — Mapa del Proyecto

> Sistema de gestión de compras familiar con IA: de la lista simple al asistente proactivo. Reduce la carga mental de "qué falta" y "a quién le toca comprarlo".

---

## 📌 Estado rápido

| Campo | Valor |
|---|---|
| Estado | 🟡 Planificación |
| Fase actual | Diseño conceptual |
| Implementación | Sin empezar |

---

## 💡 La idea

Cualquier integrante notifica un cambio por voz o texto ("Se acabó el café", "He comprado la leche"). Un agente central analiza la intención, actualiza la lista compartida y gestiona los estados automáticamente.

### Flujo de valor

1. **Captura natural** — voz o texto desde el móvil
2. **Procesamiento IA** — agente actualiza la lista y gestiona estados
3. **Gestión inteligente** — asignación automática, recordatorios, turnos
4. **Sincronización** — todos ven el mismo estado en tiempo real

### Roles

- **Integrantes (4):** emiten información, interactúan con la IA como si fuera un miembro del chat
- **Líder:** supervisión, reasignación y cambios forzados en la planificación

### Diferenciadores técnicos

- **Bidireccional:** la IA no solo recibe, empuja notificaciones al responsable
- **Memoria contextual:** recuerda quién compró qué para asignación justa y rotativa
- **Sin fricción:** lenguaje natural → base de datos centralizada

---

## 🔧 Arquitectura conceptual

1. **Interfaz** — App móvil sencilla (lista + chat)
2. **Cerebro** — Agente IA con acceso de lectura/escritura a BD compartida
3. **Comunicación** — Sistema de notificaciones vinculado al responsable

---

## 🔜 Próximos pasos

- [x] Decidir stack tecnológico ✅ 2026-06-29
- [x] Elegir canal de comunicación (WhatsApp bot, Telegram, app propia) ✅ 2026-06-29
- [x] Definir modelo de datos (lista, estados, historial) ✅ 2026-06-29
- [x] Prototipo mínimo: captura + actualización de lista ✅ 2026-06-29

---

## 🗂️ Notas del proyecto

> Sin notas aún — proyecto en fase inicial.
