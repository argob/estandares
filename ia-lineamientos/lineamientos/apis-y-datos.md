---
description: Estándares de interoperabilidad, documentación de endpoints y publicación segura de datos públicos.
tags:
- ia
- lineamiento
- api
- datos
- interoperabilidad
timestamp: '2026-06-15T11:20:00-03:00'
title: Lineamientos de APIs y datos para IA
type: Lineamiento
---

Estos lineamientos orientan a una IA que diseña, documenta o revisa APIs y estructuras de datos públicas.

## Objetivo

Promover APIs seguras, interoperables, documentadas y fáciles de consumir por equipos públicos, terceros autorizados y servicios digitales.

## Criterios

### Recursos claros

La IA debe proponer endpoints basados en recursos, con nombres consistentes, estables y comprensibles. Debe evitar verbos innecesarios en URLs y estructuras que dependan de detalles internos del organismo.

### Métodos y respuestas previsibles

La IA debe revisar que los métodos HTTP se usen de forma coherente y que las respuestas de error utilicen la familia estándar de códigos HTTP (2xx, 4xx, 5xx) con un cuerpo JSON estructurado, prohibiendo expresamente la exposición de trazas de código (*stack traces*) o consultas a bases de datos en entornos productivos.

### Documentación

La IA debe promover documentación con descripción funcional, autenticación, permisos, parámetros, ejemplos, códigos de estado, errores, límites, versionado, datos de prueba y contacto técnico.

### Seguridad y privacidad

La IA debe advertir cuando una API expone datos personales innecesarios, usa canales inseguros, carece de autenticación adecuada, o **transmite credenciales, API keys o tokens en la URL/query string** (exigiendo el uso de cabeceras seguras como `Authorization: Bearer <token>` o `X-API-Key`). Asimismo, debe verificar:
* **Almacenamiento de Tokens**: Exigir que los tokens se almacenen únicamente mediante hash **SHA-256** (`token_hash`) y que se generen con prefijos por sistema (ej. `mun_`) para permitir el escaneo automático de secretos (*secret-scanning*).
* **Respuestas 401 Genéricas**: Verificar que los fallos de autenticación 401 utilicen mensajes genéricos para evitar la enumeración de credenciales válidas.
* **Políticas CORS**: Validar que las políticas CORS se segmenten según el Nivel de Criticidad (permitida `*` únicamente en Nivel 1; restringida con *whitelist* de dominios o deshabilitada para integraciones servidor a servidor en Niveles 2 y 3).

### Permisos Granulares (Abilities / Scopes)

La IA debe validar que los permisos se definan con el formato **`recurso:accion`** (`read`, `write`, `delete`, `admin`), que cada endpoint exija exactamente una *ability* y que las respuestas HTTP 403 Forbidden incluyan en el JSON el permiso faltante (`required`).

### Identificación de Cliente y Logging de Llamadas

La IA debe promover el uso de la cabecera **`X-Client-Agent`** para aplicaciones móviles o de plataforma, y verificar que el registro de auditoría de llamadas (*api_call_logs*) sea pre-autenticación, inmutable y cuente con política de retención (90 días) sin registrar secretos ni datos personales.

### Clasificación y Documentación de Seguridad (DRSI)

La IA debe verificar la clasificación por Nivel de Criticidad (Nivel 1: Público/Bajo riesgo, Nivel 2: Medio riesgo/Datos personales, Nivel 3: Crítico/Alto impacto) y requerir la confección y aprobación previa del Documento de Requerimientos de Seguridad (DRSI) para toda API clasificada en Nivel 2 o Nivel 3.

### Disponibilidad y recuperación

La IA debe revisar si la API documenta criticidad, acuerdos de disponibilidad, límites de uso, monitoreo, manejo de degradación, respaldos de datos, recuperación ante incidentes y dependencias críticas. Para APIs que sostienen servicios esenciales, debe pedir evidencia de RTO/RPO, pruebas de restauración y procedimientos de continuidad.

### Versionado y compatibilidad

La IA debe exigir el uso de la versión mayor en la ruta de la URL (`/v1/`, `/v2/`) para evitar la ruptura de contratos de integración ante cambios retrocompatibles, manteniendo el versionado SemVer completo (`vX.Y.Z`) en el contrato OpenAPI/Swagger o cabeceras HTTP (`X-API-Version`).

### Interoperabilidad

La IA debe recomendar formatos abiertos, codificaciones estándar, fechas normalizadas, identificadores estables y catálogos compartidos cuando existan.

## Preguntas de revisión

- ¿La API resuelve una necesidad de servicio o integración clara?
- ¿Los recursos y parámetros son consistentes?
- ¿Hay documentación suficiente para consumirla sin asistencia informal?
- ¿Los errores son accionables?
- ¿Hay paginación, filtros, ordenamiento y límites?
- ¿Se protegen datos personales y credenciales?
- ¿Existe ambiente de prueba o ejemplos reproducibles?
- ¿Hay monitoreo, alertas y procedimientos de recuperación ante caídas?
- ¿Los datos críticos tienen respaldo, replicación o restauración probada?


[1] [Decreto 87/2017](https://www.argentina.gob.ar/normativa/nacional/decreto-87-2017-271486/actualizacion) - Plataforma Digital del Sector Público Nacional.
[2] [Resolución 333/2017](https://www.argentina.gob.ar/normativa/nacional/resoluci%C3%B3n-333-2017-276568/texto) - estándares web y aplicaciones móviles.
[3] [Disposición 24/2019](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-24-2019-332833/texto) - cuando corresponda reutilización o publicación de código.
[4] [Disposición 1/2026 del Centro Nacional de Ciberseguridad](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-1-2026-425749/texto) - cuando corresponda continuidad, PRD, infraestructura de respaldo o sistemas críticos.
