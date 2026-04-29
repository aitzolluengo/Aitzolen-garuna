---
tags:
  - tipo/referencia
  - gemini/cli
---

# Cómo Usar Gemini CLI

Gemini CLI es tu asistente de IA diseñado para ayudarte con tareasdirectamente desde la línea de comandos. Funciona siguiendo un ciclo de **Investigación -> Estrategia -> Ejecución**.

## Interacción Básica

Simplemente escribe tus instrucciones o preguntas. Gemini intentará entender tu intención y utilizará sus herramientas para ayudarte.

### Entendiendo la Conversación
*   **Contexto:** Gemini mantiene el contexto de toda la conversación. Puedes hacer preguntas de seguimiento o pedirle que continúe con una tarea.
*   **Herramientas:** Gemini tiene acceso a herramientas como:
    *   `read_file`: Leer el contenido de archivos.
    *   `write_file`, `replace`: Modificar archivos.
    *   `grep_search`, `glob`: Buscar contenido o archivos en tu codebase.
    *   `run_shell_command`: Ejecutar comandos de terminal.
    *   `invoke_agent`: Delegar tareas a agentes especializados para trabajos complejos.
    *   `update_topic`: Para informarte sobre el progreso y los cambios de tema.
    *   Y muchas más para interactuar con tu entorno.

### Workflow General

1.  **Investigación:** Gemini puede explorar tu codebase para entender la estructura, los patrones existentes y las convenciones. Utiliza herramientas de búsqueda (`grep_search`, `glob`) y lectura (`read_file`).
2.  **Estrategia:** Una vez que entiende el problema o la tarea, formulará un plan de acción.
3.  **Ejecución:** Implementará el plan, que puede incluir:
    *   **Plan -> Act -> Validar:** Para cada sub-tarea, definirá un enfoque de implementación y una estrategia de prueba, aplicará los cambios y luego validará con pruebas o comandos.

## Qué Puedes Pedirle a Gemini CLI

*   **Análisis de Código:** Preguntas sobre cómo funciona una parte de tu código, identificar dependencias, etc.
*   **Refactorización:** Pedirle que realice refactorizaciones específicas.
*   **Implementación de Features:** Tareas de desarrollo, como añadir una nueva funcionalidad.
*   **Corrección de Bugs:** Investigar y solucionar errores.
*   **Generación de Tests:** Crear o actualizar pruebas para tu código.
*   **Automatización de Tareas:** Ejecutar comandos de shell complejos o repetitivos.
*   **Documentación:** Ayudarte a entender o generar documentación.
*   **Entender tu Vault:** Como estás haciendo ahora, Gemini puede leer tus notas para entender tu contexto.

## Consejos para una Mejor Interacción

*   **Sé Claro y Específico:** Cuanto más clara sea tu instrucción, mejor podrá ayudarte Gemini.
*   **Proporciona Contexto:** Si la tarea es compleja, explícale el contexto o los archivos relevantes.
*   **Usa el Flujo de Conversación:** No necesitas repetir información que ya le has dado en turnos anteriores.
*   **Confirma sus Preguntas:** Si Gemini te hace una pregunta, respóndela para guiarlo.
*   **Sé Paciente:** Algunas tareas complejas pueden requerir varios pasos y turnos.

Este asistente está diseñado para ser un par de programación, ayudándote a ser más eficiente y productivo.
