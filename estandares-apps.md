# Estándares de apps móviles

**Secretaría de Innovación Tecnológica del Sector Público**
- Subsecretaría de Servicios y País Digital  
  -   Dirección Nacional de Servicios Digitales

## Índice

* [Objetivo](#objetivo)
* [Diseño](#diseño)
* [Desarrollo](#desarrollo)
* [Seguridad](#seguridad)
* [Métricas](#métricas)

## Objetivo: 

Este documento define las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar toda aplicación móvil del Estado Nacional, ya sea realizada desde el Estado o por un proveedor externo, con el fin de ser utilizados por ciudadanos.

## **Diseño**

La UX (experiencia de usuario) debe ser útil para el ciudadano además de fácil de entender y usar. La identidad visual debe ser homogénea entre los diferentes sitios del Gobierno (para lo cual se usa la librería de estilos y componentes [Poncho](http://argob.github.io/poncho/). Para más información ver los [Estándares de Diseño de UX e Identidad Visual](https://github.com/argob/estandares/blob/master/estandares-ux-visual.md)

Se debe tener en cuenta que una aplicación móvil es más costosa de desarrollar que un sitio web y es más dificil que un usuario la baje (en comparación a entrar a un sitio web). Por lo cual se debe evaluar con mayor rigurosidad si debe existir la aplicación o no. Por ejemplo en el caso de necesitar mostrar sólo información conviene hacer un sitio web, pero en el caso de tener que realizar una acción recurrente que dura poco, es posible que convenga hacer una aplicación.

## **Desarrollo** 

* Las aplicaciones deben soportar las distintas resoluciones de los distintos tipos de dispositivos. 

* El instalador de las aplicaciones no debe superar los 10 MB.

* No embeber imágenes y videos como contenido estático que hagan que los instaladores sean más pesados.

* Las aplicaciones que no tengan backend propio pueden utilizar el portal de [argentina.gob.ar](http://www.argentina.gob.ar/) para consumir contenidos dinámicos, respetando los lineamientos del Estándar de API definida por la Coordinación de Desarrollo de Servicios Digitales.

* La lista de aplicaciones de cada ministerio debe estar actualizada. Si la aplicación no está más en funcionamiento (o con soporte) hay que removerla de las tiendas.

* El código fuente de las aplicaciones deberá ser simple, fácil de comprender, escalable, flexible y deberá ser acompañado de la documentación necesaria para poder asegurar su continuidad soportando un futuro cambio de proveedor.

* Generar y proveer los manuales de uso necesarios para el ciudadano que utiliza la aplicación móvil.

* Control de Versiones: 

    * **versión v 0.0.1**: Resolución de bugs de versiones actuales.

    * **versión v.0.1.0**: Nueva funcionalidad dentro de la versión actual.

    * **versión v.1.0.0**: Representan un cambio sustancial respecto de la funcionalidad o de la estética actual del sitio. 

* Todas las aplicaciones con servicios para el ciudadano que tengan que tener registro de usuarios deben usar el sistema de login de Mi Argentina (ID).

* Todo contenido que muestra la aplicación debe ser consumido mediante una API respetando los lineamientos del Estándar de API definida por la Coordinación de Desarrollo de Servicios Digitales y el Estándar de Contenido definida por la Coordinación de Contenidos de Servicios Digitales.

* La aplicación debe brindar la posibilidad de operar en forma total o parcial en modo offline (sin conexión). La sincronización y actualización de contenidos se llevarán a cabo una vez que el dispositivo se encuentre nuevamente en modo online.

* El desarrollo se realizará para que sea compatible con la última versión más estable del sistema operativo y contemplando las versiones previas que aún siguen siendo populares.  

## **Seguridad**

* La comunicación con los web services debe ser encriptada usando un certificado SSL/TLS

* Todas las URL que lanza una aplicación deben ser https.

* Solo se deben pedir al usuario los permisos mínimos y estrictamente los que son necesarios.

* Los datos de los usuarios usados en la registración deben ser guardados con seguridad.

* Limitar cantidad de intentos de logins.

* Se deben actualizar los frameworks de desarrollo para evitar vulnerabilidades de seguridad. 

## **Métricas**

* Las aplicaciones que no cuentan con Google Analytics deben incorporar el ID y métricas provistos por la Coordinación de Análisis de Datos de Servicios Digitales. En caso de disponer, se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el análisis de información.

* Las aplicaciones deben incorporar registros de errores y fallas.

**Aplicación nativa en Android y iOS**

*Caso 1: Aplicaciones sin código de seguimiento pre-implementado.*

Para implementar código de seguimiento en aplicaciones ver el documento de [Implementación de Google Tag Manager](https://github.com/argob/estandares/blob/master/implementacion-gtm.md)

*Caso 2: Aplicaciones con código de seguimiento previamente implementado.*

En caso de poseer código de seguimiento se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el fin de análisis de información. Asimismo se deberá modificar el mismo para que se adapte a los estandares propuestos en el documento de "Guía de estandarización de métricas digitales".

## **Publicación**

* Las aplicaciones se subirán a las distintas tiendas de Servicios Digitales, excepto en caso de aplicaciones ya existentes.

* Las aplicaciones las firmará Servicios Digitales con la firma y certificados propietaria. 

* Los Ministerios deben entregar las cuentas de las distintas tiendas y/o repositorios donde estén alojadas las aplicaciones a Servicios Digitales y las firmas digitales (alias y contraseñas) y/o certificados para publicar aplicaciones.

* Los ministerios que dispongan de sus propios proveedores deberán trabajar en un repositorio provisto por Servicios Digitales.

* Los identificadores de cada aplicación deben ser únicos para cada dispositivo y tener el siguiente formato: 

  ar.gob.nombre_aplicacion

* Los datos y las capturas de pantallas de las aplicaciones a ser publicadas deben ser provistas por cada Ministerio/Secretaría, respetando las plantillas provistas por la Coordinación de Aplicaciones Móviles.

* Los datos de contactos/web/detalle de cada aplicación deben pertenecer a cada Ministerio/Secretaría y ser provistos para la carga en las tiendas.
