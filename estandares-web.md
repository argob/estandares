# Estándares web


## Objetivo: 

El presente documento tiene como objetivo definir las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar todo sitio web del Estado Nacional, ya sea realizado por empleados del Estado o personal tercerizado, con el fin de ser utilizados por ciudadanos.

Con los siguientes estándares, se busca homogeneizar la experiencia entre los diversos activos del estado, para facilitar la comprensión y utilización, primando la Usabilidad, la Accesibilidad y la Experiencia.

 

## Requisitos

### **1**. **Desarrollo**

* Se pueden usar redirects desde dominios a otros dominios.

* Los sitios web que sean la base del dominio deben usarse con www.
Ejemplo [www.educacion.gob.ar](http://www.educacion.gob.ar). Si uno ingresa a [educacion.gob.ar](http://educacion.gob.ar) se deberá generar redirect 301 al dominio con las www.

* Todos los sitios web del Estado usarán la terminación .gob.ar. El registro de .gov.ar deberá generar un redirect 301 al dominio gob.ar.

* Todos los sitios web que ofrezcan servicios de consulta online (mostrar ejemplos) deben tener una API disponible y/o planificada su implementación. (Ver estándares de APIs).

* Todos los sitios con sistemas de registración deben seguir los lineamientos definidos por la coordinación de identidad digital y tarjeta inteligente.

* Los sitios deben ser responsive para poder adaptarse y poder ser navegables desde diversos dispositivos, como por ejemplo dispositivos móviles.

* Todos los sitios y aplicaciones deberán contar con el mínimo de documentación necesaria para ser instalados en diferentes entornos.

* Compatibilidad con los siguientes navegadores

    * Internet Explorer 8 (NOTE:  Para versiones menores a IE8, debe aparecer una alerta avisando que el navegador está desactualizado, como esto: https://browser-update.org/)

    * Chrome 19

    * Firefox 3

    * Safari 6

* Control de versiones: deberán estar etiquetadas con correspondiente nombre con el formato "vx.x.x". 

### **2.** **Diseño**

* **Aplicación de marca sobre logotipo del área**: los logotipos de las áreas de gobierno deben respetar los lineamientos del Manual de identidad visual para web y aplicaciones móviles [link al manual]. Dependiendo de la cantidad de caracteres que tenga el nombre del área puede representarse con 1, 2 o 3 líneas de texto, junto a la leyenda "Presidencia de la Nación" y el Escudo de la Nación.

* **Uso de encabezados**: los encabezados deben tener un alto mínimo de 72px y fondo de color pleno blanco o color primario de la paleta. El logotipo debe tener un alto de 50px y ancho proporcional. Éste debe estar a 10px del margen superior y preferentemente alineado al margen izquierdo del contenedor principal.

* **Uso de pie de página oficial**: al final de las páginas debe agregarse el pie de página que distingue a los sitios webs oficiales del gobierno. Este debe tener la leyenda: "Dominio.gob.ar es un sitio web oficial del Gobierno Argentino". Junto a este debe estar el logotipo de Argentina.gob.ar, el cual debe linkear la página de inicio de esa web.

![Pie de página oficial](img/pie-de-pagina.png)
*Ejemplo de footer en sitio web del Ministerio de Cultura*


* **Favicon**: Se debe utilizar la versión adjunta en formato .ico con las versiones de 16px y 32px embebidas.

  Dentro de los recursos adjuntos a este documento se pueden encontrar ejemplos de código para el encabezado y los tipos de pie de página, el favicon y las diferentes disposiciones del logotipo.

* **Justificación:** Brindar un sistema visual homogéneo acorde al manual de identidad y marca, entre todas las propiedades digitales del gobierno.

* **Recursos:** Están disponibles los recursos gráficos a través de la base para webs que busca homogeneizar y facilitar la creación de sitios web. 

#### **Colores:**

La paleta de colores a utilizar es la definida en el manual de identidad visual para web y aplicaciones móviles. Los usos son los siguientes:

* **Primario**:         #0072BC  
Es el color primario que se utiliza dentro de la UI en elementos como links, botones, etc.

* **Secundario**:         #00B9F1
Se utiliza para ciertos elementos del contenido que necesitan ser destacados, por ejemplo en íconos.

* **Complementario**:         #FD4138
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

Como estética se usa un sistema visual minimalista/flat donde predomina el diseño del contenido evitando el uso de ornamentos que distraigan o afecten la performance del sitio.

Los elementos se componen de figuras simples con colores plenos, evitando el uso de degradados.

Se recomienda el uso de fotografías como parte del contenido, ya que hace más amena la lectura y ayuda a la comunicación. Ver los estándares de contenido para más información.

#### **Responsive:**

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


#### **Soporte mínimo de navegadores:**

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


#### **Front-end:**

Las tecnologías a utilizar para el desarrollo front-end de las aplicaciones son:

* **HTML5**: Código semántico y organizado para asegurar la accesibilidad del contenido. 

* **CSS3**: Uso de las últimas versiones, siempre teniendo en cuenta el soporte de los navegadores de las diferentes propiedades.

### **3.** **Usabilidad**

1. Diseñar para todas las resoluciones de pantalla de computadoras, tablets y celulares posibles.

2. Usar convenciones de estética y funcionamiento de cada plataforma o sistema operativo (Ej: [Google Material Design,](https://www.google.com/design/spec/material-design/introduction.html) [iOS Guidelines.](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/) Para sitios web se deben respetar sólo los lineamientos de identidad visual).

3. Entender qué funcionalidades son las más usadas (en base a medición de analíticas y pruebas de usabilidad) para hacerlas más fácil de acceder en futuras versiones.

4. Mostrar al usuario el estado del sistema en todo momento. Dónde está (títulos y breadcrumbs), lo que está haciendo y de qué se trata (títulos y descripciones), cuál es su progreso (indicadores de carga y barras de progreso, etc).

5. Brindar una respuesta inmediata a cada interacción (un cambio visual, un mensaje de carga, etc).

6. Los elementos interactivos deben tener un estilo para cuando está:

    1. En estado normal

    2. En foco

    3. Over (mouse encima del elemento)

    4. Activo (cuando se está haciendo clic o tap)

    5. Visitado (para enlaces dentro de un párrafo).

7. Los botones o áreas interactivas deben ser grandes como para no necesitar precisión al hacer clic o tap. Esta necesidad está basada en la [ley de Fitts.](https://es.wikipedia.org/wiki/Ley_de_Fitts) En aplicaciones móviles el mínimo de un área interactiva debe ser 44x44pts.

8. Los campos de formularios deben mostrar su etiqueta al estar completos. [Ver ejemplos de uso correctos e incorrectos.](https://www.nngroup.com/articles/form-design-placeholders/)


### 4. **Accesibilidad**

1. Los textos deben cumplir las 5 reglas de legibilidad:

    1. El contraste mínimo del texto debe ser 4,5:1 (Para un fondo blanco #fff, el texto más claro posibles es #767676). Probarlo usando herramientas como por ejemplo [http://webaim.org/resources/contrastchecker/](http://webaim.org/resources/contrastchecker/)

    2. El cuerpo de texto mínimo para sitios web es de 14px/pts para párrafos y 12px/pts para anotaciones.

    3. Usar interlineado de párrafos de 1,5 a 2 veces el cuerpo de texto.

    4. La separación entre párrafos debe ser 1,5 veces el interlineado.

    5. No usar párrafos con texto justificado.

2. Usar subrayado para los enlaces (a menos que sea un menú o botón).

3. Las fotos deben tener un texto alternativo descriptivo.

4. No usar texto que en vez de ser texto es una imagen.

5. Incluir una vista de impresión, ya sea usando una hoja de estilos o una página aparte, para que todo contenido se vea bien al imprimir.

6. Usar subtítulos para videos.

7. En web, permitir el uso de un teclado sin necesidad de mouse.


### 5. **Seguridad**

La comunicación con los web services debe ser encriptada usando un certificado SSL/TLS

Todas las URL que lanza una aplicación deben ser https.

Sólo se deben pedir al usuario los permisos mínimos y estrictamente los que son necesarios.

Los datos de los usuarios usados en la registración deben ser guardados con seguridad.

Limitar cantidad de intentos de logins.

Se deben actualizar los frameworks de desarrollo para evitar vulnerabilidades de seguridad. 

### 6. **Métricas**

**Caso 1: El sitio web no cuenta con Google Analytics**

Se deberá hacer la integración muy simple en su sitio web mediante la implementación de un pequeño código provisto por el Área de Servicios Digitales

**Caso 2: El sitio web cuenta con Google Analytics**

Se deberá brindar permisos de administración a una cuenta proporcionada únicamente para el fin de análisis de información.

**Para todos los casos**

Serán provistos de un código o etiqueta que deberá ser implementado en todas las páginas de su sitio web. La implementación es muy simple y se detalla en el documento de "Implementación de Google Tag Manager" disponible en el siguiente enlace: ######

Para conocer más acerca de Google Tag Manager, véase el apartado "Referencias"

### Referencias

¿Qué es Google Analytics?

[https://es.wikipedia.org/wiki/Google_Analytics](https://es.wikipedia.org/wiki/Google_Analytics)

¿Qué es Google Tag Manager?

[https://support.google.com/tagmanager/answer/6102821?hl=es](https://support.google.com/tagmanager/answer/6102821?hl=es)

¿Qué es una etiqueta? 

[https://support.google.com/tagmanager/answer/6102821?hl=es](https://support.google.com/tagmanager/answer/6102821?hl=es)

¿Qué es SEO? (Posicionamiento en Buscadores)

[https://es.wikipedia.org/wiki/Posicionamiento_en_buscadores](https://es.wikipedia.org/wiki/Posicionamiento_en_buscadores)

