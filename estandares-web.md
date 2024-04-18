# Estándares de sitios web

**Secretaría de Innovación, Ciencia y Tecnología**
- Subsecretaría de Tecnologías de la Información  
  -   Dirección Nacional de Servicios Digitales

## Índice

* [Objetivo](#objetivo)
* [Diseño](#diseño)
* [Contenido](#contenido)
* [Desarrollo](#desarrollo)
* [Seguridad](#seguridad)
* [Métricas](#métricas)

## Objetivo: 

Este documento define las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar todo sitio web del Estado Nacional, ya sea realizado por empleados del Estado o personal tercerizado, con el fin de ser utilizados por ciudadanos.

## **Diseño**

La UX (experiencia de usuario) debe ser útil para el ciudadano además de fácil de entender y usar. La identidad visual debe ser homogénea entre los diferentes sitios del Gobierno (para lo cual se usa la librería de estilos y componentes [Poncho](http://argob.github.io/poncho/). Para más información ver los [Estándares de Diseño de UX e Identidad Visual](https://github.com/argob/estandares/blob/master/estandares-ux-visual.md)

## **Contenido**

El estilo de comunicación de los sitios debe ser cercano al ciudadano, con lenguaje simple, preferentemente usando fotos con ciudadanos argentinos. Para más información ver la [Guía de estilo para contenidos web](https://github.com/argob/estandares/blob/master/contenido-web.md)

## **Desarrollo**

* Se pueden usar redirects desde dominios a otros dominios (ej: [www.trabajo.gob.ar](https://www.trabajo.gob.ar/) redirige a [www.argentina.gob.ar/capital-humano/trabajo](https://www.argentina.gob.ar/capital-humano/trabajo))

* Los sitios web que sean la base del dominio deben usarse con www.
Ejemplo [www.mininterior.gob.ar](http://www.mininterior.gob.ar). Si uno ingresa a [mininterior.gob.ar](http://mininterior.gob.ar) se deberá generar redirect 301 al dominio con las www.

* Todos los sitios web del Estado usarán la terminación .gob.ar. El registro de .gov.ar deberá generar un redirect 301 al dominio gob.ar.

* Todos los sitios web que ofrezcan servicios de consulta online (mostrar ejemplos) deben tener una API disponible y/o planificada su implementación. (Ver estándares de APIs).

* Todos los sitios con servicios para el ciudadano que tengan que tener registro de usuarios deben usar el sistema de login de [Mi Argentina (ID)](https://argob.github.io/mi-argentina-docs/).

* Los sitios deben ser responsive para poder adaptarse y poder ser navegables desde diversos dispositivos como por ejemplo celulares.

* Todos los sitios y aplicaciones deberán contar con el mínimo de documentación necesaria para ser instalados en diferentes entornos.

* En caso de desarrollar sistemas que requieran interacción con el usuario deberá tener con compatibilidad con los siguientes navegadores y versiones: 

    * Firefox 125 - Firefox ESR 115.10.0 (en caso de contar con Windows 7)
    
    * Chrome 124 - Chrome 109 (en caso de contar con Windows 7)

    * Microsoft Edge 124
      
    Para versiones menores deberá mostrar una alerta indicando que el navegador está desactualizado. (Ej: https://browser-update.org/)

* Control de versiones: deberán estar etiquetadas con correspondiente nombre con el formato "vx.x.x". 

### **Front-end:**

Las tecnologías a utilizar para el desarrollo front-end de las aplicaciones son:

* **HTML5**: Código semántico y organizado para asegurar la accesibilidad del contenido. 

* **CSS3**: Uso de las últimas versiones, siempre teniendo en cuenta el soporte de los navegadores de las diferentes propiedades.

### **Maquetado responsive**

Todos los sitios deben poder verse desde cualquier dispositivo que se utilice.

El soporte mínimo que se debe dar es para las siguientes resoluciones:

<table>
  <tr>
    <td></td>
    <td>Tamaño mínimo</td>
    <td>Tamaño máximo</td>
  </tr>
  <tr>
    <td>Extra small</td>
    <td>240 x 480 px</td>
    <td> 767px</td>
  </tr>
  <tr>
    <td>Small</td>
    <td>768px</td>
    <td>991px</td>
  </tr>
  <tr>
    <td>Medium</td>
    <td>992px</td>
    <td>1199px</td>
  </tr>
  <tr>
    <td>Large</td>
    <td>1200px</td>
    <td>2560 x 1440 px</td>
  </tr>
</table>


## **Seguridad**

La comunicación con los web services debe ser encriptada usando un certificado SSL/TLS.

Todas las URL que lanza una aplicación deben ser https.

Sólo se deben pedir al usuario los permisos mínimos y estrictamente los que son necesarios.

Los datos de los usuarios usados en la registración deben ser guardados con seguridad.

Limitar cantidad de intentos de logins.

Se deben actualizar los frameworks de desarrollo para evitar vulnerabilidades de seguridad. 

## **Métricas**

**Caso 1: El sitio web no cuenta con Google Analytics**

Se deberá hacer la integración muy simple en su sitio web mediante la implementación de un pequeño código provisto por la Dirección Nacional de Servicios Digitales.

**Caso 2: El sitio web cuenta con Google Analytics**

Se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el fin de análisis de información.

**Para todos los casos**

Serán provistos de un código o etiqueta que deberá ser implementado en todas las páginas de su sitio web. La implementación es muy simple y se detalla en el documento de [Implementación de Google Tag Manager](https://github.com/argob/estandares/blob/master/implementacion-gtm.md)
