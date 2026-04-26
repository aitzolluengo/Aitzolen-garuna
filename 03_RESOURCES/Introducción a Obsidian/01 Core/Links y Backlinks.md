
> El corazón de Obsidian. Lo que convierte notas sueltas 
> en un segundo cerebro conectado.

## ¿Qué es un Link?

Un enlace entre dos notas. Se crea escribiendo `[[nombre de la nota]]`.

Cuando enlazas notas, construyes conexiones entre ideas —
igual que funciona tu memoria.

## Tipos de links

### Wikilink (el estándar)

[[Conceptos Clave]]

Enlaza directamente a esa nota. Si no existe, la crea al hacer clic.

### Link con alias (texto personalizado)
[[Conceptos Clave|ver conceptos]]

El link apunta a `Conceptos clave` pero muestra `ver conceptos`.

### Link a sección específica

[[Conceptos Clave#Tags]]

Abre la nota y salta directamente al encabezado `Tags`.

### Link a bloque específico
[[Conceptos Clave#^id-del-bloque]]

Para referenciar un párrafo concreto dentro de una nota.

### Link externo (URL)
[texto visible](https://obsidian.md)

## ¿Qué es un Backlink?

Cuando creas `[[Conceptos clave]]` en esta nota, Obsidian 
registra automáticamente en `Conceptos clave` que esta nota 
la referencia. Eso es un backlink.

**Sin hacer nada extra, cada nota sabe quién habla de ella.**

## Cómo ver los Backlinks

- Panel derecho → sección **Backlinks**
- Muestra todas las notas que enlazan a la nota actual
- También muestra **Unlinked mentions** — notas que mencionan 
  el nombre pero sin link formal

## Unlinked Mentions

Obsidian detecta cuando escribes el nombre de una nota 
sin usar `[[]]`. Te lo muestra en el panel de backlinks 
para que puedas convertirlo en link con un clic.

Muy útil cuando capturas rápido sin parar a crear links.

## Flujo de trabajo real

### Al escribir una nota nueva:
1. Escribe con libertad
2. Cuando menciones un concepto que tiene (o merece) nota propia → `[[concepto]]`
3. No fuerces links — solo los naturales

### Al revisar notas antiguas:
1. Abre el panel de Backlinks
2. Revisa Unlinked Mentions
3. Convierte en links los que tengan sentido

## Buenas prácticas
- Enlaza hacia notas que **ya existen** o que **deberían existir**
- Un link vacío (nota no creada) está bien — es una deuda de conocimiento
- No abuses: 2-5 links por nota es suficiente al principio
- Los links más valiosos son los **inesperados** — cuando conectas 
  ideas de áreas distintas


## Relacionado
- [[Conceptos Clave]]
- [[Graph View]]
- [[Tags]]