---
name: triaje-inbox-a-tasks
description: Lee correos no leídos en Gmail, filtra los que requieren acción y crea tareas en Google Tasks.
---

# Instrucciones de Ejecución

1. **Lectura de Gmail (vía Zapier):**
   - Busca los últimos 10 correos con estado `UNREAD` en la bandeja de entrada.
   - **Regla estricta (`AGENTS.md`):** No marques correos como leídos, no los elimines ni envíes respuestas automáticas.
2. **Clasificación:**
   - Descarta newsletters, notificaciones automáticas sin acción y publicidad.
   - Selecciona únicamente correos que exijan respuesta, entrega, revisión técnica o gestión administrativa.
3. **Creación en Google Tasks (vía Zapier):**
   - Para cada correo accionable, crea una tarea en la lista por defecto (`Mis tareas`):
     - **Título:** `[Gmail] <Acción concreta en infinitivo>`
     - **Notas:** `De: <Remitente> | Asunto: <Asunto> | Resumen: <Qué se necesita en 1-2 frases>`
4. **Reporte al Usuario:**
   - Devuelve en el chat un resumen breve con el número de correos revisados y el listado exacto de tareas añadidas a Google Tasks.
