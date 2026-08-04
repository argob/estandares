---
description: Instrucciones operativas para que una IA audite la especificación, estructura y consistencia de endpoints y datos de APIs públicas.
tags:
- ia
- skill
- revision
- api
- interoperabilidad
timestamp: '2026-06-15T11:20:00-03:00'
title: 'Skill: Revisar una API pública'
type: Skill
---

## Objetivo

Evaluar si una API pública o de integración estatal es consistente, segura, documentada e interoperable.

## Cuándo usarla

Usar esta skill para revisar especificaciones OpenAPI, documentación, endpoints, ejemplos de request y response, contratos de integración o código relacionado con APIs.

## Instrucciones para la IA

1. Identificar el propósito de la API, sus consumidores esperados y su **Nivel de Criticidad** (Nivel 1: Público/Bajo riesgo, Nivel 2: Medio riesgo/Datos personales, Nivel 3: Crítico/Alto impacto).
2. Revisar recursos, nombres, métodos HTTP, parámetros, filtros, paginación, ordenamiento y versionado (verificar versión mayor en la ruta URL `/v1/` y versión SemVer completa `vX.Y.Z` en el contrato OpenAPI/Swagger o cabecera `X-API-Version`).
3. Revisar estructura de respuestas, códigos de estado HTTP estándar (2xx, 4xx, 5xx), metadata y auditar que las respuestas de error **no expongan trazas de código (*stack traces*)** ni detalles de infraestructura en producción.
4. Verificar documentación: autenticación (almacenamiento por hash SHA-256 de tokens y uso de prefijos por sistema como `mun_` para *secret-scanning*), permisos granulares en formato `recurso:accion`, uso de la cabecera `X-Client-Agent`, ejemplos, límites, datos de prueba (evitando datos reales de producción, según DA 641/2021), cambios y contacto.
5. Detectar exposición innecesaria de datos personales o sensibles, contrastando con el principio de minimización.
6. Revisar uso de HTTPS, **prohibición estricta de transmitir API Keys/tokens en URL o query string** (exigiendo cabeceras `Authorization: Bearer <token>` o `X-API-Key`), autorización restrictiva con exactamente una *ability* `recurso:accion` por endpoint (403 indicando el permiso faltante `required`), **respuestas 401 genéricas** (anti-enumeración), y **políticas CORS segmentadas** (permitida `*` únicamente en Nivel 1; whitelist o deshabilitada en server-to-server para Niveles 2 y 3).
7. Para APIs clasificadas en Nivel 2 o Nivel 3, verificar la confección y aprobación del **Documento de Requerimientos de Seguridad (DRSI)**, y auditar que el registro de llamadas (*api_call_logs*) sea pre-autenticación, inmutable y con retención acotada (90 días). Si además operan sobre Infraestructura Crítica (Res. 1523/2019), evaluar RTO/RPO, backups y continuidad (DA 641/2021 y Disp. 1/2026 del CNC).
8. Indicar riesgos de compatibilidad, ruptura de contrato o acoplamiento a sistemas internos.
9. Proponer mejoras concretas con ejemplos cuando corresponda.

## Formato de respuesta

```md
## Resumen técnico

Descripción breve de la API y su estado general.

## Hallazgos

- Severidad:
- Endpoint o sección:
- Evidencia:
- Impacto:
- Recomendación:
- Ejemplo sugerido:

## Riesgos de datos y seguridad

- Riesgo:
- Mitigación:

## Continuidad y operación

- Riesgo:
- Evidencia:
- Mitigación:

## Documentación faltante

- Elemento:
- Por qué importa:
```

## Referencias internas

- [APIs y datos](../lineamientos/apis-y-datos.md)
- [Seguridad y privacidad](../lineamientos/seguridad-y-privacidad.md)
