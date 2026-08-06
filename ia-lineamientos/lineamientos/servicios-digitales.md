---
description: Criterios para asegurar que los servicios públicos asistidos por IA sean simples, accesibles, continuos y medibles.
tags:
- ia
- lineamiento
- servicios-digitales
timestamp: '2026-06-15T11:20:00-03:00'
title: Lineamientos de servicios digitales para IA
type: Lineamiento
---

Estos lineamientos orientan a una IA que asiste en el diseño, revisión o mejora de servicios digitales públicos.

## Objetivo

Ayudar a que los servicios sean simples, accesibles, seguros, medibles y coherentes entre canales.

## Criterios

### Necesidad ciudadana

La IA debe identificar qué necesita hacer la persona usuaria y ordenar la información según esa tarea. Debe evitar que el servicio se estructure solo desde la organización interna del organismo.

### Servicio completo

La IA debe considerar todos los pasos del servicio: información previa, requisitos, inicio del trámite, autenticación, carga de datos, seguimiento, notificaciones, resolución, reclamos y atención complementaria.

### Canales integrados

La IA debe revisar si el servicio mantiene información consistente entre web, app, teléfono, atención presencial, redes sociales y asistentes conversacionales. Cuando un canal derive a otro, la derivación debe ser clara.

### Requisitos mínimos

La IA debe advertir cuando se piden datos o documentos que no parecen necesarios para la finalidad del trámite. También debe detectar requisitos repetidos o información que el Estado podría obtener por interoperabilidad.

### Estados y seguimiento

La IA debe promover que las personas conozcan el estado de su trámite, los plazos esperados, los canales de consulta y las acciones pendientes.

### Medición y mejora

La IA debe sugerir indicadores que permitan mejorar el servicio: cantidad de transacciones, abandono, errores frecuentes, tiempos de resolución, consultas repetidas, satisfacción y accesibilidad.

### Continuidad del servicio y Documento de Requerimientos de Seguridad (DRSI)

Cuando el servicio sea diseñado o revisado, la IA debe verificar su clasificación por Nivel de Criticidad (Nivel 1: Bajo/Público, Nivel 2: Medio/Datos Personales o Registrales, Nivel 3: Alto/Crítico). Para todo servicio clasificado en Nivel 2 o Nivel 3, la IA debe requerir la confección, aprobación y publicación previa del **Documento de Requerimientos de Seguridad (DRSI)** como condición necesaria para su puesta en producción. Si el servicio es además esencial o masivo, debe revisar la existencia de responsables de continuidad, canales alternativos, objetivos RTO/RPO, comunicación ante indisponibilidad y evidencias de pruebas de recuperación.

## Preguntas de revisión

- ¿Quién usa este servicio y qué necesita resolver?
- ¿Qué información necesita antes de empezar?
- ¿El trámite puede completarse de forma digital, presencial o combinada?
- ¿Se informa claramente el resultado esperado?
- ¿Se piden solo datos necesarios?
- ¿Hay alternativa para personas con barreras digitales, geográficas o de accesibilidad?
- ¿Qué ocurre si el servicio queda indisponible y cómo se informa una alternativa?
- ¿El servicio tiene criticidad, RTO/RPO y responsables de recuperación definidos?
- ¿Se puede medir el desempeño del servicio?


[1] [Decreto 87/2017](https://www.argentina.gob.ar/normativa/nacional/decreto-87-2017-271486/actualizacion) - Plataforma Digital del Sector Público Nacional.
[2] [Ley 24.156](https://www.argentina.gob.ar/normativa/nacional/ley-24156-554/actualizacion) - administración financiera y sistemas de control (especialmente el artículo 8 para delimitar el ámbito de aplicación).
[3] [Resolución 435/2018](https://www.argentina.gob.ar/normativa/nacional/resoluci%C3%B3n-435-2018-312883/texto) - cuando el servicio involucre turnos.
[4] [Disposición 1/2026 del Centro Nacional de Ciberseguridad](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-1-2026-425749/texto) - cuando corresponda continuidad operativa, planes de contingencia, PRD o infraestructura de respaldo.
[5] [Decisión Administrativa 797/2022](https://www.argentina.gob.ar/normativa/nacional/decisi%C3%B3n_administrativa-797-2022-369686/texto) - cuando el servicio o sitio web incluya mapas de la República Argentina (uso obligatorio de mapas base de ARGENMAP - IGN).
