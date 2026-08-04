---
description: Lista de control para evaluar si una especificación de API se alinea con los estándares de interoperabilidad del Estado.
tags:
- ia
- plantilla
- checklist
- api
timestamp: '2026-06-15T11:20:00-03:00'
title: Checklist de API
type: Plantilla
---

## Diseno

- [ ] La API tiene propósito claro.
- [ ] Los recursos están nombrados de forma consistente.
- [ ] Los métodos HTTP se usan correctamente.
- [ ] Hay versionado explícito.
- [ ] Hay paginación y límites para listados.

## Respuestas

- [ ] Las respuestas son JSON consistente.
- [ ] Los errores tienen código, mensaje y detalle accionable.
- [ ] Las fechas usan formato estándar.
- [ ] Hay metadata cuando corresponde.
- [ ] No hay claves impredecibles.

## Documentación

- [ ] Hay descripción funcional.
- [ ] Hay autenticación y autorización documentadas.
- [ ] Hay parámetros, ejemplos y códigos de estado.
- [ ] Hay ambiente o datos de prueba.
- [ ] Hay contacto técnico o canal de soporte.

## Seguridad y privacidad

- [ ] Se usa HTTPS.
- [ ] No se exponen credenciales.
- [ ] No se devuelven datos personales innecesarios.
- [ ] Hay control de acceso.
- [ ] Hay límites de uso o protección ante abuso.

## Operación

- [ ] Hay política de cambios.
- [ ] Hay monitoreo de errores.
- [ ] Hay trazabilidad suficiente.
- [ ] Hay estrategia de deprecación.
- [ ] Hay criticidad definida cuando corresponde.
- [ ] Hay objetivos de recuperación para APIs críticas.
- [ ] Hay backups, replicación o restauración probada para datos críticos.
