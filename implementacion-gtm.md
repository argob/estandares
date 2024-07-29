# Implementación de Google Tag Manager

**Secretaría de Innovación, Ciencia y Tecnología**
- Subsecretaría de Tecnologías de la Información y las Comunicaciones  
  -   Dirección Nacional de Servicios Digitales

Versión: 0.1 

## Índice:

* [Objetivo](#objetivo)
* [Introducción](#introducción)
* [Tipos de implementación](#tipos-de-implementación)
    * [Websites](#websites)
    * [Instalando el código de seguimiento en su sitio web](#instalando-el-código-de-seguimiento-en-su-sitio-web)
    * [Implementando Google Tag Manager en aplicaciones nativas (Android y IOS)](#implementando-google-tag-manager-en-aplicaciones-nativas-android-y-ios)
        * [Introducción general](#introducción-general)
        * [Para implementar una aplicación Android nativa](#para-implementar-una-aplicación-android-nativa)
        * [Para implementar una aplicación iOS nativa](#para-implementar-una-aplicación-ios-nativa)

## Objetivo

El objetivo de este documento es explicar los prerrequisitos y pasos necesarios para implementar Google Tag Manager (GTM) en las distintas plataformas que deberán incluirse en el proyecto de estandarización de métricas web propuesto por **Gobierno Digital**.

En este documento, se encuentra además el vínculo a la "Guía de estandarización de métricas digitales" que contiene los detalles de cómo se espera la información en los reportes de Google Analytics.

## Introducción

El objetivo de esta documentación es proveer los prerrequisitos necesarios para la implementación del código de seguimiento de Google Tag Manager para los tres tipos de sitios implementados en la actualidad.

Esta guía contiene los primeros pasos fundamentales que son requeridos para una correcta implementación.

En todos los casos las etiquetas de seguimiento de Google Tag Manager serán provistas por **Gobierno Digital**, y solo se aceptarán como válidas las etiquetas provistas por este organismo.

No se podrá implementar otras etiquetas de Google Analytics o Google Tag Manager que no sean las provistas por **Gobierno Digital**.

## Tipos de Implementación.

### Websites

Para añadir el código de seguimiento de Google Tag Manager (GTM) a las páginas web se proporciona un fragmento de contenedor para cada contenedor web. 

### Instalando el código de seguimiento en su sitio web.

* **Gobierno Digital** va a proveer a el/los desarrollador/es un código único llamado ID, con el formato **GTM-XXXXX**.

* El/los desarrolladores deberán copiar y pegar el fragmento de código en su sitio web. Pegue este código de modo que aparezca inmediatamente después de la etiqueta <body> de apertura en todas las páginas del sitio:

* Observe la parte del código **GTM-XXXXXX**: es el identificador único de cada uno de sus contenedores. 

* **IMPORTANTE:** Quite las etiquetas previas que están ahora en el contenedor del Tag Manager de Google (en caso de requerir acceso a los reportes diríjase al apartado "pedido de acceso a reportes).

### Implementando Google Tag Manager en aplicaciones nativas (Android y IOS)

#### Introducción general

Google Tag Manager permite a los desarrolladores cambiar los valores de configuración en su aplicación móvil usando Google Tag Manager sin tener que reconstruir y volver a presentar binarios de la aplicación a los mercados de aplicaciones.

Esto es útil para la gestión de los valores de configuración o banderas de la aplicación que tenga que cambiar en el futuro, incluyendo:

* Otros ajustes de la interfaz de usuario y strings de presentación.

* Tamaños, ubicaciones o tipos de anuncios que se publiquen en su aplicación.

* Varias opciones de la usabilidad.

Los valores de configuración también pueden ser evaluados durante la ejecución mediante normas, lo que permite configuraciones dinámicas, tales como:

* Modificar el tamaño de las secciones o publicidades basados en la resolución de pantalla.

* Usar el lenguaje y la ubicación para configurar elementos de la IU.

Google Tag Manager también permite la implementación dinámica de códigos de seguimiento específicos y de los píxeles en las aplicaciones. Los desarrolladores pueden empujar eventos importantes en una capa de datos y decidir después qué etiquetas o píxeles de seguimiento deben ser enviados. Actualmente Tag Manager admite las siguientes etiquetas:

* Google Analytics para aplicaciones móviles

* DoubleClick

* Función personalizada de llamadas

#### Para implementar una aplicación Android nativa

1. Instalar el [SDK de Android](https://developer.android.com/sdk/index.html)

2. Descargar la aplicación [Google Play SDK](https://developer.android.com/google/play-services/setup.html) de servicios

3. Pedir la etiqueta de GTM correspondiente a su sitio. (**Gobierno Digital**)

4. Implementar la etiqueta de GTM en la app.

Una vez que haya completado estos pasos, y siguiendo la documentación provista podrá configurar y utilizar Google Tag Manager dentro de su aplicación Android.

**Empezando**

Siguiendo esta guía de introducción, usted podrá:

* [Añadir Google Tag Manager a su proyecto](https://developers.google.com/tag-manager/android/v4/#add)

* [Inicializar TagManager en su aplicación](https://developers.google.com/tag-manager/android/v4/#init)

* [GET valores de configuración de un contenedor de Tag Manager](https://developers.google.com/tag-manager/android/v4/#get)

* [PUSH los valores y eventos en dataLayer](https://developers.google.com/tag-manager/android/v4/#push)

* [Vista previa, depuración y publicación de su contenedor](https://developers.google.com/tag-manager/android/v4/#preview-publish)

Esta guía utiliza fragmentos de código a partir de los animales lindos de la aplicación de ejemplo incluido en el SDK de servicios de Google Play. La fuente completa para este proyecto está disponible en:

    <android-sdk-directorio>/extras/google/google_play_services/tagmanager/cuteanimals.

**LINK a la documentación completa para ANDROID.**

[https://developers.google.com/tag-manager/android/v4/#getting-started](https://developers.google.com/tag-manager/android/v4/#getting-started)

#### Para implementar una aplicación iOS nativa

Antes de utilizar esta guía de instalación inicial, necesitará lo siguiente:

* Una cuenta de Google Tag Manager

* Un nuevo contenedor Tag Manager con [macro de recolección de datos](https://support.google.com/tagmanager/answer/3127354)

* Una aplicación móvil para iOS para implementar Google Tag Manager

* El [SDK de servicio de Google Analytics](https://developers.google.com/analytics/devguides/collection/ios/resources), que contiene la biblioteca Tag Manager.

**Empezando**

Después de seguir esta guía de introducción, usted podrá:

* Añadir el [SDK de Google Tag Manager](https://developers.google.com/tag-manager/ios/v3/#add-sdk) a su proyecto

* Establecer los [valores predeterminados para contenedores](https://developers.google.com/tag-manager/ios/v3/#set-default)

* [Abrir el contenedor](https://developers.google.com/tag-manager/ios/v3/#open-container)

* [GET valores de configuración del contenedor](https://developers.google.com/tag-manager/ios/v3/#get-values)

* [Eventos PUSH al DataLayer](https://developers.google.com/tag-manager/ios/v3/#push-datalayer)

* [Vista previa y publicación](https://developers.google.com/tag-manager/ios/v3/#preview-publish) del Contenedor

**Para Agregar el SDK de Google Tag Manager para su proyecto**

Antes de utilizar el SDK de Google Tag Manager, tendrá que añadir los archivos de cabecera del Tag Manager de Google (GTM) **libGoogleAnalyticsServices.a** desde el directorio **Library** del paquete SDK para su proyecto.

A continuación, añada lo siguiente a las bibliotecas vinculadas a su aplicación de destino si no están ya presentes:

__* CoreData.framework__

__* SystemConfiguration.framework__

__* libz.dylib__

__* libsqlite3.dylib__

__* libGoogleAnalyticsServices.a__

**LINK a la documentación completa para IOS.**

[https://developers.google.com/tag-manager/ios/v3/#intro](https://developers.google.com/tag-manager/ios/v3/#intro)

