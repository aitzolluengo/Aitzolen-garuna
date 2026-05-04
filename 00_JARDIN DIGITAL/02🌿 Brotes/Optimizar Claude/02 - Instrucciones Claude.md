---
tags: [claude, instrucciones, programacion, eficiencia]
aliases: [Las 13 instrucciones, Reglas para Claude Code]
---

# Las 13 Instrucciones para Optimizar Claude

> [!NOTE] Enlace relacionado
> Esta nota forma parte de [[Exprimir-Claude-20-dolares]].

Aquí tienes la lista detallada de cada instrucción mencionada en el video, con su explicación de por qué es importante:

1.  **No programar sin contexto**
    - **Qué hace:** Obliga a la IA a leer y entender los archivos relevantes del proyecto *antes* de escribir código.
    - **Objetivo:** Evitar soluciones que no encajan en la base de código existente.

2.  **Respuestas cortas**
    - **Qué hace:** Pide explicaciones mínimas. "Di lo necesario, nada más".
    - **Objetivo:** Ahorrar tokens en respuestas que no son código puro, siendo ultra-conciso.

3.  **No reescribir archivos completos**
    - **Qué hace:** Instruye a usar herramientas de reemplazo selectivo en lugar de volcar todo el archivo de nuevo con un pequeño cambio.
    - **Objetivo:** Eficiencia máxima al modificar código, reduciendo drásticamente los tokens de salida.

4.  **No releer archivos ya leídos**
    - **Qué hace:** Le indica que *recuerde y confíe* en lo que ya ha leído en la misma conversación.
    - **Objetivo:** No volver a solicitar el archivo, manteniendo el contexto sin gasto extra.

5.  **Validar antes de declarar hecho**
    - **Qué hace:** Le exige ejecutar código de prueba o verificaciones para confirmar que su solución funciona.
    - **Objetivo:** Pasar de "parece correcto" a "está verificado", evitando bugs por falso positivismo.

6.  **Cero charla aduladora**
    - **Qué hace:** Elimina frases como "¡Gran idea!", "Excelente pregunta". Va directo al grano.
    - **Objetivo:** Comunicación puramente transaccional y profesional, sin halagos que gastan tokens.

7.  **Soluciones simples**
    - **Qué hace:** Buscar siempre la implementación más sencilla y directa.
    - **Objetivo:** Evitar la sobreingeniería y soluciones complejas cuando una simple basta.

8.  **No pelear con el usuario**
    - **Qué hace:** Si el usuario pide algo raro o contradictorio, debe ejecutarlo sin intentar "corregir" al usuario con un sermón.
    - **Objetivo:** Reducir la fricción y el gasto en tokens en debates innecesarios.

9.  **Leer solo lo necesario**
    - **Qué hace:** Al buscar contexto, leer archivos específicos y partes concretas, no todo el proyecto.
    - **Objetivo:** No saturar el contexto de la IA con información irrelevante.

10. **No narrar el plan**
    - **Qué hace:** No explica *lo que va* a hacer ("Ahora voy a modificar la función X...").
    - **Objetivo:** Simplemente lo hace y lo muestra, eliminando texto introductorio innecesario.

11. **Paralelizar tool calls**
    - **Qué hace:** Cuando sea posible, ejecutar varias herramientas independientes al mismo tiempo (ej: leer tres archivos a la vez).
    - **Objetivo:** Reducir la latencia y acelerar la ejecución de tareas.

12. **No duplicar código en la respuesta**
    - **Qué hace:** Prohíbe mostrar el código ya existente en su totalidad; solo muestra las partes que cambian o se añaden.
    - **Objetivo:** Minimizar los tokens de salida, mostrando solo el "diff" o los fragmentos clave.

13. **No usar Agent innecesariamente**
    - **Qué hace:** No lanzar sub-agentes autónomos para tareas simples que puede hacer directamente en un solo paso.
    - **Objetivo:** Evitar la complejidad y el gasto extra de gestionar agentes para tareas triviales.