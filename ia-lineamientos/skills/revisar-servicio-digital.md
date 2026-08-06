---
description: Instrucciones operativas para que una IA evalúe la simplicidad, accesibilidad y consistencia de un servicio digital.
tags:
- ia
- skill
- revision
- servicios-digitales
timestamp: '2026-06-15T11:20:00-03:00'
title: 'Skill: Revisar un servicio digital público'
type: Skill
---

## Objetivo

Evaluar si un servicio digital público es claro, accesible, seguro, medible y consistente entre canales.

## Cuándo usarla

Usar esta skill para revisar páginas de trámite, flujos de servicio, formularios, aplicaciones, pantallas de seguimiento, turnos o servicios multicanal.

## Instrucciones para la IA

1. Identificar la tarea principal de la persona usuaria.
2. Revisar si la información responde qué es, a quién corresponde, requisitos, pasos, costo, plazo, resultado y canales de ayuda.
3. Detectar requisitos, documentos o datos personales que parezcan innecesarios o repetidos. Evaluar si la solicitud de datos cumple con la minimización y el principio de "necesidad de saber" (DA 641/2021).
4. Revisar si el flujo contempla inicio, confirmación, seguimiento, errores, consultas y cierre.
5. Evaluar consistencia entre canales cuando haya web, app, teléfono, turnos, presencialidad o asistente conversacional.
6. Identificar barreras de accesibilidad, lenguaje, conectividad, ubicación geográfica o disponibilidad documental. Si el servicio o sitio web incluye mapas de la República Argentina, verificar el uso obligatorio de los mapas base del servicio ARGENMAP (IGN) de conformidad con la DA 797/2022.
7. Determinar la clasificación por **Nivel de Criticidad** del servicio (Nivel 1: Bajo/Público, Nivel 2: Medio/Datos Personales o Registrales, Nivel 3: Alto/Crítico). Para todo servicio clasificado en Nivel 2 o 3, verificar la confección, aprobación y publicación del **Documento de Requerimientos de Seguridad (DRSI)** previo al pase a producción. Si el servicio es además esencial o masivo (Res. 1523/2019), revisar responsables de continuidad, RTO/RPO, backups, pruebas de recuperación y playbooks de incidentes (DA 641/2021 y Disp. 1/2026 del CNC).
8. Proponer indicadores de mejora y monitoreo.
9. Priorizar hallazgos por impacto en la persona usuaria y riesgo institucional.

## Formato de respuesta

```md
## Resumen

Breve descripción del servicio revisado y su principal riesgo u oportunidad.

## Hallazgos

### Crítico
- Evidencia:
- Impacto:
- Recomendación:

### Alto
- Evidencia:
- Impacto:
- Recomendación:

### Medio
- Evidencia:
- Impacto:
- Recomendación:

### Bajo
- Evidencia:
- Impacto:
- Recomendación:

## Indicadores sugeridos

- Indicador:
- Por qué importa:

## Continuidad operativa

- Criticidad estimada:
- Evidencia disponible:
- Brecha o validación necesaria:

## Supuestos y validaciones necesarias

- Supuesto o punto a validar:
```

## Referencias internas

- [Lineamientos de servicios digitales](../lineamientos/servicios-digitales.md)
- [Contenido y lenguaje claro](../lineamientos/contenido-y-lenguaje-claro.md)
- [Accesibilidad](../lineamientos/accesibilidad.md)
- [Seguridad y privacidad](../lineamientos/seguridad-y-privacidad.md)
