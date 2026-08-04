---
description: Pautas de protección de datos, ciberseguridad y privacidad en sistemas de administración pública nacional.
tags:
- ia
- lineamiento
- seguridad
- privacidad
timestamp: '2026-06-15T11:20:00-03:00'
title: Lineamientos de seguridad y privacidad para IA
type: Lineamiento
---

Estos lineamientos orientan a una IA que revisa servicios digitales, contenidos, formularios, APIs o asistentes que tratan datos de personas.

## Objetivo

Reducir riesgos de exposición indebida de datos, accesos no autorizados, uso excesivo de información personal, decisiones automatizadas sin control humano suficiente e indisponibilidad de servicios críticos.

## Criterios

### Minimización de datos

La IA debe cuestionar cada dato solicitado: para qué se usa, si es obligatorio, si ya está disponible por otra vía, cuánto tiempo se conserva y quién puede acceder.

### Transparencia

La IA debe recomendar que las personas sepan que datos se solicitan, con qué finalidad, quién los trata, qué consecuencias tiene no aportarlos y qué canales existen para consultas o reclamos.

### Seguridad técnica

La IA debe advertir riesgos de seguridad: transmisión prohibida de claves, credenciales o tokens en URLs/query strings (exigiendo el uso de cabeceras HTTP seguras como `Authorization` o `X-API-Key`), falta de HTTPS, errores verbosos con trazas de código (*stack traces*) en producción, uso de `Access-Control-Allow-Origin: *` en APIs con datos personales o registrales, permisos excesivos y ausencia de *rate limiting*. Asimismo, debe verificar la confección y aprobación previa del Documento de Requerimientos de Seguridad (DRSI) para servicios y APIs de Nivel 2 y 3, promoviendo el desarrollo seguro y protegiendo los datos de prueba.

### Continuidad operativa y recuperación

Cuando el servicio, API o sistema pueda afectar prestaciones esenciales, datos estratégicos o servicios de alto impacto, la IA debe pedir evidencia de inventario, clasificación de criticidad, RTO/RPO, estrategia de backups o replicación, procedimientos de recuperación, responsables, pruebas periódicas y registro de incidentes. Debe distinguir entre una recomendación general de resiliencia y una obligación aplicable a sujetos alcanzados por normativa vigente, incluyendo la identificación de Infraestructuras Críticas de Información (sectores esenciales como energía, salud, finanzas, transporte y el propio funcionamiento del Estado).

### Respaldo y sitios alternativos

La IA debe advertir si no hay información sobre centro de datos de respaldo, redundancia de conectividad, seguridad física y lógica equivalente, monitoreo, cifrado, restauración desde backups o pruebas de conmutación. Para infraestructura crítica o servicios esenciales, debe recomendar validación técnica especializada.

### Autenticación proporcional y Niveles de Criticidad

La IA debe favorecer mecanismos de autenticación acordes al Nivel de Criticidad del servicio (Nivel 1: público/orientativo; Nivel 2: OAuth 2.0 / JWT y CORS restringido para datos personales; Nivel 3: mTLS, OAuth 2.0 con PKCE e IPs autorizadas para servicios críticos). No todos los servicios requieren el mismo nivel de identidad, pero los datos sensibles requieren mayor protección. Se debe recomendar la aplicación del principio de "necesidad de saber", limitando los permisos y privilegios de acceso al personal y a los sistemas estrictamente a lo necesario para sus funciones.

### Uso responsable de IA

Cuando se propongan sistemas de IA, la IA debe recomendar supervisión humana, evaluación de sesgos, registro de decisiones relevantes, explicabilidad suficiente, pruebas antes de despliegue y monitoreo posterior.

### Datos sensibles

La IA debe marcar como alto riesgo los casos que involucren salud, menores, discapacidad, identidad, ubicación, situación socioeconómica, credenciales, biometría o datos que puedan producir discriminación.

## Preguntas de revisión

- ¿Se piden solo datos necesarios?
- ¿El usuario entiende para qué se usan sus datos?
- ¿Hay información sensible o poblaciones vulnerables?
- ¿La autenticación es proporcional al riesgo?
- ¿Las comunicaciones usan canales seguros?
- ¿Hay controles de acceso y registro?
- ¿El servicio tiene criticidad definida y objetivos RTO/RPO?
- ¿Existen backups, replicación y pruebas de restauración o conmutación?
- ¿Hay roles, contactos y playbooks de respuesta y recuperación?
- ¿El sistema automatiza decisiones que requieren control humano?


[1] [Decreto 87/2017](https://www.argentina.gob.ar/normativa/nacional/decreto-87-2017-271486/actualizacion) - Plataforma Digital del Sector Público Nacional.
[2] [Resolución 1523/2019](https://www.argentina.gob.ar/normativa/nacional/resoluci%C3%B3n-1523-2019-328599/texto) - definición de Infraestructuras Críticas y Glosario de Ciberseguridad.
[3] [Decisión Administrativa 641/2021](https://www.argentina.gob.ar/normativa/nacional/decisi%C3%B3n_administrativa-641-2021-351345/texto) - Requisitos Mínimos de Seguridad de la Información para el Sector Público Nacional.
[4] [Disposición 8/2021 de la Dirección Nacional de Ciberseguridad](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-8-2021-356582/texto) - Guía Introductoria a la Seguridad para el Desarrollo de Aplicaciones Web.
[5] [Disposición 1/2022 sobre Mi Argentina](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-1-2022-361068/texto) - términos y políticas vinculadas con perfil ciudadano.
[6] [Resolución 44/2023](https://www.argentina.gob.ar/normativa/nacional/resoluci%C3%B3n-44-2023-389245/texto) - Segunda Estrategia Nacional de Ciberseguridad y Unidad de Gestión y Cooperación en Ciberseguridad.
[7] [Decreto 269/2026](https://www.argentina.gob.ar/normativa/nacional/decreto-269-2026-425100/texto) - contexto institucional sobre tecnologías emergentes e IA.
[8] [Disposición 1/2026 del Centro Nacional de Ciberseguridad](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-1-2026-425749/texto) - continuidad operativa, planes de contingencia, PRD y centros de datos de respaldo para sujetos alcanzados.
