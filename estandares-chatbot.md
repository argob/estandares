# Diseño de Interfaces Conversacionales (Chatbots)

Prácticas recomendadas, uso de componentes y patrones, usuarios representativos, arquitectura, métricas y cuestiones a tener en cuenta.



* [Qué hace un chatbot](#qué-hace-un-chatbot)

* [Centrado en el usuario](#centrado-en-el-usuario)
	* [Investigación de usuario](#investigación-de-usuario)
	* [Hablar el lenguaje de los usuarios](#hablar-el-lenguaje-de-los-usuarios)

* [Arquitectura de la información](#seguridad)
	* [Cómo plasmar la arquitectura de un chatbot](#comó-plasmar-la-arquitectura-de-un-chatbot)
	* [Reglas (o intenciones) y Temas](reglas-o-intenciones-y-temas)
	* [Disparadores](#disparadores)
	* [Condicionales y variables](#condicionales)
	* [Identificación de usuarios](#identificación-de-usuarios)
	
* [Prácticas recomendadas](#practicas-recomendadas)
	* [Que parezca una conversación](#que-parezca-una-conversación)
	* [Que sea breve](#que-sea-breve)
	* [Que hable en el lenguaje del usuario](#que-hable-en-el-lenguaje-del-usuario)
	* [Personalidad y tono de comunicación](#personalidad-y-tono-de-comunicación)
	* [Accesibilidad/Lenguaje claro](#accesibilidad-/-lenguaje-claro)
	
* [Patrones de uso](#patrones-de-uso)
	* [Onboarding](#onboarding)
	* [Mensajes](#mensajes)
	* [Respuesta a “no entendidos”](#respuesta-a-no-entendidos)
	* [Respuestas genéricas](#respuestas-genéricas)
	* [Notificaciones/Campañas](#notificaciones-/-campañas)
	
* [Componentes](#componentes)
	* [Mensajes sólo texto](#mensajes-soló-texto)
	* [Pantalla de bienvenida](#pantalla-de-bienvenida)
	* [Archivos multimedia](#archivos-multimedia)
	* [Carruseles](#carrusel)
	* [“Pills” de respuestas rápidas](#pills-de-respuestas-rápidas)
	* [Menú persistente](#menú-persistente)
	* [APIS](#apis)

* [Métricas, monitoreos y mejoras](#métricas-monitoreos-y-mejoras)
	* [Monitoreo de conversaciones](#monitoreo-de-conversaciones)
	* [Métricas](#métricas)

## Qué hace un chatbot:



Un chatbot es una interfaz conversacional que permite un tipo particular de comunicación con los usuarios de un producto o servicio. Se trata de un chat en donde el usuario escribe y recibe respuestas automatizadas similares a las de una conversación con una persona, una extensión de la experiencia de chat que usamos en los teléfonos celulares. Usar un chatbot para relacionarnos con nuestros usuarios nos permite:

* Usar un lenguaje conversacional cercano al usuario
* Llegar a cualquier dispositivo (de escritorio o móvil, de gama alta o baja)
* Llegar a usuarios que ya tengan instaladas apps de mensajería
* Brindar un servicio de atención disponible las 24 horas
* Segmentar a los usuarios para enviar información personalizada
* Actualizar en el momento contenidos sin necesidad de desarrollo
* Monitorear las interacciones para mejorar el chatbot
* Obtener métricas de uso para realizar análisis estadístico


### Tipos de chatbots

Por un lado existen los chatbots que usan conversaciones automatizadas y otros que integran la atención automática con la de operadores “humanos”. Muchas plataformas incluyen funcionalidades para integrar atención automatizada y personalizada en base a prioridades, asignación de temas, cantidad de operadores disponibles, etc.

Por otro lado hay una diferencia entre los chatbots que funcionan con procesamiento de lenguaje natural y aprendizaje automático y los chatbots basados en reglas. En los chatbots basados en reglas se definen y cargan todas las respuestas posibles y se activan con determinadas interacciones. En ese caso el aprendizaje se logra mediante el monitoreo manual de conversaciones.

Y además los chatbots se pueden programar desde cero o utilizar plataformas pre existentes que proveen una interfaz de usuario para generar las interacciones. Existen plataformas pagas y gratuitas. Muchas son compatibles para integrarse con Messenger, Whatsapp y distintas aplicaciones o canales.

Esta guía tiene algunas consideraciones aplicables a todo tipo de diseño conversacional, pero se centra básicamente en cómo armar un bot basado en reglas y partiendo de una plataforma pre-diseñada. No explica cómo programar un chatbot desde cero o configurar la infraestructura donde se aloja.


## Centrado en el usuario

### Investigación de usuario

Es importante que el diseño del producto o servicio responda a un objetivo y resuelva un problema o necesidad de los futuros usuarios. Por eso recomendamos siempre realizar investigación de usuario en la etapa inicial. Entrevistando usuarios representativos podemos confirmar si lo que estamos pensando tiene usuarios potenciales, si van a adoptar la solución que propongamos, si existe la necesidad que pretendemos solucionar, cuáles son los dispositivos o tecnología a disposición de los usuarios y si hay algunas otras cuestiones relacionadas a los usuarios que debamos tener en cuenta.

Algunas metodologías o prácticas para la investigación de usuario que recomendamos son:

* Protopersonas y Personas
* Entrevistas personales y/o grupales semiestructuradas
* Pruebas de usabilidad

### Hablar el lenguaje de los usuarios

Es importante que la información esté redactada en términos que sean de uso corriente para los usuarios. Si utilizamos un lenguaje que sea difícil de comprender es muy probable que el usuario abandone la conversación. No es lo mismo un chatbot diseñado para estudiantes de medicina que para embarazadas de un centro de salud. No es lo mismo hablarle a gente joven que a gente mayor. Es importante indagar a los usuarios antes de definir el tono de comunicación con el que se van a diseñar las conversaciones.

## Arquitectura de información

### Cómo plasmar la arquitectura de un chatbot

Recomendamos tener la arquitectura de información definida previamente a la implementación. Por un lado, para permitir una puesta en común de cara entre los equipos y por otro para facilitar la operativa de mantenimiento y crecimiento. Sin un diseño de arquitectura ordenado es posible que se con el crecimiento del chatbot se cometan errores como por ejemplo que se dupliquen o superpongan contenidos y se creen reglas conflictivas entre sí. Además, un buen diseño de arquitectura va a redundar también en una buena experiencia de usuario.
Hay diversas formas de graficar un diseño de arquitectura de información como mapas, diagramas de flujo, flujos de acciones, wireframes y listas anidadas. Esto es útil para visualizar los recorridos que queremos para nuestros usuarios. En el caso de los chatbots es muy útil conocer de antemano los elementos que se utilizan para estructurar las interacciones, esto ayuda a plasmar un diseño de arquitectura que refleje fielmente lo que queremos implementar.



En general los bots basados en reglas se organizan en base a:

* **Disparadores**

	Son palabras claves que al ser escritas disparan reglas o temas. 
    
* **Reglas** (también llamadas intenciones)

	Se disparan como respuesta a botones, o disparadores que escribe o acciona el usuario. Pueden también ser invocadas por otras reglas en base a una determinada condición programada.

* **Temas**

	Son agrupadores de reglas y disparan menúes de reglas.
    
* **Variables**

	Son parámetros que se asignan a los usuarios en base a determinadas acciones que realizan o datos que suministran. Sirven para condicionar las reglas o los disparadores.
    
* **Condicionales**

	Son filtros en base a determinadas variables que sirven para derivar u orientar el recorrido del usuario.

#### Reglas (o intenciones) y Temas

* El chatbot basado en reglas funciona disparando al usuario mensajes o menúes de opciones a partir de palabras clave del usuario a las que llamamos “disparadores”. El bot también puede disparar reglas a partir de botones que se ofrecen al usuario para interactuar. Existe otro elemento que dispara contenido llamado “Temas”.

* Los temas agrupan a las reglas o intenciones.

* No se debe crear intenciones o temas con nombres repetidos aunque el bot permita hacerlo ya que al reordenarlas se pueden ocasionar confusiones.

* Los temas con las reglas que lo componen se pueden usar para armar menúes de opciones “automáticamente”. Si la plataforma la tiene, esta funcionalidad (add topic) arma menúes tomando los nombres de las reglas de un tema y los convierten en botones. Por eso es recomendable que:
	* Dentro de cada “tema” haya solamente reglas que tengan relación con ese tema.
	* Las reglas tengan siempre nombres “presentables” y entendibles. Por ejemplo si usamos el nombre “Regla_prueba1” esto puede terminar siendo un botón visto por el usuario.
	* No haya “temas” que engloben muchísimas intenciones por la construcción automática de menúes mencionada más arriba.

### Disparadores


Una de las formas de interacción principales de un chatbot son los llamados “disparadores”. Los disparadores son palabras “clave” que al ser escritas por los usuarios “disparan” determinadas “Reglas o intenciones” y “temas” del bot. Las reglas pueden emitir un mensaje de texto, un “carrusel”, un menú de botones etc. Los “temas” en general disparan un menú con varias reglas.

A tener en cuenta:

* Se recomienda que los disparadores para las reglas contengan siempre más de una palabra para que el bot pueda dar una respuesta más precisa y que la conversación parezca más real. Por ejemplo, en lugar de “alimentación”, incluir “alimentación embarazo” o “alimentación bebé”.

* Los temas sí responden a disparadores con una sola palabra como “alimentación” o “embarazo” ya que disparan un menú de reglas para que el usuario elija.

* Se debe prestar atención al uso de las palabras porque su raíz puede llevar a confusiones con las reglas. Esto se ajusta probando el uso de los disparadores y especialmente mediante los monitoreos de usuario.

* Estas palabras se pueden obtener en el inicio, durante la investigación de usuario previa y utilizando palabras en Google Trends. De todos modos, una vez que esté implementado, conviene calibrar y mejorar los disparadores mediante monitoreo el conversaciones.

### Condicionales y variables

Una forma de orientar la conversación es condicionarla en base a variables capturadas a partir de determinadas acciones. Es recomendable pensar desde el principio los casos de uso o “trayectorias” para encauzar la conversación en una buena experiencia. Por ejemplo, si le damos al usuario una lista de temas en un menú de botones para elegir como “Salud, Educación, Transporte”, podemos capturar el botón seleccionado, en este caso, “Transporte” en la variable “Consulta tema” y a partir de eso ofrecerle más contenidos relacionados al que eligió previamente..
Las variables también se usan para condicionar los disparadores, por ejemplo que el disparador “vacunas bebé” dispare determinada regla si el usuario recibió o no determinada campaña de vacunación, etc. Para eso debemos generar las variables previamente.


### Identificación de usuarios

Un elemento a tener en cuenta al pensar la arquitectura es definir desde el principio si el usuario va a estar identificado o va a tener sesiones de usuario aisladas. En el caso de usuarios que están registrados que llegan a un chatbot por Facebook, Messenger, Whatsapp, SMS o alguna red social se pueden realizar acciones de seguimiento que no son posibles en los usuarios de 1 sola sesión como es el caso de los webchats. Por ejemplo, notificaciones, recordatorios, etc.

## Prácticas recomendadas

### Que parezca una conversación

La idea del chatbot es que parezca una conversación con el usuario. Esto parece obvio, pero diseñando bots, a veces se parte de contenidos con información “en crudo”, originalmente pensada para un texto en un sitio, un libro, un folleto, etc.  El trabajo es convertir ese contenido en una conversación y para eso tendremos que funcionar como “guionistas” o “dialoguistas”, pensando la redacción de los mensajes para que simulen una charla. En un chatbot la interfaz de usuario son los mensajes que guían la conversación y el hecho de que parezcan reales ayuda a que la experiencia fluya. Aunque el usuario sepa que está hablando con un bot, una vez que comience la conversación va a esperar ese tipo de intercambio.

### Que sea breve

Los mensajes tienen que ser breves, más o menos de 140 caracteres, como un tweet. Esto es principalmente para que entren en la pantalla del celular o la ventana del webchat. Interactuar con un mensaje largo es muy incómodo físicamente. En el caso de tener contenido muy largo se puede utilizar botones conectores, como “Seguir leyendo”, que además son útiles para medir el interés de los usuarios en el contenido que están recibiendo.

### Que hable en el lenguaje del usuario

Es importante que los mensajes y otros textos, como botones, estén redactados en el lenguaje del usuario y que sean comprendidos por la mayoría de ellos.
Profundizamos este tema en este mismo documento en:

* [El lenguaje de los usuarios](#hablar-el-lenguaje-de-los-usuarios)
* [Mensajes](#mensajes)
* [Accesibilidad/Lenguaje claro](#accesibilidad-/-lenguaje-claro)

### Personalidad y tono de comunicación

Es importante definir un tono y estilo de comunicación consistente para la redacción de los mensajes de respuesta del chatbot. La falta de consistencia puede romper la ilusión del chateo y generar desconfianza en el usuario. Además, en un equipo de trabajo es posible que la redacción no esté a cargo de una sola persona y por eso es necesario plasmar un manual de estilo.

Lo ideal es que además el tono de comunicación responda a una “personalidad” diseñada para el chatbot. Esto facilita bastante el diseño de los mensajes, es más fácil pensar la redacción si nos ponemos en el lugar del emisor como un “personaje”.

Algunas cuestiones que recomendamos:

* **¿A quién le estoy hablando?**

	Es importante mantener la concordancia en la persona del receptor. Si le hablamos de “tú” o de “vos” no le hablemos de “Usted” en otro mensaje.
    
* **¿Quién habla?**

	Es importante respetar en la redacción la persona del emisor (plural, singular).
    
    Ej, si le dijimos “te vamos a enviar la dirección” no le digamos luego “te envié la dirección”, de “nosotros” no pasar a hablar de “mí”.
    
* **¿Cómo habla?**

	No es lo mismo si el chatbot habla como médico/a, adolescente, vendedor/a de ropa dependiendo de la función del bot y del público del mismo. Si hablamos en lenguaje informal, no podemos luego pasar a hablar en lenguaje técnico o muy formal, si no utilizamos emojis y exclamaciones no deberíamos comenzar a utilizarlos de repente.
    
* **Tiempos verbales**

	Debemos respetar los tiempos verbales que elijamos para la redacción. Por ejemplo si un día le preguntamos ¿Fuiste al turno? no deberíamos preguntarle al día siguiente ¿Has ido al turno?
    
* **Imágenes y botones**

	Las imágenes y botones deben mantener una coherencia estética. Los botones y componentes de interfaz deben utilizar siempre las mismas palabras para nombrar las cosas (Ej Descargar vs. Download, etc.).
    
### Accesibilidad/Lenguaje claro

Es recomendable que todos los desarrollos sean accesibles. Los chats de Facebook o Messenger están programados para ser accesibles, en el caso de webchats se recomienda revisar la accesibilidad con un lector de pantalla (NVDA, JAWS).

El lenguaje claro es una metodología para escribir textos que sean accesibles principalmente a personas con discapacidad cognitiva pero también para extranjeros, personas mayores o personas con alguna dificultad para la comprensión.

Sugerimos informarse sobre la misma y testear la accesibilidad de los productos.

Aquí se puede bajar [información sobre la metodología del Lenguaje Claro](http://capacitacion.hcdn.gob.ar/wp-content/uploads/2018/08/Manual-SAIJ-de-lenguaje-claro.pdf). Incluimos también algunas recomendaciones para la redacción en “Redacción y estructuración de los mensajes”

En Argentina la [Ley de Accesibilidad 26.653](http://servicios.infoleg.gob.ar/infolegInternet/anexos/175000-179999/175694/norma.htm) hace obligatoria la accesibilidad en desarrollos digitales para organismos y empresas del Estado; concesionarias y prestadoras; instituciones y organizaciones de la sociedad civil que sean beneficiarias, reciban subsidios, donaciones, condonaciones por parte del Estado o celebren contratos con el mismo.

## Patrones de uso

### Onboarding

En un chatbot el onboarding o bienvenida, es decir el mensaje inicial que dispara el chat al comenzar la conversación, es el mensaje más importante y al cual debemos dedicar más tiempo de diseño. Este mensaje va a definir si los usuarios permanecen en el chat o “rebotan” abandonando la conversación.

Por eso es recomendable:

* Comenzar con un mensaje corto y conciso que explique claramente qué ofrece el chat (para qué se puede utilizar).

* Si contamos con el nombre o nickname del usuario, es amigable mencionarlo en el saludo. Ej. “¡Hola Mariana!”.

* Si requerimos datos del usuario para completar el onboarding:

	* Solicitarle la menor cantidad posible y solamente los que van a ser utilizados en provecho del usuario.
	* Explicarle al usuario para que se van a utilizar los datos, por ejemplo: “Ingresá tu DNI para brindarte información sobre el estado del trámite” o “Ingresá la fecha de tu viaje para confirmar disponibilidad”.
	* Si existen “disclaimers”, “términos y condiciones” o cuestiones legales que deban ser aceptadas, el onboarding puede ser una instancia en donde solicitar el consentimiento informado del usuario. Es imprescindible que el usuario sepa qué datos va a compartir y cómo se van a proteger los mismos.

### Mensajes

* Los mensajes deben estar redactados en el lenguaje más simple posible.
* Privilegiar las palabras de uso común por sobre las menos conocidas (sondear en los usuarios las palabras que usan para nombrar las cosas).
* Intentar que haya una sola idea o concepto en cada mensaje.
* Utilizar mensajes cortos.

	En lo posible, los mensajes no deben superar la extensión de lo que se puede visualizar en un celular. Si el contenido es muy largo, se puede utilizar botones conectores como “Seguir leyendo”, que además pueden usarse para medir el interés.
    
* Es recomendable que los mensajes cierren proponiendo una interacción al usuario, para que el mensaje no quede “suelto”. Si en la última respuesta ofrecemos un botón, menú o alguna interacción, favorecemos que el usuario retome la conversación si lo desea.


## Respuesta a “no entendidos”

En el uso de un chatbot va a ocurrir muchas veces que el usuario escriba cosas para las cuales el bot no tenga respuesta. Esto puede ser por 3 razones:

* No hay información cargada sobre ese tema porque no corresponde al propósito del bot.
 
* La pregunta realizada por el usuario está relacionada con el propósito del bot pero la información solicitada no está cargada. 

* La información está, pero la respuesta no se muestra porque las palabras que utilizó el usuario no están asignadas como “disparadores” a la respuesta que contiene esa información.

Para eso hay que tener en cuenta:

* Hacia el usuario brindar una respuesta automática que le haga saber que el mensaje no fue comprendido y le ofrezca algún tipo de acción posible o camino a seguir. Estas son algunas de las opciones que además se pueden combinar:

	* Decirle que el bot no ha comprendido lo que escribió.
	* Pedirle que lo escriba con otras palabras.
	* Ofrecerle un menú de opciones con botones.
	* Ofrecerle ser derivado a un operador y/o mail (en el caso de contar con equipo para eso).

* Revisar periódicamente en la plataforma de monitoreo de conversaciones los mensajes “No entendidos”, si la plataforma cuenta con esa funcionalidad. Revisando estos términos se puede mejorar muchísimo el bot:
	* En el caso en que la información exista y no se haya disparado, cargar las palabras que utilizó el usuario como “disparadores”.
	* En el caso en que la información no exista pero la consulta sea pertinente, se puede tomar nota e incorporar la información solicitada.

## Respuestas genéricas

Hay intenciones del bot que conviene tener programadas para ciertas interacciones del usuario como saludos, agradecimientos, preguntas sobre quién está manteniendo la conversación y otras interacciones esperables. Se disparan cuando en medio de una conversación el usuario escribe “gracias”, “hola”, “quién sos”, etc. En algunas plataformas de chatbot estas reglas vienen “pre configuradas” pero siempre es bueno revisarlas y adecuarlas a la propia personalidad o público del bot.

## Notificaciones/Campañas

En el caso de que se pueda tener un seguimiento del usuario (usuarios identificados). Se puede utilizar notificaciones como una forma de mantener la conversación, o brindar servicios como recordatorios, información personalizada, etc. También se pueden utilizar los mensajes “proactivos” del bot para envíos masivos y/o segmentados de anuncios, como campañas de vacunación, productos en promoción, noticias y encuestas, entre otros. Al ser mensajes que el bot envía sin que hayan sido solicitados recomendamos que:

* Ofrezcan la posibilidad de des-suscribirse para quien no quiera seguir recibiéndolas.
* Se tome en cuenta el horario en que van a llegar para que no sean una molestia.

### Componentes

* Antes de desarrollar un chatbot, es importante saber en qué dispositivos se van a conectar los usuarios. Puede ser un componente de chat en una página web, un perfil de una red social como Facebook Messenger, aplicaciones de mensajería como Whatsapp y Telegram o un sistema de envío de mensajes por SMS. Dependiendo del dispositivo o aplicación que se utilice para distribuir el chatbot, habrá más o menos elementos visuales y/o auditivos soportados.

* elemento más compatible e interoperable que puede utilizarse tanto en aplicaciones como en teléfonos e incluso compatible con sistemas de voz, es el mensaje de texto.

* Este elemento será soportado por cualquier plataforma o dispositivo.

### Mensajes de sólo texto
El texto simple es el formato de interacción básica de un chatbot y el que mejor funciona para brindar una experiencia similar a una conversación.

En el caso de trabajar para dispositivos o aplicaciones que no soporten elementos gráficos como botones o carruseles, el mensaje sólo texto se puede utilizar para todo tipo de interacción, utilizando disparadores asociados a números o letras. Por ejemplo si le preguntamos al usuario:

“¿Recibió tu hijo la vacuna del sarampión?”

Si la recibió escribe A

Si no la recibió escribe B”

En las plataformas en las cuales sí son soportados todos los elementos gráficos (Por ej Messenger) los mensajes de texto se pueden combinar con botones imágenes y carruseles.



### Pantalla de bienvenida

En los casos de chatbots que provienen de Messenger o Facebook, la pantalla de bienvenida es lo primero que el usuario ve al iniciar la conversación (antes del onboarding). Incluye el nombre, la descripción, la foto del perfil y en el caso de bots vinculados a Facebook, la foto de portada de la página asociada al bot.  Es un mensaje que el usuario ve una sola vez cuando encuentra el chatbot antes de empezar a conversación. Puede incluir un texto de saludo opcional en la pantalla que presente la finalidad del bot y si hubiese avisos legales breves, podrían ir en esta pantalla.


### Archivos multimedia

La plataforma de Messenger permite enviar activos de medios enriquecidos como mensajes independientes o adjuntos a plantillas de mensajes estructurados. Estos son los tipos de activos admitidos:

* Audio
* Videos
* Imágenes
* Archivos


### Carruseles

Los carruseles son recomendados para presentar un menú de temas e intenciones de forma ordenada y atractiva. Las plantillas también admiten botones que amplían su funcionalidad.


### “Pills” de respuestas rápidas

Las respuestas rápidas permiten presentar “menúes” de opciones en forma de “botones” o “pills”. Son útiles para generar “temas” o grupos de reglas para orientar la navegación cuando los disparadores no son del todo específicos o tienen una sola palabra. También se usan para “cerrar” mensajes con propuestas de interacción posibles.


Es importante tener en cuenta la longitud de los nombres de las pills ya que el número de caracteres suele ser limitado. Lo mismo ocurre con la cantidad de pills por menú.

### Menú persistente

El menú persistente es un elemento que queda siempre visible para el usuario. Se ve en forma de menú colapsado de 3 líneas en el extremo izquierdo de la pantalla, junto al cuadro de diálogo. Se recomienda para mostrar las acciones que tienen que estar siempre disponibles para el usuario cómo “Compartir”, “Configuración”, etc.


### APIs

Las plataformas de chatbots permiten acceder a webservices o interfaces con otros sistemas o fuentes de datos. Esto sirve para que los bots puedan interoperar con otras plataformas y hacer uso de funciones pre existentes en las mismas. 

En general, para permitir la interacción entre un bot y un web service, será necesario configurar tokens que autoricen el acceso del bot a los datos o sistemas a conectar. También deberá conocerse de antemano la URL o dirección del servicio, qué parámetros será necesario enviar al invocarlo y cuál es la estructura de datos esperable como respuesta, a fin de poder leer y extraer la información obtenida.

De esta manera, se pueden integrar servicios tales como mapas geo-referenciados según listados de coordenadas de interés para el chatbot o de obtención de información sobre una base de datos vinculada a bases de datos conectadas a la plataforma.


## Métricas, monitoreos y mejoras

### Monitoreo de conversaciones

Si la plataforma del chatbot lo permite se puede realizar un monitoreo de las conversaciones con los usuarios. El monitoreo se enfoca antes que nada en los mensajes “No entendidos” (cuando el bot reconoce que no tiene una respuesta para el mensaje) o en los “falsos positivos” (cuando el bot encuentra una respuesta pero es equivocada).

Sobre este tema hablamos en el párrafo anterior: [Respuesta a no entendidos](#respuesta-a-no-entendidos)

Otras ventajas del monitoreo de conversaciones son:

* Identificar problemáticas o inquietudes de los usuarios que no estaban previstas.
* Identificar las palabras con las cuales usuarios nombran a las cosas que estamos intentando comunicar y que a veces difieren de las que estábamos utilizando originalmente.
* Identificar puntos de abandono de la conversación

### Métricas
Para cualquier producto que se desarrolle, servicio que se brinde o política pública que se implemente, necesitamos saber si lo que implementamos está funcionando y cómo se puede mejorar.

En los chatbots las métricas son útiles para evaluar el funcionamiento, la usabilidad de la herramienta y el comportamiento de los usuarios.

Las plataformas de chabot suelen ofrecer distintas métricas pre configuradas:

* Temas más consultados
* Cantidad de usuarios
* Cantidad de usuarios que recibieron un envío masivo o lo “vieron”
* Reglas más utilizadas

No todas las mediciones para evaluar un proyecto se van a poder implementar en el chatbot, pero como la plataforma establece un vínculo directo con los usuarios ofrece muchas posibilidades.

Los datos que queramos obtener pueden implicar un desarrollo adicional. Se puede medir por ejemplo cuántas veces fueron presionados determinados botones, datos de comportamiento de los usuarios que se van guardando en forma de variables, respuesta a determinada pregunta, encuestas enviadas, etc. 

Lo ideal es definir de entrada las mediciones que vamos a realizar para aprovechar los datos que generen las conversaciones desde el principio.



