---
name: briefing-github-diario
description: Consulta commits recientes e issues abiertos en GitHub y envía un briefing técnico por Telegram.
---

# Instrucciones de Ejecución

1. **Consulta en GitHub (vía Zapier):**
   - Obtén los últimos 5 commits y los issues abiertos en los repositorios activos del usuario.
   - Si el usuario especificó un repositorio en su mensaje, filtra exclusivamente por ese repositorio.
2. **Síntesis y Priorización:**
   - Agrupa los cambios por repositorio.
   - Identifica si hay algún issue bloqueante o PR pendiente de revisión.
   - Propón 1 única acción prioritaria para arrancar la jornada.
3. **Envío por Telegram:**
   - Envía el resumen al chat de Telegram del usuario usando este formato exacto:
     ```markdown
     ⚙️ *Briefing GitHub*
     *Commits recientes:*
     - [Repo] Mensaje de commit (autor)
     *Issues abiertos:*
     - #ID Título del issue
     *Foco recomendado:* <acción concreta>
     ```
4. **Verificación:** Confirma en la sesión actual que el mensaje fue enviado a Telegram.
