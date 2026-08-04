---
description: Instrucciones operativas para evaluar la seguridad de aplicaciones web basándose en prácticas seguras de desarrollo (S-SDLC).
tags:
- ia
- skill
- revision
- desarrollo-seguro
- codigo-seguro
timestamp: '2026-06-15T11:20:00-03:00'
title: 'Skill: Revisar desarrollo seguro y código web'
type: Skill
---

## Objetivo

Evaluar si el diseño de arquitectura, plan de desarrollo o código fuente de una aplicación web cumple con los estándares de seguridad y desarrollo seguro establecidos en la Guía de la Dirección Nacional de Ciberseguridad (Disposición DNCib 8/2021).

## Cuándo usarla

Usar esta skill al realizar revisiones de código (code reviews / pull requests), evaluar pliegos o especificaciones de software a adquirir/desarrollar, y al auditar la seguridad técnica en el ciclo de vida de aplicaciones web del Sector Público Nacional.

## Instrucciones para la IA

1. **Identificar la fase del ciclo de vida (S-SDLC):** Ubicar el estado del proyecto (Inicio, Requerimientos, Diseño, Implementación, Pruebas, Despliegue, Mantenimiento) y el rol de los responsables de seguridad.
2. **Revisar Validación de Entradas:**
   - Exigir que toda validación se realice en el servidor (nunca confiar en validaciones de cliente).
   - Aplicar el criterio de "lista blanca" (permitir solo lo aceptable y rechazar el resto).
   - Comprobar que las rutinas estén centralizadas.
3. **Revisar Codificación de Salidas:**
   - Comprobar que cualquier entrada de usuario reflejada en el frontend esté correctamente codificada/escapada para prevenir XSS y ataques de phishing.
4. **Evaluar Autenticación y Sesión:**
   - Verificar el uso de librerías/frameworks estándar (no desarrollos a medida).
   - Exigir el almacenamiento de contraseñas mediante hashing seguro (bcrypt, PBKDF2, scrypt) y nunca en texto plano.
   - Validar que los formularios de credenciales tengan deshabilitado el autocompletado en el frontend.
   - Comprobar que existan tiempos de expiración automática de sesión y opción clara de cierre.
5. **Evaluar Control de Accesos:**
   - Verificar la aplicación estricta del principio de mínimo privilegio y "necesidad de saber".
   - Asegurar que la validación de permisos se ejecute en el servidor y para cada solicitud.
6. **Revisar Excepciones y Errores:**
   - Verificar que en entornos productivos estén desactivados los mensajes de depuración (debugging) y stack-traces que expongan el funcionamiento interno del sistema.
7. **Revisar Carga de Archivos:**
   - Exigir restricciones estrictas en tipos y extensiones de archivos.
   - Recomendar análisis de malware y almacenamiento en servidores o particiones aisladas de la aplicación web principal.
8. **Detectar Puertas Traseras (Backdoors):**
   - Buscar bypasses de autenticación, contraseñas cableadas en código (hardcoded credentials) o rutas administrativas de prueba, exigiendo su eliminación antes de producción.
9. **Inspeccionar la Segregación de Ambientes:**
   - Validar que no se utilicen datos reales de producción en entornos de desarrollo o prueba (usar datos simulados/anonimizados).
   - Exigir la separación física o lógica entre servicios web (DMZ) y bases de datos.
10. **Revisar Planificación de Pruebas y Mantenimiento:**
    - Recomendar revisiones manuales entre pares limitadas a bloques de máximo 400 líneas de código y sesiones de 1 hora.
    - Asegurar que existan protocolos de backup probados, canales de reporte de incidentes y un proceso seguro de descarte de la aplicación (borrado seguro mediante sobreescritura).

## Formato de respuesta

```md
## Resumen de la revisión

Breve diagnóstico sobre el cumplimiento general del desarrollo/código respecto a la Disposición 8/2021.

## Hallazgos de código y diseño

### [Nivel de Severidad: Crítico / Alto / Medio / Bajo]
- **Archivo/Línea o Componente:**
- **Debilidad (OWASP / DNCib):** (ej. Entrada no validada, Credencial expuesta)
- **Evidencia detectada:** (Describir o mostrar el fragmento de código inseguro)
- **Impacto:** (Riesgo tecnológico y de negocio)
- **Mitigación recomendada:** (Código sugerido seguro o cambio de arquitectura)

## Evaluación del S-SDLC (Ciclo de Vida Seguro)

- **Fase analizada:** (Diseño, Implementación, Despliegue, etc.)
- **Estado de cumplimiento:** (Indicar brechas en segregación de entornos, pruebas de seguridad o backups)
- **Recomendación para el equipo:**


[1] [Disposición DNCib 8/2021](https://www.argentina.gob.ar/normativa/nacional/disposici%C3%B3n-8-2021-356582/texto)
[2] [Decisión Administrativa 641/2021](https://www.argentina.gob.ar/normativa/nacional/decisi%C3%B3n_administrativa-641-2021-351345/texto) - ```

## Referencias internas

- [Lineamientos de seguridad y privacidad](../lineamientos/seguridad-y-privacidad.md)
- [Marco normativo](../marco-normativo.md)
