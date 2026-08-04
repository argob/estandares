---
description: Lista de control para verificar la adopción de prácticas mínimas de seguridad durante el ciclo de vida del desarrollo.
tags:
- ia
- plantilla
- checklist
- desarrollo-seguro
timestamp: '2026-06-15T11:20:00-03:00'
title: Checklist de desarrollo seguro (S-SDLC)
type: Plantilla
---

## Inicio del proyecto

- [ ] Se identificó el alcance y el contexto del desarrollo (interno o tercerizado).
- [ ] Intervino el responsable de seguridad de la información en el inicio de la iniciativa.
- [ ] Se revisó el marco normativo aplicable al tipo de datos y al servicio.

## Análisis de requerimientos

- [ ] Se identificaron y clasificaron los activos del sistema (datos, servicios, código).
- [ ] Se enumeraron los casos de abuso (acciones potenciales de un atacante).
- [ ] Se formularon requerimientos de seguridad explícitos y en formato afirmativo.
- [ ] Se evaluaron los requerimientos de privacidad y la justificación de almacenamiento de datos.
- [ ] Se realizó un análisis de riesgos inicial sobre la arquitectura propuesta.

## Diseño seguro

- [ ] Se minimizó la superficie de ataque (reducción de dependencias y componentes externos).
- [ ] El diseño favorece la mantenibilidad y simplicidad (para reducir la ventana de vulnerabilidad).
- [ ] Se definió seguridad por defecto y políticas de desaliento a configuraciones inseguras.
- [ ] Se negoció un equilibrio entre controles de seguridad y usabilidad del sistema.
- [ ] Se requiere autorización por defecto para acceder a cualquier recurso.
- [ ] Se aplica el principio de mínimo privilegio y separación de responsabilidades y roles.
- [ ] Se implementaron controles de defensa en profundidad (capas de seguridad consecutivas).
- [ ] Se evita depender únicamente de validaciones hechas en el cliente (navegador/frontend).
- [ ] Se diseñaron interfaces de auditoría y monitoreo para los administradores sin revelar datos personales.
- [ ] Se realizó el modelado de amenazas del diseño (diagramas de flujo de datos y análisis STRIDE).

## Codificación segura (Implementación)

- [ ] Toda entrada es validada en el servidor antes de ser procesada.
- [ ] La validación de entradas usa criterios de "lista blanca" (permitir solo lo aceptable).
- [ ] Las rutinas de validación están centralizadas para facilitar su mantenimiento.
- [ ] Se codifican y escapan adecuadamente todas las salidas para prevenir XSS.
- [ ] Se usan librerías estándares y mantenidas para autenticación y control de accesos.
- [ ] Las contraseñas se almacenan mediante algoritmos de hashing seguro (bcrypt, PBKDF2, scrypt).
- [ ] Los formularios de credenciales tienen deshabilitado el autocompletado en el frontend.
- [ ] El manejo de sesiones está centralizado y cuenta con tiempos de finalización automática.
- [ ] Se previeron errores y excepciones sin revelar información interna del sistema.
- [ ] La carga de archivos está restringida por extensiones, analiza virus y se almacena de forma aislada.
- [ ] Se eliminaron todas las credenciales hardcodeadas y backdoors administrativas del código.

## Pruebas de seguridad

- [ ] Las pruebas de seguridad se iniciaron de forma temprana y en paralelo al desarrollo.
- [ ] Se realizan revisiones manuales de código entre pares (en bloques de ~400 líneas por hora).
- [ ] Se complementó la revisión con herramientas de escaneo estático de código (SAST).
- [ ] Se planificaron pruebas de penetración (caja negra) y auditorías manuales (caja blanca).
- [ ] Se firmaron acuerdos de confidencialidad en caso de usar evaluadores externos.

## Despliegue y hardenizado

- [ ] Existe una estricta segregación física o lógica entre los ambientes de desarrollo, pruebas y producción.
- [ ] No se usan datos reales de producción ni credenciales productivas en desarrollo o testing.
- [ ] Se removieron del servidor productivo los paquetes de desarrollo, debuggers y código de prueba.
- [ ] Se cambiaron todas las credenciales predeterminadas de los servicios.
- [ ] El servidor web está aislado de la base de datos (por ejemplo, web en DMZ, base de datos en red privada).
- [ ] Se configuro el cifrado de almacenamiento de datos y de canales de transmisión (HTTPS / TLS).

## Mantenimiento y descarte

- [ ] Existe un protocolo de backup periódico probado con responsables definidos.
- [ ] Hay herramientas para monitoreo de abuso y alertas de seguridad configuradas.
- [ ] Se cuenta con un canal de contacto para reporte de fallos y una base de conocimientos.
- [ ] Se realiza seguimiento de vulnerabilidades y aplicación ágil de parches de seguridad.
- [ ] Al finalizar el ciclo de vida del sistema, se planificó la migración segura o la destrucción de datos (sobreescritura y destrucción física de soportes).
