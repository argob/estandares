---
description: Resumen operativo de los estándares tecnológicos (ETAP) vigentes de la Oficina Nacional de Tecnologías de Información.
tags:
- ia
- lineamiento
- etap
- tecnologia
- pliegos
timestamp: '2026-06-15T11:20:00-03:00'
title: Estándares Tecnológicos para la Administración Pública Nacional (ETAP) — Lineamientos
type: Lineamiento
---

**Fuente:** Disposición ONTI DI-2023-60102103-APN-DET#JGM — Anexo III, versión 26  
**Organismo:** Oficina Nacional de Tecnologías de Información (ONTI), Argentina  
**Aplicación:** Proyectos de adopción tecnológica en el Sector Público Nacional (SPN)

---

## Principio general

La incorporación de tecnología en el Sector Público no es un fin en sí mismo, sino un medio para hacer más eficientes los procesos internos y elevar la calidad de los servicios a la ciudadanía. Todo requerimiento técnico debe ser **abierto** (sin especificar marca o proveedor) y orientado a resultados.

---

## 1. Servicios de Nube (Cloud Computing)

### Conceptos clave
- **Modelos de servicio:** SaaS, PaaS, IaaS.
- **Modelos de implementación:** Pública, Privada, Híbrida.
- **Características esenciales (NIST SP 800-145):** servicio a demanda, amplio acceso a la red, puesta en común de recursos, elasticidad, servicio medido.

### Estructura del pliego (siempre incluir)
1. **Alcance** — qué servicios se requieren y sus funcionalidades.
2. **Disponibilidad** — porcentajes mínimos exigibles.
3. **Penalidades** — créditos/devoluciones por incumplimiento.

### Aspectos del alcance a considerar
- Gestión de cuentas de usuarios (altas, bajas, permisos).
- Estadísticas y reportes de uso.
- Redundancia para servicios críticos.
- Elasticidad / escalabilidad a demanda (horizontal y vertical para PaaS/IaaS).
- Infraestructura como código (opcional).
- Balanceo de carga (opcional).
- Cronograma de activación de recursos (opcional).
- Reserva anticipada de recursos o consumo para optimizar costos (opcional).
- Pruebas de estrés de arquitectura (opcional).
- Asistencia técnica: puede contratarse al proveedor directamente o a un partner oficial certificado.
- Auditoría de recursos: logs y trazabilidad de acciones.
- Entornos de producción, desarrollo y testing claramente diferenciados.

### Disponibilidad recomendada
| Tipo de servicio | Disponibilidad mínima mensual |
|---|---|
| Cualquier servicio | ≥ 95% |
| Servicios críticos | ≥ 99,95% |

- Los valores no pueden ser modificados unilateralmente por el proveedor.
- Incluir cláusulas de **tiempo mínimo medio entre fallas** para evitar que fallas cortas acumuladas queden fuera del cómputo de penalidades.

### Penalidades
- Los porcentajes de crédito/devolución forman parte de las características publicadas del servicio y deben estar disponibles en dominio público antes de la adjudicación.
- Deben mantenerse fijos durante toda la vigencia del contrato.

---

## 2. Servicios Profesionales

### Situaciones típicas de contratación
- Consultorías (análisis, estudios, planes estratégicos).
- Soluciones innovadoras (diseño centrado en el usuario).
- Mantenimientos evolutivos y/o adaptativos.
- Exigencias ciertas con requerimientos impredecibles (trabajo a demanda).
- Mudanzas y/o migraciones de infraestructura o sistemas.

### Estructura del pliego
1. **Alcance** (entregables o horario laboral, cronograma, perfiles profesionales).
2. **Disponibilidad** (% mensual sobre horas contratadas).
3. **Penalidades** (% del valor mensual, escaladas por criticidad).

### Aspectos clave del alcance
- Definir entregables con formato y contenido mínimo, asociados a fechas.
- Si no hay entregables predefinibles, establecer **horario laboral** y disponibilidad total del equipo.
- Definir **cantidad, roles y competencias** de cada perfil profesional.
- Solicitar **currículums y certificaciones** que avalen las competencias requeridas.
- Incluir cláusulas de **propiedad intelectual** (código fuente, documentación, etc. pertenecen al organismo).
- Incluir cláusulas de **confidencialidad** de toda la información, incluso tras finalizado el contrato.
- Definir criterios objetivos de **conformidad mensual del servicio**.

### Metodologías ágiles (caso especial)
Indicadas cuando existe al menos uno de estos factores:
- Contextos complejos o de gran incertidumbre.
- Alta volatilidad o ambigüedad en los requerimientos.
- Diseño centrado en el usuario como factor crítico de adopción.
- Implementaciones ambiciosas o de alta complejidad.

**Cinco etapas genéricas del proceso ágil:**

| Etapa | Descripción |
|---|---|
| 1. Relevamiento de situación actual | Actores, destinatarios, infraestructura, procesos existentes |
| 2. Empatía con destinatarios | Mapas de empatía, perfiles de usuario, CANVAS de valor |
| 3. Definición del problema | Exploración de enfoques, formulación en positivo ("¿Cómo podríamos...?") |
| 4. Elaboración y validación de prototipos | Prototipo mínimo viable validado con usuarios reales |
| 5. Implementación | Sprints con entregables, ciclos de calidad y mantenimiento |

---

## 3. Servicios de Blockchain

### Tipos
- **Pública (permissionless):** acceso abierto, ej. Bitcoin, Ethereum.
- **Privada (permissioned):** acceso por invitación, validador único.
- **Federada / Consorcio:** múltiples organizaciones comparten la red; ej. **Blockchain Federal Argentina (BFA)**.

### BFA — consideraciones para organismos públicos
- No es necesario unirse al consorcio para usar el servicio; basta con crear una cuenta.
- Se requiere un **nodo transaccional** propio que opere con Ether provisto por el consorcio BFA.
- No hay tiempo garantizado para la inclusión de transacciones: se recomienda hacer **pruebas de concepto** antes de adoptar.
- BFA no tiene responsabilidad sobre el contenido de las transacciones firmadas por terceros.
- Considerar aspectos **legales de jurisdicción** sobre el contenido publicado en la blockchain.

---

## 4. Dimensionamiento de Almacenamiento (SAN/NAS)

### Tipos principales
- **NAS (Network Attached Storage):** comparte la red LAN de usuarios.
- **SAN (Storage Area Network):** red propia de almacenamiento, recomendada para datos críticos.

### Elegir SAN cuando se requiere
- Backup centralizado, rápido y desatendido.
- Escalabilidad de rendimiento y capacidad.
- Compartir archivos entre múltiples plataformas.
- Alta disponibilidad de datos.

### Fórmula de dimensionamiento
```
CF ≥ CI × (1 + P/100)^A
```
Donde: **CI** = capacidad inicial, **P** = crecimiento anual (%), **A** = años de vida útil.

**Ejemplo:** CI=10TB, P=15%, A=5 años → CF ≥ 20,1 TB

### Tipos de disco (velocidad vs. costo)
De más rápido a más lento (y más caro a más barato): **SSD > SAS > NL SAS > SATA**

---

## 5. Proceso de Digitalización

### Distinción clave
- **Digitalizar** = convertir soporte papel a soporte digital.
- **Informatizar** = generar información nativamente en soporte digital.

### Requisitos previos mínimos antes de iniciar
- Identificar los documentos originales.
- Solicitar intervención del **Archivo General de la Nación** (obligatorio antes de cualquier eliminación de originales).
- Conocer el volumen, velocidad de conversión y características físicas de los originales.
- Definir trazabilidad extremo a extremo y posibilidad de auditoría completa.
- Conocer tecnologías de autenticidad: **firma digital, firma electrónica, sellos de tiempo**.

### Formatos destino estándares aceptados
| Formato | Uso |
|---|---|
| PDF / PDF/A | Documentos (preservación a largo plazo: PDF/A) |
| PNG, TIFF | Imágenes |
| HTML, XHTML | Texto e imagen web |
| ODF (odt, ods, odp) | Documentos de oficina abiertos |
| Strict Open XML (docx, xlsx, pptx) | Documentos Office (con precaución por compatibilidad) |
| TXT | Texto plano |
| XML / XSD | Integración de datos |
| GZIP / ZIP | Compresión |

> **Importante:** Digitalizar NO habilita eliminar originales en papel. Se requiere autorización del Archivo General de la Nación.

---

## 6. Geotecnologías

### Definición
Gestión de información geoespacial mediante TIC (geodesia, fotogrametría, SIG, teledetección, etc.).

### Marco institucional: IDERA
La **Infraestructura de Datos Espaciales de la República Argentina** (IDERA) establece las siguientes recomendaciones:

| Principio | Aplicación |
|---|---|
| **Acceso** | Público por defecto; restringido solo si hay legislación específica o seguridad nacional |
| **Difusión** | Vía internet, con licencias Creative Commons |
| **Uso** | Según la licencia elegida por el productor |
| **Interoperabilidad** | Estándares abiertos, metadatos según perfil IDERA |
| **Propiedad** | Del organismo que produce la información |

### Mapas base obligatorios: ARGENMAP (IGN)
De conformidad con la **Decisión Administrativa 797/2022**, todas las jurisdicciones, entidades y organismos del Sector Público Nacional (art. 8 incisos a y b de la Ley 24.156) que requieran publicar un mapa de la República Argentina en sus sitios web institucionales deben utilizar **obligatoriamente** los mapas base del servicio **ARGENMAP**, desarrollado por el **Instituto Geográfico Nacional (IGN)**.

### Formatos recomendados para publicación
- Información vectorial: **WFS (Web Feature Service)**
- Información raster: **WCS (Web Coverage Service)**
- Descarga: **Shapefile** y **.kmz**, con metadatos en **.xml**

---

## 7. Escritorios Virtuales (VDI)

### Modalidades de implementación
1. Datacenter propio.
2. Housing en datacenter de terceros (ej. ARSAT).
3. **DaaS** (Desktop as a Service) — ver lineamiento de servicios de nube.

### Recursos que consume un escritorio virtual
- **CPU** y **RAM** (según SO y aplicaciones).
- **Almacenamiento** (imagen de SO + datos de usuario si hay persistencia).
- **Ancho de banda** de Internet.

### Seguridad de datos
| Aspecto | Medidas recomendadas |
|---|---|
| **Confidencialidad** | Políticas de acceso, certificados SSL, túneles VPN |
| **Integridad** | Permisos granulares sobre archivos, conexiones seguras |
| **Disponibilidad** | Redundancia en datacenter, backups periódicos |

### Ventajas estratégicas
- Reducción de hardware (menos PCs físicas).
- Administración centralizada y simplificada.
- Mayor movilidad y teletrabajo seguro.
- Mayor seguridad (menos vectores de ataque).
- Mejor adaptabilidad a cambios futuros.

---

## 8. Desarrollo de Software como Proyecto de Innovación Tecnológica

### Etapas del ciclo de desarrollo
| Etapa | % horas estimado | Descripción |
|---|---|---|
| Análisis | ~10% | Relevamiento, definición del problema, requerimientos |
| Diseño | ~10% | Diseño externo (UX/API) e interno (arquitectura de datos) |
| Implementación | ~35% | Codificación según plan de trabajo |
| Testing | ~35% | Pruebas por casos definidos en diseño, control de calidad Q(%) |
| Puesta en producción | ~10% | Instalación, integración, pruebas finales |

### Criterio de calidad en testing
```
Q(%) = BugsUltimoCiclo / BugsTotales × 100
```
Si Q(%) < umbral definido en el diseño → se supera el ciclo de testing.

### Métodos de estimación de horas hombre
- **Descomposición Top-Down:** rápido, menos preciso.
- **Descomposición Bottom-Up:** más preciso, requiere más inversión.
- **Estadísticos (1 punto / 3 puntos):** basados en juicio experto.
- **Consenso (Wideband Delphi / Planning Poker):** validados por grupo de expertos.
- **Puntos de función (IFPUG-FPA):** cuantifica funcionalidades por complejidad.

### Buenas prácticas para el SPN
1. Usar **metodologías ágiles e iterativas** (DevOps, DevSecOps).
2. Preferir plataformas **abiertas e interoperables**.
3. Compatibilidad con plataformas de gobierno (**argentina.gob.ar**).
4. Reutilizar servicios existentes (SSO de AFIP/ANSES, validación DNI de RENAPER).
5. Documentar y compartir para que otros organismos puedan reutilizar.
6. Garantizar **accesibilidad web** (Ley 26.653).
7. Incluir **seguridad desde el diseño**: validación de inputs, 2FA, control de acceso por roles, encriptación TLS/SSL, pruebas de penetración.

### Etapa de operación posterior
| Servicio | Descripción |
|---|---|
| Garantía de buen funcionamiento | Corrección sin costo por un plazo (ej. 6 meses) post-entrega |
| Mantenimiento correctivo | Corrección de bugs no detectados en producción |
| Mantenimiento evolutivo | Nuevas funcionalidades surgidas post-implementación |
| Mantenimiento adaptativo | Migración a nuevos entornos o plataformas |

---

## 9. Resguardo en Cinta (Biblioteca Robótica)

### Estrategias de backup
| Tipo | Ventaja | Desventaja |
|---|---|---|
| **Completo (Full)** | Restauración en una operación | Lento, alto desgaste |
| **Incremental** | Rápido si hay pocos cambios | Restauración requiere recorrer todos los ciclos previos |
| **Diferencial** | Solo dos conjuntos de cintas | Puede volverse voluminoso si hay muchos cambios |

**Práctica recomendada:** combinar resguardo completo periódico + incrementales/diferenciales entre ciclos.

### Variables clave a relevar antes de dimensionar
1. Frecuencia requerida de resguardo.
2. Volumen total de datos.
3. Porcentaje de variabilidad de los datos por período.
4. Tiempo máximo admisible para un resguardo completo (no debe superar un día hábil).
5. Capacidad y velocidad de grabación de las cintas disponibles en el mercado.

### Alternativa para volúmenes muy altos
**VTL (Virtual Tape Library):** arreglo de discos redundantes que emula el comportamiento de un sistema de cintas, con respaldo secundario en cinta física para datos históricos.

---


## Normativa y referencias complementarias
- Decisión Administrativa 797/2022 — Uso obligatorio de mapas base del servicio ARGENMAP (IGN) para publicación de mapas web.
- Disposición ONTI 1/2021 — Guía para la incorporación de nuevas tecnologías en el SPN.
- Ley 26.653 — Accesibilidad de la información en las páginas web.
- NIST SP 800-145 — Definición de Cloud Computing.
- IDERA — Perfiles y esquemas de metadatos geoespaciales.
- Blockchain Federal Argentina (BFA) — https://bfa.ar
- SINDAP — Sistema Nacional de Datos Públicos (licencias abiertas).
