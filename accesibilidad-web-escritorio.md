# Guía de revisión de accesibilidad de sitios webs en computadoras de escritorio

El objetivo de este documento es explicar los aspectos que debe revisar un desarrollador front end o analista de accesibilidad para asegurar que un sitio web sea accesible (lo cual en parte hace que lo puedan usar personas con discapacidades visuales, mediante el uso de lectores de pantalla).

**Las formas de revisar la accesibilidad que proponemos es:**

1. Testear con herramientas automáticas
2. Navegar como una persona con discapacidad
3. Chequear visualmente y con validador de w3c

## 1. Testear con herramientas automáticas

Para una primera mirada está bueno testear con herramientas automáticas, si bien se debe complementar con revisiones manuales (los puntos 2, 3 y 4).

### Analizar con Tota11y

1. Instalar Tota11y https://khan.github.io/tota11y/
2. Se sugiere utilizar en el navegador Firefox
3. En esa página hay un botón que dice “tota11y” que hay que arrastrar a la barra de marcadores.

Luego entrando con el navegador a la página que se quiere analizar y tocando el botón de “tota11y” que está en la barra va a aparecer abajo a la izquierda un botón con un unos anteojos. Tocando el botón Tota11y va a mostrar un menú de opciones para elegir los elementos que queremos chequear.

Para cada elemento el programa va a indicar los problemas en una vista marcada en la pantalla, en rojo lo que hay que solucionar y en verde lo que es correcto.

**Este programa es útil para verificar:**

- Etiquetas de formularios
- Orden de encabezados
- Contraste

#### Etiquetas de formularios

Las etiquetas son para que el usuario con discapacidad visual “escuche” los nombres de los elementos de formulario y sepa qué datos está completando. La vista marcada mostrará si faltan etiquetas en inputs o botones, luego habrá que visualizar si están asociadas correctamente a los inputs (esto lo vemos en la parte de testeo manual).

**Los elementos que tienen que tener etiquetas de formulario son:**

- Inputs
- Checkbox
- Radiobutton
- Select
- Botones (button)
- Encabezados (h1, h2, h3, etc)

El tota11y muestra si los encabezados están ordenados correctamente:

- Los encabezados hay que usarlos para jerarquizar la información, no para asignar estilo
Debe existir un h1 que describa el propósito de la página.
- No puede haber encabezados no consecutivos (después de un h1 debería haber un h2, un h3 y no un h4 después de un h2, etc).
- Los elementos que no “encabezan” a otros elementos no deben ser etiquetados como encabezados. P. Ej.: Un número de teléfono aislado no debe ser etiquetado como un encabezado.

#### Contraste

El contraste debe tener un ratio mayor a 4.5 (esto lo verifica el Tota11y).

## 2. Navegar como una persona con discapacidad visual

Para chequear la accesibilidad de la página al menos lo que hago es navegar la página como lo hacen las personas con discapacidad visual.

- Navegando por teclado
- Escuchando la página con un lector de voz (NVDA, JAWS, Voice over)

### Pautas para la navegación por teclado

Utilizando el teclado podemos verificar que se cumpla lo siguiente:

#### Todo elemento debe ser navegable por teclado

Las personas con discapacidad visual, algunas con discapacidad motriz y muchas otras no utilizan el mouse/mousepad, utilizan teclados o tecnologías asistivas que las emulan. Si la página es navegable y operable por teclado tenemos garantizada gran parte de la accesibilidad.

Utilizando frameworks accesibles esto viene configurado por defecto, en general los problemas surgen cuando se usan elementos que no son estándar como botones o formularios diseñados ad hoc y no se chequea que se puedan accionar mediante el teclado.

La navegación por teclado se puede testear sin utilizar el NVDA para hacer una revisión previa. Para navegar con teclado las teclas más usadas:

- Flecha abajo y arriba para avanzar de arriba abajo por los textos
- Tab para avanzar entre elementos interactivos
- Shift tab para retroceder entre elementos interactivos
- Enter o barra espaciadora para accionar los formularios, desplegables y controles en general
- Teclado para ingresar texto o números en inputs

#### La secuencia de navegación debe debe ser la misma que la visual

Cuando navegamos la pantalla operando el teclado la secuencia de navegación debe ser igual a la percibida visualmente. Si hay alteraciones mínimas no sería un problema pero algunas veces la alteración del orden de los elementos tergiversa totalmente el contenido como por ejemplo en un cuadro o tabla. Muchas veces los problemas de la secuencia de navegación son ocasionados por el uso indiscriminado de la etiqueta “tabindex” en la maquetación.

#### El foco debe ser visible

Al navegar la página con teclado el foco que va cambiando de un elemento a otro tiene que ser visible, en general esto viene configurado por defecto en todos los componentes y lo que hay que hacer es no modificarlos para ocultar el foco como se hace en algunos casos por una cuestión “estética”.

#### No debe haber trampas para el foco

La trampa para el foco es un problema de accesibilidad muy raro de encontrar pero es importante evitarlo porque para el usuario puede significar tener que abandonar la página o resetear equipo. Se dice que hay una “trampa para el foco” cuando un elemento de la navegación al ser accedido por teclado atrapa el foco y no permite continuar la navegación volver atrás y bloquea la navegación.

Para detectar este error hay que navegar la página con el teclado y si se encuentra una trampa para el foco la mejor solución es reemplazar el elemento que la está causando por un elemento nativo estándar del “framework” que estamos utilizando que sea accesible de origen.

*Para navegar cómo navegan lo más similar posible a como navegan las personas con discapacidad es importante instalar un lector de pantalla y comprobar si la página se “escucha” correctamente*

### Pautas para revisar con un lector de pantalla

Primero se debe tener instalado un lector de pantalla como el NVDA (gratuito).

https://www.nvaccess.org/download/

Con el uso del lector vamos a poder chequear si la página tiene:

#### Texto alternativo (audible) para imágenes e íconos

Navegando con el NVDA nos vamos a dar cuenta si el lector nos está describiendo el contenido de una imágen o ícono.

Las imágenes tienen que tener un texto alternativo para que los lectores de pantalla puedan convertirlo en audio, el texto alternativo se coloca en el atributo alt=”texto alternativo correspondiente”.

Cuando las imágenes no son relevantes (separadores, líneas, etc) se recomienda dejar la etiqueta de alt vacía alt = “ “ ya que si no se coloca la etiqueta el lector va a leer el nombre del archivo y el directorio.

Los íconos y o svg también tienen que tener texto alternativo si no se escuchan correctamente con el lector, se puede poner con etiquetas ARIA. Nunca se debe usar imágenes para botones, menúes o elementos de interacción.

#### Gráficos interactivos, visualizaciones de datos, mapas

Si existen gráficos que no se pueden hacer accesibles porque la ubicación en pantalla es fundamental para su comprensión el gráfico debe estar acompañado por un texto o enlace a texto como alternativa accesible.

Por ej: Si la imagen muestra un mapa con geocalización de sucursales la alternativa accesible puede ser una lista de sucursales con dirección, localidad, provincia. Si la imagen muestra un gráfico con ordenadas x e y la alternativa accesible puede ser el cuadro de doble entrada que dio origen al gráfico.

#### Formularios

Las etiquetas de formularios se tienen que escuchar navegando con Tab.

Las etiquetas (“label” “legend”) de formulario tienen que ser audibles cuando el foco ingresa en ese elemento.

A veces la etiqueta es audible cuando recorremos “toda la página” navegando con las flechas pero la etiqueta también tiene que escucharse cuando navegamos con la tecla TAB y esto no pasa cuando las etiquetas no están asociadas explícitamente con los inputs.

La tecla tab es muy usada por las personas con discapacidad visual porque “acortan” camino ya que saltan de input a input o de enlace a enlace sin pasar por otros contenidos. Del mismo modo en celulares se usa un modo para recorrer solo los controles de formulario.

Para que la etiqueta sea audible con navegación por teclado (tab) o en móviles es necesario que además de estar asociada al input como “label” tenga una asociación explícita entre el input y la label que se logra con “label for” y “id”.

Si las etiquetas no se escuchan al navegar con tab (desktop) o modo controles (móvil) ese formulario no será accesible.

Los grupos de inputs deben estar asociados entre sí y tener un nombre.

Navegando con TAB en la web o en modo “Controles” los usuarios de lector de voz “caen” en los inputs de opciones sin pasar por el título (el TAB manda el foco directamente al 1er input). Si el grupo no está correctamente etiquetado la persona va a recorrer las opciones sin saber a que pertenecen.

Por ej si las opciones son:

**Cantidad de pasajes**

- 1
- 2
- 3

La persona va a escuchar **“uno, dos, tres”** y no sabrá que esta elección se refiere a **“Cantidad de pasajes”.**

Lo correcto es que la persona escuche: **“Cantidad de pasajes botón de opción 1, 2, 3”**

Si el título de la agrupación o “legend” no se escucha es un problema de accesibilidad y se soluciona etiquetando el grupo de opciones como “fieldset” desde “Cantidad de pasajes” hasta el fin de “3” y luego etiquetando “Cantidad de pasajes” con la etiqueta “legend” para darle nombre al grupo de opciones.

#### Los formularios tienen que tener devolución de errores audible

Cuando enviamos un formulario y hay un error esa devolución de errores debe ser audible.
Este es uno de los errores más bloqueantes que existen porque impiden a los usuarios con discapacidad visual avanzar.

Lo tolerado o mínimo (y lo más fácil de lograr) es que en la página de devolución de errores aparezca enfocado el primer campo que debe ser corregido y que ese campo diga en forma audible su “label”.

Por ejemplo si falta ingresar:

- DNI
- Nombre
- Apellido

La página de devolución de error debe mostrarse con el foco en el input DNI y el audio debe decir lo mismo que antes del envio “completar campo de texto DNI”. Para que esto suceda los input deben tener sus nombres (labels) asociadas correctamente con “label for” y “id”.

Lo ideal (es más difícil de lograr) es que la devolución de mensaje de error del formulario ofrezca una lista audible de todos los campos que falta completar o corregir.

En el caso de que el formulario haya sido completado con éxito el usuario debe recibir este mensaje en forma audible.

#### Cambios de pantalla anunciados en forma audible

Es muy común encontrar que los cambios o interacciones que se suceden en la pantalla después de la carga inicial sean “inaudibles” para el usuario de lector de voz.

Opciones de formulario que despliegan otras, renovación de info de tiempo o cotización, pop ups, páginas dentro de páginas,y desarrollos con javascript y sus “frameworks” no van a cambiar para la persona con discapacidad visual a menos que lo maquetemos accesible exprofeso. Este problema en general es bloqueante porque la persona se queda sin poder avanzar.

El lector carga el html inicial en un DOM accesible y no actualiza información a menos que se lo hayamos avisado previamente mediante una etiqueta (puede ser ARIA Live).

Lo recomendable es usar este tipo de interactividad contemplando la maquetación accesible y si eso no es posible evitar los elementos que cambian luego de la carga inicial del html.

Cuando el elemento está bien maquetado se comporta de un modo equivalente al que se percibe visualmente: Anuncia el cambio y permite la interacción.

#### Pop Ups, modales

Los pop ups o ventanas emergentes son parte del grupo “elementos que llegan a la pantalla luego de la carga inicial” pero tienen otras particularidades.

Para que un pop up sea accesible tiene que cumplir con las siguientes características al analizarla con el lector de pantalla + navegación con teclado:

- La aparición del pop up debe anunciarse en forma audible.
- El cierre del pop up también debe anunciarse en forma audible
- El pop up debe capturar el foco de la navegación esto quiere decir que al abrirse el pop up deberíamos poder navegar dentro del mismo y no deberíamos poder navegar fuera del mismo hasta que lo cerremos. Uno de los problemas más comunes es cuando un pop up aparece en pantalla pero el foco de la navegación se mantiene navegando “por debajo” del mismo leyendo y recorriendo los elementos de la página cómo si el pop up no existiera. Este problema puede ser bloqueante si no nos permite cerrar el pop up o si no nos permite accionar dentro del pop up.
- Los elementos dentro del pop up deben ser navegables con teclado.
- El pop up debe poder cerrarse a voluntad del usuario con la tecla “escape” que es un estándar para cierre de pop ups. Además se puede incluir un elemento para cerrarlo dentro del pop up, este tiene que anunciarse en forma audible

#### Desplegables

Para que un desplegable sea accesible debe ser navegable por teclado y en forma audible, debe:

- Permitir er desplegado y contraído utilizando el teclado.
- Anunciar su condición de desplegable en forma audible.
- Anunciar su estado en forma audible (desplegado, contraído).
- Permitir la navegación a través de sus opciones o índice mediante teclado y en forma audible
- Capturar el foco dentro del área simulada del desplegable y no debe permitir que el foco salga de esa área hasta que el desplegable sea contraído por el usuario
- Permitir ser plegado con la tecla “escape”
- Una opción de selector o desplegable no debe iniciar cambios sin aceptación del usuario. En el caso de selectores que inician cambios o llevan a diferentes secciones deben acompañarse de un botón “Ir” o similar que permita confirmar el cambio iniciado por el usuario en el selector.

#### Tablas

Si hay una tabla con datos tiene que anunciarse y leerse como tabla en forma audible.

La información debe leerse de manera que coincida con la estructura visual: la primera fila, de izquierda a derecha, luego la segunda. Si los “heads” están bien colocados los datos de las celdas van a mencionar al usuario a que columna pertenecen para una mayor comprensión.

Para que el usuario sepa que es una tabla debe tener una etiqueta "<caption>" con el título de la tabla además de las etiquetas "<table>"

Si la información o la estructura son complejas debe tener una explicación con un "<table summary=”…”>"

Cuando hacemos una tabla con información tabular no se deben utilizar celdas columnas o filas para generar “padding” o espacios. Las celdas columnas o filas deben estar ocupadas únicamente por los datos.

Cuando hay información tabular lo correcto es utilizar una tabla. Cuando no hay información tabular no se debe usar tablas para maquetar.

Si la información (que no es tabular) está maquetada con tablas y esto no se puede modificar (pasa en sitios antiguos) se sugiere hacerlas “invisibles” al lector de pantalla.

Para hacer “invisible” al lector la estructura de tablas sugiere dejar solo las etiquetas "<tr>" y "<td>" para definirlas y ocultar las demás.

#### Audios y videos

Los controles de audios o videos deben ser operables por teclado (no mouse).

Los audios deben poder ser leídos y los videos deben poder ser escuchados.

Para los audios se puede incluir una transcripción escrita. Los videos deben tener opción a subtítulos.

Los videos deben tener opción a audiodescripción, es un audio que incluye una descripción de lo que se oye en los videos además de lo que dicen los parlamentos (Ej. “ruido de puerta que se cierra”, “suena el timbre”)

#### "Panel de elementos" de NVDA

El NVDA tiene un “panel de elementos” que las personas con discapacidad utilizan bastante. Es como un índice de la página divido por tipo de elementos (Encabezados, Enlaces, Elementos de formulario, Botones, Puntos de referencia. Este panel nos puede ayudar a detectar problemas en:

- Nombre de los enlaces
- Etiquetado
- Puntos de referencia

Al panel de NVDA se accede teniendo el NVDA encendido y tocando simultáneamente las teclas “Bloq mayúscula + F7” o “Insert + F7”. El tema de las teclas es bastante difícil de configurar pero con un poco de paciencia sale.

Al abrir el panel de elementos podemos ver la lista de enlaces y de paso revisar si existen los siguientes problemas de accesibilidad.

##### Enlaces con textos específicos y se entiendan fuera del contexto visual

Por ej “VER MÁS” “HACER CLICK AQUÍ” no se entienden aisladamente. En la lista de enlaces de una página de noticias se verá:

- VER MÁS
- VER MÁS
- VER MÁS

Y el usuario no sabe a dónde lleva cada uno.

Hay varias formas de solucionar esto pero la más sencilla es llamando a los enlaces con el nombre específico ej “Ver más notas sobre contaminación”.

Los enlaces no deben ser demasiados largos (deben tener menos que una línea de texto) en lo posible.

##### Etiquetado

Lo que funciona y se ve como botón debe estar etiquetado como botón, y lo que funciona como enlace y se ve como enlace debe estar etiquetado como enlace. Todos los elementos de formulario tienen que estar etiquetados según su función. Esto va a ser más importante aún si queremos que el sitio sea accesible en mobile.

##### Puntos de referencia

Los puntos de referencia deben estar etiquetados correctamente (main, nav, aside para html5 y si no mediante etiquetas ARIA).

Los “puntos de referencia” permiten al usuario con discapacidad visual “saltar bloques”. Esto es pasar por alto los bloques repetidos como el cabezal, el menú de la izquierda para no tener que escuchar todo ese contenido de nuevo y poder pasar directo al contenido principal “main”.

## 3. Chequeos a simple vista, validador w3c

Otras cosas que tenemos que chequear y la mayoría se puede verificar a simple vista o con el validador de la W3C

### La página debe tener título

La página tiene que tener un título que describa su propósito (esto se indica con la etiqueta &lt;title&gt;) es una de los elementos más importantes porque es lo que permite a una persona con discapacidad irse de la página pronto si es una que no tiene lo que busca. El título debe ser específico. Si hay varias páginas en un sitio no deberían llamarse todas con el mismo nombre si no con el nombre específico de la página en sí, el del sitio se puede poner al final del título para reforzar pertenencia.

### Expiración de sesión

Para que un sitio sea accesible no debe haber tiempo limitado para realizar una tarea.
Si se necesita hacer esto por seguridad se debe incluir la opción de solicitar más tiempo para la operación.

### Lenguaje de la página

El lenguaje de la página tiene que estar declarado en el html.

Para que el lector pueda pronunciar las palabras correctamente el lenguaje de la página tiene que estar declarado en la etiqueta **lang=”es-AR”**, esto se puede chequear verificando el código de la página.

### Nombre, rol (función), valor

Este criterio de evaluación de accesibilidad apunta a que todos los componentes del html tienen que tener un nombre, una función y un valor declarados para el lector de pantalla. Por ejemplo:

- En un input estilo “radiobutton” el nombre sería la “label”, la función seria “botón de opción (radiobutton)” y el valor sería “marcado” o “no marcado”.
- En el caso de los iframes por ejemplo suele pasar que no se le coloca el nombre y entonces el usuario no sabe que va a ocurrir en esa sección de la página.

En general los componentes nativos de los framework estándar ya contienen estas especificaciones pero es importante verificarlo en el caso de que se desarrollen componentes de interfaz de usuario propios.

### Parsing

Para chequear que el html esté bien construido se recomienda ingresar el url en el validador de la w3c https://validator.w3.org/

Algunos errores que el validador detecta no son un problema de accesibilidad para el usuario pero está bueno solucionarlos para maximizar la compatibilidad entre dispositivos y estar en regla con la Ley de Accesibilidad que lo exige.