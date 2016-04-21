# Estándares de Apps Móviles

**Ministerio de Modernización**

Dirección Nacional de Servicios Digitales

Versión: 0.1 


## Índice:

* [Objetivo](#objetivo)
* [Requisitos](#requisitos)
    * [Desarrollo](#desarrollo) 
    * [Diseño:](#diseño) 
        * [Colores](#colores) 
        * [Tipografías](#tipografías) 
        * [Estética y elementos gráficos](#estética-y-elementos-gráficos)  
    * [Usabilidad](#usabilidad) 
    * [Seguridad](#seguridad) 
    * [Métricas](#métricas) 
    * [Publicación](#publicación)

## Objetivo: 

El presente documento tiene como objetivo definir las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar toda aplicación móvil del Estado Nacional, ya sea realizada desde el Estado o por un proveedor externo, con el fin de ser utilizados por ciudadanos.

Con los siguientes estándares, se busca homogeneizar la experiencia entre los diversos activos del Estado, para facilitar la comprensión y utilización, primando la Usabilidad, la Accesibilidad y la Experiencia.

 

## Requisitos

### **Desarrollo** 

* Las aplicaciones deben soportar las distintas resoluciones de los distintos tipos de dispositivos. 

* El instalador de las aplicaciones no debe superar los 10 MB.

* No embeber imágenes y videos como contenido estático que hagan que los instaladores sean más pesados.

* Las aplicaciones que no tengan backend propio pueden utilizar el portal de argentina.gob.ar para consumir contenidos dinámicos, respetando los lineamientos del Estándar de API definida por la Coordinación de Desarrollo de Servicios Digitales.

* La lista de aplicaciones de cada ministerio debe estar actualizada. Si la aplicación no está más en funcionamiento (o con soporte) hay que removerla de las tiendas.

* El código fuente de las aplicaciones deberá ser simple, fácil de comprender, escalable, flexible y deberá ser acompañado de la documentación necesaria para poder asegurar su continuidad soportando un futuro cambio de proveedor.

*  Generar y proveer los manuales de uso necesarios para el ciudadano que utiliza la aplicación móvil.

* Control de Versiones: 

    * **versión v 0.0.1**: Resolución de bugs de versiones actuales.

    * **versión v.0.1.0**: Nueva funcionalidad dentro de la versión actual.

    * **versión v.1.0.0**: Representan un cambio sustancial respecto de la funcionalidad o de la estética actual del sitio. 

* Las aplicaciones con sistemas de registración deben seguir los lineamientos definidos por la Coordinación de Identidad digital y Tarjeta Inteligente de Servicios Digitales.

     **¿Por qué?**

  Brinda un sistema homogéneo de registración para los ciudadanos en todas las propiedades digitales del gobierno.

* Todo contenido que muestra la aplicación debe ser consumido mediante una API respetando los lineamientos del Estándar de API definida por la Coordinación de Desarrollo de Servicios Digitales y el Estándar de Contenido definida por la Coordinación de Contenidos de Servicios Digitales.

  **¿Por qué?**

  Permite actualizar el contenido de forma dinámica sin necesidad de generar una nueva versión de la aplicación y homogeneizando un lenguaje común para todas las propiedades digitales del gobierno.

* La aplicación debe brindar la posibilidad de operar en forma total o parcial en modo offline (sin conexión). La sincronización y actualización de contenidos se llevarán a cabo una vez que el dispositivo se encuentre nuevamente en modo online.

	**¿Por qué?** 

  Evitar el tráfico de datos innecesarios para el ciudadano y brindar la posibilidad de usar la aplicación aún cuando no se cuenta con una conexión a Internet.

* El desarrollo se realizará para que sea compatible con la última versión más estable del sistema operativo y contemplando las versiones previas que aún siguen siendo populares.  

### **Diseño**

* Los nombres de las aplicaciones deberán contar con la aprobación de la Dirección Nacional de Servicios Digitales. 

* Los iconos lanzadores de las aplicaciones serán creados y provistos por la Coordinación de Diseño de Servicios Digitales.

  **¿Por qué?**

  Brinda un sistema visual homogéneo para todas las propiedades digitales del gobierno.

#### **Colores:**

La paleta de colores a utilizar es la definida en el manual de identidad visual para web y aplicaciones móviles. Los usos son los siguientes:

* **Primario**:   #0072BC  
Es el color primario que se utiliza dentro de la UI en elementos como links, botones, etc.

* **Secundario**:   #00B9F1
Se utiliza para ciertos elementos del contenido que necesitan ser destacados, por ejemplo en iconos.

* **Complementario**:   #FD4138
Se utiliza para elementos que necesiten un destaque diferencial y en ciertos elementos para dar calidez en páginas muy extensas que no contengan fotografías.

* **Neutros**: 

    * **Texto**: #111111

    * **Gris claro**: #767676

    * **Bordes y detalles**: #CCCCCC

    * **Fondo**: #F5F5F5

    * **Blanco**: #FFFFFF

#### **Tipografías:**

La familia tipográfica estándar es **Roboto** dada su alta legibilidad en medios digitales.

Para textos largos se usa Droid Serif para cansar menos al lector, ya que por su forma las letras se identifican más fácil.

Ambas familias tipográficas están hechas por Google y su uso es libre y gratuito bajo licencia Apache 2.0.

#### **Estética y elementos gráficos:**

Como estética se usa un sistema visual minimalista "flat" en donde predomina el diseño del contenido evitando el uso de ornamentos que distraigan.

Los elementos se componen de figuras simples con colores plenos, evitando el uso de degradados.

Se recomienda el uso de fotografías como parte del contenido, ya que hace más amena la lectura y ayuda a la comunicación. Ver los Estándares de Contenido para más información.

### **Usabilidad**

1. Diseñar para todas las resoluciones de pantalla de computadoras, tablets y celulares posibles.

2. Usar convenciones de estética y funcionamiento de cada plataforma o sistema operativo (Ej: [Guía Google](https://www.google.com/design/spec/material-design/introduction.html), [Guía iOS](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/), [Guía BlackBerry](https://developer.blackberry.com/design/bb10/), [Guía Windows Phone](https://blogs.msdn.microsoft.com/africaapps/2014/03/08/uxui-guidelines-for-windows-phone-8/). Para sitios web se deben respetar sólo los lineamientos de identidad visual).

3. Entender qué funcionalidades son las más usadas (sobre la  base de la medición de analíticas y pruebas de usabilidad) para hacerlas más fácil de acceder en futuras versiones.

4. Mostrar al usuario el estado del sistema en todo momento. Dónde está (títulos y breadcrumbs), lo que está haciendo y de que se trata (títulos y descripciones), cuál es su progreso (indicadores de carga y barras de progreso), etc).

5. Brindar una respuesta inmediata a cada interacción (un cambio visual, un mensaje de carga, etc).

6. Los elementos interactivos deben tener un estilo para cuando está:

    1. En estado normal

    2. En foco

    3. Activo (cuando se está haciendo clic o tap)

    4. Visitado (para enlaces dentro de un párrafo).

7. Los botones o áreas interactivas deben ser grandes como para no necesitar precisión al hacer click o tap. Esta necesidad está basada en la [ley de Fitts.](https://es.wikipedia.org/wiki/Ley_de_Fitts) En aplicaciones móviles el mínimo de un área interactiva debe ser 44x44pts.

8. Los campos de formularios deben mostrar su etiqueta al estar completos. [Ver ejemplos de uso correctos e incorrectos.](https://www.nngroup.com/articles/form-design-placeholders/)


### **Seguridad**

* La comunicación con los web services debe ser encriptada usando un certificado SSL/TLS

* Todas las URL que lanza una aplicación deben ser https.

* Solo se deben pedir al usuario los permisos mínimos y estrictamente los que son necesarios.

* Los datos de los usuarios usados en la registración deben ser guardados con seguridad.

* Limitar cantidad de intentos de logins.

* Se deben actualizar los frameworks de desarrollo para evitar vulnerabilidades de seguridad. 

### **Métricas**

* Las aplicaciones que no cuentan con Google Analytics deben incorporar el ID y métricas provistos por la Coordinación de Análisis de Datos de Servicios Digitales. En caso de disponer, se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el análisis de información.

  **¿Por qué?**

  Para conocer más acerca de Google Tag Manager, véase el apartado "Referencias".

* Las aplicaciones deben incorporar registros de errores y fallas.

  **¿Por qué?**

  Permite registrar, identificar y rastrear las fallas que se generan dentro de las aplicaciones, y poder resolverlos para mantener la mejora continua de las aplicaciones y ofrecer una mejor experiencia de uso al ciudadano.

**Aplicación nativa en Android**

*Caso 1: Aplicaciones sin código de seguimiento pre-implementado.*

Para implementar código de seguimiento en aplicaciones Android deberá consultar el documento __"Implementación de Google Tag Manager"__. Chequear link abajo.

*Caso 2: Aplicaciones con código de seguimiento previamente implementado.*

En caso de poseer código de seguimiento se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el fin de análisis de información. Asimismo se deberá modificar el mismo para que se adapte a los estandares propuestos en el documento de "Guía de estandarización de métricas digitales".

**Aplicación nativa en IOS**

*Caso 1: Aplicaciones sin código de seguimiento pre-implementado.*

Para implementar código de seguimiento en aplicaciones IOS deberá consultar el documento **"Implementación de Google Tag Manager"**. Chequear link abajo.

*Caso 2: Aplicaciones con código de seguimiento previamente implementado.*

En caso de poseer código de seguimiento se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el fin de análisis de información. Asimismo se deberá modificar el mismo para que se adapte a los estandares propuestos en el documento de "Guía de estandarización de métricas digitales".

### **Publicación**

* Las aplicaciones se subirán a las distintas tiendas de Servicios Digitales, excepto en caso de aplicaciones ya existentes.

   **¿Por qué?**

  Mantener una tienda centralizada permite al ciudadano conocer de una manera directa cuáles otros servicios y productos están disponibles. 

* Las aplicaciones las firmará Servicios Digitales con la firma y certificados propietaria. 

  **¿Por qué?** 

  Para lograr mantener la continuidad del producto sin importar el desarrollador o tercero.

* Los Ministerios deben entregar las cuentas de las distintas tiendas y/o repositorios donde estén alojadas las aplicaciones a Servicios Digitales y las firmas digitales (alias y contraseñas) y/o certificados para publicar aplicaciones.

  **¿Por qué?**

  Para llevar un control y un seguimiento de los lineamientos establecidos por la Dirección Nacional.

* Los ministerios que dispongan de sus propios proveedores deberán trabajar en un repositorio provisto por Servicios Digitales.

  **¿Por qué?**

  Para lograr mantener la continuidad del producto sin importar el desarrollador o tercero.

* Los identificadores de cada aplicación deben ser únicos para cada dispositivo y tener el siguiente formato: 

  ar.gob.nombre_aplicacion

  **¿Por qué?**

  * Permite tener homogeneidad en los identificadores de todas las aplicaciones. 
  * Permite que exista una única aplicación instalada dentro del dispositivo. 
  * Una vez publicadas las aplicaciones en las tiendas, los identificadores no pueden ser cambiados ni removidos porque sino se considera una nueva aplicación, completamente distinta de la anterior y no una nueva versión del mismo.

* Los datos y las capturas de pantallas de las aplicaciones a ser publicadas deben ser provistas por cada Ministerio/Secretaría, respetando las plantillas provistas por la Coordinación de Aplicaciones Móviles.

* Los datos de contactos/web/detalle de cada aplicación deben pertenecer a cada Ministerio/Secretaría y ser provistos para la carga en las tiendas.

  **¿Por qué?**

  Es importante que el ciudadano pueda contactarse con las áreas que publican las aplicaciones para disponibilizar información que crea necesaria. 

