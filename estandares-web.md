# Estándares de sitios web

**Secretaría de Innovación Tecnológica del Sector Público**
- Subsecretaría de Servicios y País Digital
-- Dirección Nacional de Servicios Digitales

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

El estilo de comunicación de los sitios debe ser cercano al ciudadano, con lenguaje simple, preferentemente usando fotos con ciudadanos argentinos. Para más información ver la [Ficha para producción de contenidos web para Argentina.gob.ar
](https://github.com/argob/estandares/blob/master/Ficha%20de%20producci%C3%B3n%20de%20contenidos%20web%20para%20argentina.md)

## **Desarrollo**

* Se pueden usar redirects desde dominios a otros dominios (ej: www.salud.gob.ar redirige a www.argentina.gob.ar/salud)

* Los sitios web que sean la base del dominio deben usarse con www.
Ejemplo [www.educacion.gob.ar](http://www.educacion.gob.ar). Si uno ingresa a [educacion.gob.ar](http://educacion.gob.ar) se deberá generar redirect 301 al dominio con las www.

* Todos los sitios web del Estado usarán la terminación .gob.ar. El registro de .gov.ar deberá generar un redirect 301 al dominio gob.ar.

* Todos los sitios web que ofrezcan servicios de consulta online (mostrar ejemplos) deben tener una API disponible y/o planificada su implementación. (Ver estándares de APIs).

* Todos los sitios con servicios para el ciudadano que tengan que tener registro de usuarios deben usar el sistema de login de Mi Argentina (ID).

* Los sitios deben ser responsive para poder adaptarse y poder ser navegables desde diversos dispositivos como por ejemplo celulares.

* Todos los sitios y aplicaciones deberán contar con el mínimo de documentación necesaria para ser instalados en diferentes entornos.

* Compatibilidad con los siguientes navegadores

    * Internet Explorer 8 (NOTE:  Para versiones menores a IE8, debe aparecer una alerta avisando que el navegador está desactualizado, como esto: https://browser-update.org/)

    * Chrome 19

    * Firefox 3

    * Safari 6

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

### **Soporte mínimo de navegadores:**

Todos los sitios web deben poder verse bien y con todas sus funcionalidades andando en las siguientes versiones mínimas:

<table>
  <tr>
    <td></td>
    <td>Soporte medio</td>
    <td>Soporte completo</td>
  </tr>
  <tr>
    <td>Internet Explorer</td>
    <td>8 - 9</td>
    <td>10+</td>
  </tr>
  <tr>
    <td>Edge</td>
    <td>-</td>
    <td></td>
  </tr>
  <tr>
    <td>Firefox</td>
    <td>-</td>
    <td>3+</td>
  </tr>
  <tr>
    <td>Chrome</td>
    <td>-</td>
    <td>19+</td>
  </tr>
  <tr>
    <td>Safari</td>
    <td>-</td>
    <td>6+</td>
  </tr>
  <tr>
    <td>Opera</td>
    <td>-</td>
    <td></td>
  </tr>
  <tr>
    <td>iOS Safari</td>
    <td>4 - 6</td>
    <td>7+</td>
  </tr>
  <tr>
    <td>Android Browser</td>
    <td>2.0 - 2.6</td>
    <td>4 +</td>
  </tr>
  <tr>
    <td>Chrome para Android</td>
    <td>-</td>
    <td>19+</td>
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

Se deberá hacer la integración muy simple en su sitio web mediante la implementación de un pequeño código provisto por el Área de Servicios Digitales

**Caso 2: El sitio web cuenta con Google Analytics**

Se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el fin de análisis de información.

**Para todos los casos**

Serán provistos de un código o etiqueta que deberá ser implementado en todas las páginas de su sitio web. La implementación es muy simple y se detalla en el documento de [Implementación de Google Tag Manager](https://github.com/argob/estandares/blob/master/implementacion-gtm.md)
