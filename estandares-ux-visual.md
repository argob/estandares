# Estándares de Diseño de UX e Identidad Visual para sitios web y aplicaciones móviles

**Secretaría de Innovación, Ciencia y Tecnología**
- Subsecretaría de Tecnologías de la Información y las Comunicaciones  
  -   Dirección Nacional de Servicios Digitales

## Índice

* [Objetivo](#objetivo)
* [Principios de UX](#principios-de-ux)
* [Uso de Poncho para sitios web](#uso-de-poncho-para-sitios-web)
* [Uso de Poncho para aplicaciones móviles](#uso-de-poncho-para-aplicaciones-móviles)

## **Objetivo**

Este documento define las pautas elementales a ser consideradas al momento de idear y diseñar sitios webs y aplicaciones móviles del Estado Nacional, ya sean realizadas desde el Estado o por un proveedor externo, con el fin de ser utilizadas por ciudadanos.

## **Principios de UX**

La UX o experiencia de usuario sucede en base al diseño, contenidos y performance del sitio. Al momento de pensar en la utilidad del sitio para los ciudadanos se debe tener en cuenta:

1. Investigar (con usuarios y métricas) **qué servicios son los más usados o demandados** y que sea lo primero que se vea al entrar al sitio (y así mismo darles diferentes jerarquías a los servicios según su uso).

2. **Ayudar al usuario a entender dónde está y qué tiene que hacer,** con títulos, breadcrumbs y botones con textos claros (ej: no usar "hacer click acá" si no "descargar tarifas de peajes 2019"). También usar textos y animaciones de "cargando" para cuando el sitio vaya a tardar para mostrar información.

3. Al momento de disponibilizar de forma digital un servicio, **también mejorar el servicio.** Por ejemplo un formulario debe tener sólo los datos necesarios para que el ciudadano pueda usar el servicio, no datos personales que sirvan sólo para estadísticas, por lo cual se puede cambiar el servicio para que tanto su versión en papel como la digital tengan menos campos para completar.

## **Uso de Poncho para sitios web**

http://argob.github.io/poncho/

Poncho es la librería de estilos y componentes para diseñar y desarrollar sitios web del Estado Nacional. Contiene lineamientos y soluciones específicas para reutilizar:

* **Identidad:** Usar los colores, íconos y tipografía ([Lora](https://fonts.google.com/specimen/Lora) para titulares y [Montserrat](https://fonts.google.com/specimen/Montserrat) para cuerpos de texto) de Poncho: [Identidad](http://argob.github.io/poncho/identidad/colores/)

* **Componentes:** Usar los [componentes](https://argob.github.io/poncho/componentes/botones/) de Poncho (en el caso de necesitar componentes nuevos se pueden hacer basandose en componentes de Bootstrap 3 y Material Design).

* **Plantillas:** Las plantillas son páginas con componentes necesarios para que la misma cumpla alguna función. Su uso es opcional pero ayuda a entender cómo combinar los componentes. [Plantillas](https://argob.github.io/poncho/plantillas/headers-y-footers/)

* **Headers y footers:** Los headers de sitios externos a argentina.gob.ar deben tener el título del sitio en la esquina superior izquierda, como se muestra en esta plantilla: https://argob.github.io/poncho/plantillas/headers-y-footers/header-footer-v1.html

### **Uso de Poncho para aplicaciones móviles**

Las aplicaciones móviles tanto para Android como para iOS usan la identidad de Poncho (colores e íconos) pero según el sistema operativo usan diferentes tipografías, componentes y patrones de uso:

* **Android:** https://m3.material.io/

* **iOS:** https://developer.apple.com/design/human-interface-guidelines/designing-for-ios
