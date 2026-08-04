---
description: Instrucciones operativas para auditar planes de contingencia y recuperación ante desastres en infraestructuras y servicios críticos.
tags:
- ia
- skill
- revision
- ciberseguridad
- continuidad-operativa
timestamp: '2026-06-15T11:20:00-03:00'
title: 'Skill: Revisar continuidad operativa y recuperación'
type: Skill
---

## Objetivo

Evaluar si un servicio, sistema, API o infraestructura pública cuenta con criterios mínimos de continuidad operativa, recuperación ante incidentes y resiliencia.

## Cuándo usarla

Usar esta skill cuando se revise un sistema crítico, un servicio esencial, una infraestructura de datos, un centro de procesamiento, una API de alto impacto, un plan de contingencia o un Plan de Recuperación ante Desastres (PRD).

## Instrucciones para la IA

1. Identificar el organismo, sistema, servicio o infraestructura revisada y si pertenece al Sector Público Nacional u otro ámbito, determinando si califica como Infraestructura Crítica de Información según los sectores de la Resolución 1523/2019.
2. Determinar la criticidad estimada: alta, media o baja, según impacto en personas, continuidad de servicios, datos, obligaciones legales, operación institucional y reputación, justificándolo en base a los criterios de impacto de la Resolución 1523/2019 (vida humana, económico, social, funciones del Estado, soberanía, etc.).
3. Revisar si existe inventario del sistema y de sus dependencias: aplicaciones, datos, infraestructura, proveedores, enlaces y responsables.
4. Verificar si hay RTO, RPO, orden de recuperación y recursos necesarios definidos y aprobados.
5. Revisar estrategia de respaldo y recuperación: backups, replicación, sitio alternativo, conmutación, restauración y retorno a la normalidad (según Directriz 13 de la DA 641/2021 y requerimientos de la Disp. 1/2026 del CNC).
6. Revisar roles, contactos, escalamiento, autoridad para declarar contingencia y coordinación con seguridad, comunicaciones, soporte y proveedores.
7. Revisar playbooks específicos para escenarios relevantes, incluyendo ransomware, caída de infraestructura, pérdida de datos, indisponibilidad de proveedor y desastre físico.
8. Verificar controles de seguridad durante la recuperación: autenticación, segmentación, cifrado, monitoreo, protección de evidencia forense y seguridad física.
9. Revisar registro de incidentes, playbooks de escalamiento y el cumplimiento de los plazos de notificación (reporte obligatorio a la Dirección Nacional de Ciberseguridad dentro de las 48 horas de detectado un incidente, según la Directriz 12 de la DA 641/2021), evidencias de pruebas, resultados, métricas, remediaciones y actualización del plan.
10. Diferenciar hallazgos técnicos, buenas prácticas y obligaciones normativas. Recomendar validación jurídica cuando el alcance legal no sea claro.

## Formato de respuesta

```md
## Resumen

Sistema o servicio revisado, criticidad estimada y principal brecha de continuidad.

## Alcance y criticidad

- Alcance:
- Dependencias principales:
- Criticidad estimada:
- Justificación:

## Hallazgos

- Severidad:
- Evidencia:
- Impacto:
- Recomendación:
- Validación necesaria:

## RTO/RPO y recuperación

- Sistema o componente:
- RTO:
- RPO:
- Estrategia de recuperación:
- Brecha:

## Pruebas y evidencias

- Prueba o evidencia esperada:
- Estado:
- Próxima acción:


- Norma aplicable:
- Criterio que sostiene:
- Alcance o duda a validar:
```

## Referencias internas

- [Seguridad y privacidad](../lineamientos/seguridad-y-privacidad.md)
- [Servicios digitales](../lineamientos/servicios-digitales.md)
- [APIs y datos](../lineamientos/apis-y-datos.md)
- [Marco normativo](../marco-normativo.md)
