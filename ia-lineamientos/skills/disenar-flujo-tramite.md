---
description: Instrucciones operativas para estructurar o rediseñar flujos de trámites centrados en las necesidades del ciudadano.
tags:
- ia
- skill
- diseno
- tramites
timestamp: '2026-06-15T11:20:00-03:00'
title: 'Skill: Diseñar o mejorar un flujo de trámite'
type: Skill
---

## Objetivo

Ayudar a estructurar un trámite digital o multicanal para que sea comprensible, completable y medible.

## Cuándo usarla

Usar esta skill cuando se diseña un trámite nuevo, se migra un trámite presencial a digital, se mejora un formulario existente o se reduce abandono.

## Instrucciones para la IA

1. Definir tarea, público, resultado esperado y organismo responsable.
2. Separar información previa, inicio, carga de datos, adjuntos, revisión, confirmación, seguimiento y cierre.
3. Identificar datos y documentos necesarios, opcionales y obtenibles por interoperabilidad.
4. Proponer pasos cortos con labels claros y ayudas contextuales.
5. Diseñar estados: borrador, enviado, observado, en revisión, aprobado, rechazado, vencido o finalizado según corresponda.
6. Definir errores recuperables y mensajes claros.
7. Considerar accesibilidad, dispositivos móviles, baja conectividad y atención alternativa.
8. Para trámites esenciales o de alto impacto, definir alternativa operativa ante indisponibilidad, mensajes de contingencia, responsables de escalamiento y requisitos de recuperación del servicio.
9. Proponer indicadores para medir éxito, abandono y tiempos.

## Formato de respuesta

```md
## Flujo propuesto

1. Paso:
   - Objetivo:
   - Datos:
   - Validaciones:
   - Mensajes:

## Datos y documentos

- Dato/documento:
- Obligatorio:
- Justificación:
- Fuente alternativa:

## Estados del trámite

- Estado:
- Qué ve la persona:
- Acción disponible:

## Riesgos y mitigaciones

- Riesgo:
- Mitigación:

## Contingencia

- Escenario de indisponibilidad:
- Alternativa para la persona:
- Responsable o validación necesaria:
```

## Referencias internas

- [Servicios digitales](../lineamientos/servicios-digitales.md)
- [Contenido y lenguaje claro](../lineamientos/contenido-y-lenguaje-claro.md)
- [Accesibilidad](../lineamientos/accesibilidad.md)
- [Seguridad y privacidad](../lineamientos/seguridad-y-privacidad.md)
