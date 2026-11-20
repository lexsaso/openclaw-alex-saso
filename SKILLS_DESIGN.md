# Diseño de Skills Personalizadas — OpenClaw

Este documento define la arquitectura funcional de las skills personalizadas antes de su implementación en el directorio `skills/`.

---

## Skill 1: `briefing-github-diario`

1. **¿Qué hace esta skill?**
   Recopila los issues abiertos y los últimos commits de mis repositorios activos en GitHub y me envía un resumen ejecutivo accionable por Telegram.
2. **¿Qué input necesita el agente?**
   - **Input del usuario:** Una orden breve como `"dame el briefing de GitHub"` o `"resumen diario de repos"` (opcionalmente indicando el nombre de un repositorio específico).
   - **Contexto previo (de los 5 archivos):** A partir de `USER.md`, `TOOLS.md` y `SOUL.md`, el agente sabe qué repositorios priorizar, que debe usar la conexión de GitHub y Telegram vía Zapier, y que el tono debe ser técnico, directo y sin relleno.
3. **¿Cómo es un buen output?**
   - **Formato:** Mensaje corto en Markdown (< 1.200 caracteres) dividido en: *Commits recientes*, *Issues pendientes* y *Siguiente paso recomendado*.
   - **Destino:** Chat directo en **Telegram**.
   - **Criterio de éxito:** Recibo la notificación en Telegram con enlaces o identificadores reales de mis commits/issues y sin ningún dato sensible expuesto.

---

## Skill 2: `triaje-inbox-a-tasks`

1. **¿Qué hace esta skill?**
   Analiza los correos no leídos en Gmail, filtra los que requieren una acción real por mi parte y crea automáticamente una tarea estructurada en Google Tasks para cada uno.
2. **¿Qué input necesita el agente?**
   - **Input del usuario:** Comando `"revisa mi bandeja"` o `"triaje de correos"` (opcionalmente con límite de correos, por defecto los últimos 10 no leídos).
   - **Contexto previo (de los 5 archivos):** De `USER.md` conoce mis proyectos y prioridades (IA, formación, desarrollo); de `TOOLS.md` sabe usar Gmail (solo lectura) y Google Tasks (lista `Mis tareas`); de `AGENTS.md` respeta la regla de no responder ni borrar correos automáticamente.
3. **¿Cómo es un buen output?**
   - **Formato:** Lista de tareas creadas en Google Tasks con título en infinitivo (`[Email] Responder a...`), notas con el remitente y resumen en 2 líneas, más un breve reporte en chat de cuántos correos se procesaron y cuántos se descartaron por ser boletines/spam.
   - **Destino:** **Google Tasks** (lista por defecto) + confirmación en la sesión activa.
   - **Criterio de éxito:** Las tareas accionables aparecen visibles en mi lista de Google Tasks con contexto suficiente para ejecutarlas sin abrir Gmail de inmediato.
