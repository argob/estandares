---
description: Instrucciones operativas para evaluar y auditar la conformidad de interfaces web con las pautas de accesibilidad.
tags:
- ia
- skill
- revision
- accesibilidad
timestamp: '2026-06-15T11:20:00-03:00'
title: 'Skill: Revisar accesibilidad digital'
type: Skill
---

## Objetivo

Detectar barreras de accesibilidad en sitios, aplicaciones, formularios, contenidos y componentes interactivos.

## Cuándo usarla

Usar esta skill para revisar prototipos, HTML, pantallas, formularios, componentes, flujos o reportes de herramientas automáticas.

## Instrucciones para la IA

1. Revisar estructura semántica: título, `h1`, jerarquía de encabezados, landmarks, listas, tablas y enlaces.
2. Revisar operación por teclado: orden de foco, foco visible, activación con Enter o espacio y ausencia de trampas de foco.
3. Revisar formularios: labels, fieldsets, legends, ayudas, errores, foco en error y confirmaciones.
4. Revisar alternativas: texto alternativo, transcripciones, captions y alternativas textuales para gráficos, mapas o visualizaciones.
5. Revisar contraste, tamanos, proximidad visual y dependencia exclusiva del color.
6. Revisar contenido dinámico: modales, alertas, desplegables, carga de resultados, cambios de estado y regiones anunciadas.
7. Diferenciar hallazgos comprobados de puntos que requieren test manual con lector de pantalla.
8. Priorizar como crítico todo bloqueo que impida completar una tarea.

## Formato de respuesta

```md
## Resumen de accesibilidad

Estado general y bloqueos principales.

## Hallazgos

- Severidad:
- Criterio:
- Evidencia:
- Impacto:
- Recomendación:
- Validación:

## Pruebas manuales recomendadas

- Prueba:
- Objetivo:

## Riesgo residual

- Punto que no pudo verificarse:
```

## Referencias internas

- [Accesibilidad](../lineamientos/accesibilidad.md)
