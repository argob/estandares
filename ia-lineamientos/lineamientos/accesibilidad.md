---
description: Pautas para garantizar que el software y la información sean accesibles para todas las personas desde el inicio.
tags:
- ia
- lineamiento
- accesibilidad
timestamp: '2026-06-15T11:20:00-03:00'
title: Lineamientos de accesibilidad para IA
type: Lineamiento
---

Estos lineamientos orientan a una IA que revisa interfaces, contenidos o componentes digitales.

## Objetivo

Ayudar a que los servicios digitales puedan ser usados por todas las personas, incluidas personas con discapacidad, personas mayores, personas con baja conectividad o personas que usan tecnologías asistivas.

## Criterios

### Revisar con evidencia

La IA debe basar sus hallazgos en elementos concretos: estructura HTML, foco, formularios, contraste, texto alternativo, mensajes de error, componentes interactivos, lectura con lector de pantalla o resultados de herramientas automáticas.

### Usar semántica nativa

La IA debe favorecer HTML semántico y controles nativos cuando sea posible. Debe advertir cuando un elemento visual parece botón, enlace, lista, tabla o encabezado pero no está marcado como tal.

### Navegación por teclado

La IA debe revisar que todos los controles puedan recorrerse y accionarse con teclado, que el foco sea visible, que el orden sea coherente y que no existan trampas para el foco.

### Formularios accesibles

La IA debe verificar labels asociados, fieldsets y legends cuando corresponda, instrucciones claras, errores audibles, foco en errores y mensajes de éxito comprensibles.

### Alternativas accesibles

La IA debe pedir texto alternativo para imágenes informativas, transcripciones o alternativas para multimedia, y representaciones textuales para mapas, gráficos o visualizaciones complejas.

### Contenido dinámico

La IA debe advertir cuando cambios de estado, modales, desplegables, alertas o resultados de búsqueda no se anuncian a tecnologías asistivas.

## Preguntas de revisión

- ¿La página tiene un `h1` claro y jerarquía de encabezados?
- ¿Todo se puede usar con teclado?
- ¿El foco visible está preservado?
- ¿Los formularios se entienden con lector de pantalla?
- ¿Los errores indican qué corregir y cómo hacerlo?
- ¿Las imágenes y gráficos tienen alternativa adecuada?
- ¿Los modales y desplegables anuncian apertura, cierre y estado?


[1] [Ley 26.653](https://www.argentina.gob.ar/normativa/nacional/ley-26653-175694/texto) - accesibilidad de la información en páginas web.
[2] [Decreto 656/2019](https://www.argentina.gob.ar/normativa/nacional/decreto-656-2019-328722/texto) - reglamentación de accesibilidad web.
[3] [Disposición ONTI 6/2019](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-6-2019-329284/texto) - pautas de accesibilidad de contenido web 2.0.
[4] [Resolución 333/2017](https://www.argentina.gob.ar/normativa/nacional/resoluci%C3%B3n-333-2017-276568/texto) - estándares web y aplicaciones móviles.
