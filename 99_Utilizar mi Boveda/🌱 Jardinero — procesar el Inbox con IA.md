---
fecha: 2026-07-01
tags:
  - sistema
---

# 🌱 Jardinero — procesar el Inbox con IA

El **Jardinero** es un agente de Claude Code que vacía la *Captura rápida* de mi [[Inbox]]: coge lo que apunto suelto, lo clasifica y lo lleva a su carpeta con el frontmatter correcto. Es la parte de **procesar** de mi [[Flujo de trabajo]], pero automatizada.

> [!tip] La idea
> Yo **capturo** en Obsidian (libre y diario). El Jardinero **ordena** desde Claude Code cuando yo se lo pido (idealmente el domingo).

---

## 1. Capturar (en Obsidian, como siempre)

Cuando se me ocurra algo, lo escribo en el [[Inbox]] bajo `## Captura rapida`, con su tag. No me preocupo de dónde va — para eso está el Jardinero.

```
- [ ] Comprar cuerdas para el bajo #musica
- [ ] Vi Dune 2, registrarla #cine
- [ ] Idea: app para contar remadas #rowing
- [ ] Regalo para el aita, unos calcetines #compras
```

---

## 2. Procesar (en Claude Code)

Abro Claude Code dentro del vault y escribo:

```
/jardinero
```

O simplemente le digo *"procesa el inbox"* o *"jardinero"*.

El agente:
1. **Lee** la Captura rápida.
2. **Me enseña un plan** (dry-run): qué clasifica como qué y dónde lo pondría. **No toca nada todavía.**
3. Yo digo **OK** (o le corrijo algún destino).
4. **Aplica**: crea las notas con su frontmatter, mueve las tareas a su proyecto/área, y **limpia el Inbox** de lo ya procesado.

> [!warning] Seguro por diseño
> Nunca escribe sin enseñarme antes el plan, y nunca borra algo que no haya procesado.

---

## 3. Cómo clasifica (por tag)

| Tag | Va a… |
|---|---|
| `#tfg` | Proyecto Think&DoIT |
| `#rowing` | Proyecto Rowing Fantasy |
| `#ingles` | Área Aprendizaje / B2 |
| `#musica` | Área Bajo / Música |
| `#kirola` | Área Deporte |
| `#cine` (peli concreta) | Sistema de Cine (nota de película) |
| `#compras` / regalo / recado | `03_RESOURCES/Compras/` |
| `#personal` | Se queda como tarea con fecha |
| Idea nueva sin desarrollar | `00_JARDIN DIGITAL/01🌱 Semillas/` |

**Reglas:**
- Si es una **tarea de un proyecto/área**, la mueve como `- [ ]` a esa nota.
- Si es una **idea para desarrollar**, crea una **semilla** del jardín.
- Si **duda**, me pregunta. No se inventa nada.
- Respeta prioridad (`⏫`/`⏬`), fechas (`📅`) y enlaces (`[[...]]`).

---

## 4. Qué se queda pendiente

Algunas capturas necesitan datos que solo tengo yo. Por ejemplo `Registrar pelis #cine`: sin los títulos no puede crear las notas de película. En esos casos **lo deja en el Inbox** y me pide la info.

---

## Relacionado
- [[Inbox]]
- [[Flujo de trabajo]]
- [[Cómo usar este vault]]
