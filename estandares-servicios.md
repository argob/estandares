# Estándares Servicios

**Secretaría de Innovación, Ciencia y Tecnología**
- Subsecretaría de Tecnologías de la Información y las Comunicaciones  
  -   Dirección Nacional de Servicios Digitales

Versión: 1.0 

**Índice**

* [Objetivo](#objetivo)
* [Requisitos](#requisitos)
* [Niveles de Criticidad y Seguridad](#niveles-de-criticidad-y-seguridad)
* [Aclaraciones](#aclaraciones)

## Objetivo

El presente documento tiene como objetivo definir las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar todo servicio, ya sea realizado por empleados del Estado o personal tercerizado, cuyo destinatario sean los ciudadanos.

Con los siguientes estándares, se busca homogeneizar la experiencia entre los diversos sectores del Estado, para facilitar la comprensión y utilización, primando la Usabilidad, la Accesibilidad y la Experiencia de los ciudadanos.

 

## Requisitos

Los ministerios deberán:

* Realizar un relevamiento de los servicios y trámites que tienen a su cargo, con especial atención a los indicadores mencionados ut supra, y comunicarlo a la Secretaría de Innovación, Ciencia y Tecnología en tanto organismo responsable del mejoramiento de los procesos de la Administración Pública Nacional.

* Designar un responsable por ministerio como referente para la Secretaría de Innovación, Ciencia y Tecnología en todos los asuntos relativos a servicios y trámites en tanto organismo responsable del mejoramiento de los procesos de la Administración Pública Nacional.

* Informar a la Secretaría de Innovación, Ciencia y Tecnología cuáles son las prioridades de mejora en servicios y trámites en tanto organismo responsable del mejoramiento de los procesos de la Administración Pública Nacional.

* Relevar mensualmente la cantidad de beneficiarios de cada servicio en tanto esta información permite dimensionar el alcance que tiene.

* Realizar mensualmente un cálculo aproximado de la cantidad de beneficiarios potenciales de cada servicio para, de esta manera, dimensionar el universo de ciudadanos que aún no acceden a él. 

* Calcular mensualmente la cantidad de transacciones que tiene cada trámite, ya sea presencial o digital.

* Relevar mensualmente el tiempo estimado necesario para realizar cada trámite, ya sea presencial o digital.

* Informar a la Secretaría de Innovación, Ciencia y Tecnología todas las creaciones de nuevos servicios y trámites, y de modificaciones que se realicen a servicios y trámites ya existentes, en tanto este es el organismo a cargo de la simplificación de los procedimientos administrativos de la Administración Pública Nacional.

## Niveles de Criticidad y Seguridad

Para garantizar la postura de ciberseguridad e interoperabilidad de los servicios y APIs del Sector Público Nacional, los servicios tecnológicos se clasificarán según su nivel de impacto y sensibilidad:

| Nivel de Criticidad | Alcance y Definición | Requisitos de Seguridad y Control |
| :--- | :--- | :--- |
| **Nivel 1 (Bajo)** | Servicios de consulta pública u orientativos sin manejo de datos personales ni registrales (ej. catálogos de información pública). | Autenticación opcional; CORS universal (`*`) permitido; transporte seguro HTTPS obligatorio. |
| **Nivel 2 (Medio)** | Servicios que gestionan datos personales de ciudadanos, trámites registrales o transacciones con autenticación. | Autenticación obligatoria (OAuth 2.0 / JWT); restricción de origen CORS (*whitelist*); DRSI obligatorio; auditoría nominal. |
| **Nivel 3 (Alto)** | Servicios críticos o de infraestructura sensible del Estado Nacional (ej. identidades, bases registrales nacionales, sistemas financieros). | Autenticación mTLS / OAuth 2.0 con PKCE; IPs autorizadas; monitoreo continuo 24/7; DRSI aprobado y registrado; revocación en <8h. |

### Documento de Requerimientos de Seguridad (DRSI)

Previo al pase a producción de cualquier servicio público o API clasificado en **Nivel 2 o Nivel 3**, el organismo proveedor DEBE confeccionar, aprobar y publicar el correspondiente **Documento de Requerimientos de Seguridad (DRSI)**, detallando los controles de acceso, responsables técnicos y políticas de contingencia implementadas.

## Aclaraciones

* Por **servicios** entendemos a todos los beneficios, certificaciones y/o prestaciones que el Estado ofrece a la ciudadanía en el marco de una política pública. Esto incluye un amplio rango de prestaciones, desde pensiones y subsidios hasta legalización de documentos e inscripción a registros.

* Por **trámites** entendemos a todas las transacciones que un ciudadano deba realizar en el marco de un servicio específico prestado por el Estado. Algunos ejemplos usuales de estas transacciones son: inscripciones, renovaciones, modificaciones, bajas, etc. Los trámites pueden ser presenciales, digitales o combinados.


