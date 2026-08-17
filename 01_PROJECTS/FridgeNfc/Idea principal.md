# FridgeNFC

Stickers NFC en la nevera o armarios que, al escanearlos, abren una lista compartida de lo que falta en casa. Cualquier miembro de la familia puede marcar, añadir o eliminar items en tiempo real desde su móvil.

---

## Problema

La lista de la compra se fragmenta — cada uno apunta cosas en sitios distintos o directamente no las apunta. El NFC elimina la fricción: ves que falta algo, pegas el móvil al sticker, lo apuntas. Sin app instalada, sin cuenta.

---

## Concepto clave

Cada familia tiene un **ID único** codificado en la URL del sticker NFC:

```
https://usuario.github.io/fridgenfc?id=abc123
```

Todos los que escaneen ese sticker comparten la misma lista. Para tener otra lista (nevera, bodega, armario) se usa otro sticker con otro ID.

---

## Stack

| Capa | Tecnología | Por qué |
|---|---|---|
| Frontend | HTML + JS vanilla | Sin build, sin dependencias, carga rápida en móvil |
| Backend / sync | Firebase Realtime DB | Gratis, tiempo real, sin servidor |
| Hosting | GitHub Pages | Gratis, desde el repo |
| NFC | NFC Tools (app móvil) | Para programar la URL en el sticker |

---

## Flujo de uso

1. Usuario escanea sticker NFC con el móvil
2. Se abre la webapp con la lista de esa nevera (`?id=abc123`)
3. Ve los items pendientes en tiempo real
4. Puede marcar como comprado, añadir o eliminar
5. El cambio se refleja al instante en el móvil de cualquier otro miembro

---

## UI (mínima viable)

- Lista de items con checkbox
- Input para añadir item nuevo
- Tap en item → tachado / marcado como comprado
- Botón para limpiar los comprados
- Sin login, sin onboarding

---

## Arquitectura Firebase

```
/listas
  /abc123          ← ID de la familia
    /items
      /item1: { nombre: "Leche", comprado: false }
      /item2: { nombre: "Huevos", comprado: true }
```

El ID se genera aleatoriamente la primera vez que alguien crea una lista y se guarda en la URL del sticker.

---

## Despliegue

1. Crear repo en GitHub → activar GitHub Pages
2. Configurar proyecto Firebase (Realtime DB, reglas públicas de lectura/escritura)
3. Añadir config de Firebase al `index.html`
4. Generar un ID aleatorio para la lista → construir la URL
5. Programar el sticker NFC con NFC Tools
6. Pegar el sticker en la nevera

---

## Preguntas abiertas

- [ ] ¿Límite de items por lista?
- [ ] ¿Cómo comparte alguien la URL sin sticker? (link directo como fallback)
- [ ] ¿Historial de lo que se compró o solo lista activa?
- [ ] ¿Varios stickers por casa (nevera, bodega)? → mismo ID o IDs distintos
- [ ] ¿Nombre de la lista visible en la UI?

---

## Próximos pasos

- [ ] Crear repo GitHub
- [ ] Crear proyecto Firebase y obtener config
- [ ] `index.html` básico con lectura/escritura a Firebase
- [ ] Probar con URL manual antes de programar el sticker
- [ ] Programar sticker y pegar
