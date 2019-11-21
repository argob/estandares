# Estándares de sitios web

**Ministerio de Modernización**

Dirección Nacional de Servicios Digitales

## Índice

* [Objetivo](#objetivo)
* [Diseño](#diseño)
    * [Estrategia de UX](#estrategia-de-ux)
    * [Uso de Poncho](#uso-de-poncho)
* [Contenido](#contenido)
* [Desarrollo](#desarrollo)
* [Seguridad](#seguridad)
* [Métricas](#métricas)

## Objetivo: 

El presente documento tiene como objetivo definir las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar todo sitio web del Estado Nacional, ya sea realizado por empleados del Estado o personal tercerizado, con el fin de ser utilizados por ciudadanos.

Con los siguientes estándares, se busca homogeneizar la experiencia entre los diversos activos del estado, para facilitar la comprensión y utilización, primando la Usabilidad, la Accesibilidad y la Experiencia.

## **Diseño**

### **Estrategia de UX**

La UX o experiencia de usuario sucede en base al diseño, contenidos y performance del sitio. Al momento de pensar en la utilidad del sitio para los ciudadanos se debe tener en cuenta:

1. Investigar (con usuarios y métricas) qué servicios son los más usados o requeridos y **que sea lo primero que se vea al entrar al sitio** (y así mismo darles diferentes jerarquías a los servicios según su uso).

2. Ayudar al usuario a entender dónde está y qué tiene que hacer, con títulos, breadcrumbs y botones con textos claros (ej: no usar "hacer click acá" si no "descargar tarifas de peajes 2019"). También usar textos y animaciones de "cargando" para cuando el sitio vaya a tardar para mostrar información.

3. Al momento de disponibilizar de forma digital un servicio, también mejorar el servicio. Por ejemplo un formulario debe tener sólo los datos necesarios para que el ciudadano pueda usar el servicio, no datos personales que sirvan sólo para estadísticas, por lo cual se puede cambiar el servicio para que tanto su versión en papel como la digital tengan menos campos para completar.

### **Uso de Poncho**

http://argob.github.io/poncho/

Poncho es la librería de estilos y componentes para diseñar y desarrollar sitios web del Estado Nacional. Contiene lineamientos y soluciones específicas para reutilizar:

* **Identidad:** Usar los colores, íconos y tipografía (Roboto) de Poncho: http://argob.github.io/poncho/identidad/colores/

* **Componentes:** Usar los componentes de Poncho http://argob.github.io/poncho/identidad/colores/ (en el caso de necesitar componentes nuevos se pueden hacer basandose en componentes de Bootstrap 3 y Material Design).

* **Plantillas:** Las plantillas son páginas con componentes necesarios para que la misma cumpla alguna función. Su uso es opcional pero ayuda a entender cómo combinar los componentes.

* **Headers y footers:** Los headers de sitios externos a argentina.gob.ar deben tener el título del sitio en la esquina superior izquierda, como se muestra en esta plantilla: http://argob.github.io/poncho/plantillas/headers-y-footers/header-footer-v2.html

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
