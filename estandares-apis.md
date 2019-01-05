# Estándares de APIs

**Ministerio de Modernización**

Dirección Nacional de Servicios Digitales

Versión: 1.0

## Índice

* [Objetivo](#objetivo)
* [Requisitos](#requisitos)
* [Lineamientos](#lineamientos)
* [Idioma](#idioma)
* [RESTful URLs](#restful-urls)
* [Verbos HTTP](#verbos-http)
* [Soporte JSON](#soporte-json)
* [Respuestas](#respuestas)
* [Formato de fecha](#formato-de-fecha)
* [Manejo de errores](#manejo-de-errores)
* [Usar UTF-8](#usar-utf-8)
* [Versiones](#versiones)
* [Límite de registros](#limite-de-registros)
* [Ejemplos de Peticiones y Respuestas](#ejemplos-de-peticiones-y-respuestas)
* [Datos de prueba](#datos-de-prueba)
* [Seguridad](#seguridad)
* [Siempre usar HTTPS](#siempre-usar-https)
* [Claves API](#claves-api)
* [CORS](#cors)
* [Documentación](#documentacion)
* [Referencias](#referencias)

## Objetivo

El presente documento tiene como objetivo definir las pautas elementales a ser consideradas al momento de diseñar, desarrollar e implementar toda APIs ya sea realizado por empleados del Estado o personal tercerizado, con el fin de ser utilizados por ciudadanos.

Con los siguientes estándares, se busca homogeneizar la experiencia entre los diversos activos del estado, para facilitar la comprensión y utilización, primando la Usabilidad, Accesibilidad y Experiencia.

## Requisitos

Las APIs deben cumplir con los estándares establecidos en este documento.

**¿Por qué?**

  * Calidad

  * Productividad

  * Homogeneización

## Lineamientos

Estos lineamientos tienen como objetivo apoyar una verdadera API RESTful. Excepciones a tener en cuenta:

* Poner el número de versión de la API en la URL. No acepte ninguna petición que no especifique el número de versión ([más info](#versiones)).

* No traducir al español lo que DEBE estar en inglés.

* Armar una documentación detallada como por ejemplo: [https://github.com/18F/api-standards](https://github.com/18F/api-standards/)

* Para el armado de la misma se recomienda utilizar herramientas como:

  * [Swagger](https://swagger.io/)
  * [Raml](https://raml.org/)
  * [MkDocs](http://www.mkdocs.org/)
  * [Aglio](https://github.com/danielgtaylor/aglio)

## Idioma

De ninguna forma se debe traducir lo que DEBE estar en inglés. A continuación se detallan algunos ejemplos:

### **Ejemplo válido**

* http://www.ejemplo.gob/api/v1.0/articulos?year=2016&sort=desc

### **Ejemplo NO válido**

* http://www.ejemplo.gob/api/v1.0/articulos?anio=2016&orden=desc

## RESTful URLs

### Lineamientos generales

* Una URL identifica un recurso.

* Las URLs DEBEN incluir sustantivos, no verbos.

* Use sustantivos en plural solamente para consistencia (no sustantivos en singular).

* Use los verbos HTTP apropiados (GET, POST, PUT, PATCH, DELETE) para operar en las colecciones y elementos.

* No necesita ir más allá de resource/identifier/resource

* Ponga el número de versión en la URL, por ejemplo: http://ejemplo.gob.ar/v1.0/path/to/resource

* Especificar campos opcionales como una lista separada por coma.

* Para indicar el formato de respuesta utilizar el campo content-type del header siendo por defecto el formato JSON. Por ejemplo:
XML: Content-Type: application/xml
JSON: Content-Type: application/json; charset=utf-8

* El formato DEBE ser: api/v2.0/resource/{id}

### Ejemplos válidos de URLs

* Lista de artículos:

  * GET http://www.ejemplo.gob/api/v1.0/articulos

* Filtrando con query string:

  * GET http://www.ejemplo.gob/api/v1.0/articulos?year=2016&sort=desc

* Un artículo en formato JSON:

  * GET http://www.ejemplo.gob/api/v1.0/articulos/1234

* Todos los comentarios de un artículo en particular:

  * GET http://www.ejemplo.gob/api/v1.0/articulos/1234/comentarios

* Especificar campos opcionales en una lista separada por coma:

  * GET http://www.ejemplo.gob/api/v1.0/articulos/1234?fields=title,body

* Agregar un comentario a un artículo específico:

  * POST http://ejemplo.gob/api/v1.0/articulos/1234/comentarios

### Ejemplos NO válidos de URLs

* Sustantivos singulares:

  * http://www.ejemplo.gob/articulo

  * http://www.ejemplo.gob/articulo/1234

* Verbo en la URL:

  * http://www.ejemplo.gob/articulo/1234/create

* Filtro fuera del *query string*

  * http://www.ejemplo.gob/articulos/2016/desc

## Verbos HTTP

Los verbos HTTP, o métodos, se deben utilizar en el cumplimiento de sus definiciones de la norma 1.1 / HTTP. Acá un ejemplo de cómo deben ser los verbos HTTP para crear, leer, actualizar y eliminar las operaciones en un contexto particular:

<table>
  <tr>
    <td>Método HTTP</td>
    <td>POST</td>
    <td>GET</td>
    <td>PUT/PATCH</td>
    <td>DELETE</td>
  </tr>
  <tr>
    <td>Operación</td>
    <td>CREATE</td>
    <td>READ</td>
    <td>UPDATE</td>
    <td>DELETE</td>
  </tr>
  <tr>
    <td>/articulos</td>
    <td>Crea nuevo artículo</td>
    <td>Lista de artículos</td>
    <td>Error</td>
    <td>Elimina todos los artículos</td>
  </tr>
  <tr>
    <td>/articulos/1234</td>
    <td>Error</td>
    <td>Muestra el artículo 1234</td>
    <td>Si existe, actualiza el artículo; sino, devuelve error.</td>
    <td>Borra 1234</td>
  </tr>
</table>


## Soporte JSON

* Las respuestas DEBEN ser un objeto JSON (no un array). Usar un array para retornar resultados limita la capacidad de incluir metadata sobre resultados, y limita la capacidad de las API’s para agregar *top-level keys* en el futuro.

* No usar claves impredecibles. Realizar el *parsing* de una respuesta JSON donde las claves son impredecibles es difícil y genera malestar a los clientes.

* Usa guión_bajo para las claves. Diferentes lenguajes usan diferentes convenciones. JSON usa guión_bajo, no camelCase.

Más info en [json.org](http://www.json.org/json-es.html)

## Respuestas

* No valores en claves.

* La metadata solamente debe contener propiedades directas a la respuesta, no propiedades relacionadas a la información de la respuesta.

### Ejemplo válido

No valores en claves:

    "tags": [
      {"id": "125", "name": "Ciudadano"},
      {"id": "834", "name": "Servicios"}
    ],

### Ejemplo NO válido

Valores en claves:

    "tags": [
      {"125": "Ciudadano"},
      {"834": "Servicios"}
    ],

## Formato de fecha

Usar ISO 8601, en UTC.

* Para solo fechas, el formato debe ser 2016-01-27.

* Para fechas completas, el formato debe ser 2016-01-27T10:00:00Z.

  * 2016-01-27T10:00:00Z

    * año, mes, día

    * hora, minutos, segundos

    * UTC

Más info en [The 5 laws of API dates and times](http://apiux.com/2013/03/20/5-laws-api-dates-and-times/)

## Manejo de errores

Las respuestas de errores DEBEN incluir los códigos de estados HTTP, mensaje para el desarrollador, mensaje para el usuario final, código de error interno, enlaces con más información para los desarrolladores. Por ejemplo:

    {
        "status" : 400,
        "developerMessage" : "Detallar una descripción clara del problema. Proveer a los desarrolladores sugerencias de cómo resolver sus problemas.",
        "userMessage" : "Este es el mensaje para el usuario final.",
        "errorCode" : "444444",
        "moreInfo" : "http://www.ejemplo.gob.ar/developer/path/to/help/for/444444, http://drupal.org/node/444444",
    }

Use estos 3 simples códigos de respuesta indicando (1) éxito, (2) fallo debido a un problema del cliente, (3) fallo debido a un problema del servidor:

1. 200 - OK

2. 400 - Bad Request

3. 500 - Internal Server Error

## Usar UTF-8

Usar [UTF-8](http://utf8everywhere.org/)

Esperar caracteres acentuados o comillas en la salida de la API, aún cuando no se espere.

Una API debe informar a los clientes de esperar UTF-8 mediante la inclusión de una notación de caracteres en la cabecera Content-Type para las respuestas.

Una API que retorna JSON DEBE usar:

* Content-Type: application/json; charset=utf-8

## Versiones

* Nunca libere la versión de una API sin su número de versión.

* Los números de version deben abarcar dos niveles de versión: x.x

* Las versiones DEBEN ser enteros, no decimales, con el prefijo ‘v’.

* Dar soporte al menos una versión anterior a la actual.

* Ejemplos:
Válido: v1.0, v2.1, v3.5
No válido: v-1.1, v1.2.5, 1.3.3


## Límite de registros

* Si el límite no está especificado, retornar resultados con un valor por defecto.

* Para obtener registros de 51 a 75, hacer los siguiente:

  * [http://ejemplo.gob/articulos?limit=25&offset=50](http://ejemplo.gob/articulos?limit=25&offset=50)

  * offset=50 significa, ‘evitar los primeros 50 registros’

  * limit=25 significa, ‘retornar un máximo de 25 registros’

La información sobre los límites de registros y totales disponibles DEBEN ser incluidos en la respuesta. Por ejemplo:

    {
        "metadata": {
            "resultset": {
                "count": 227,
                "offset": 25,
                "limit": 25
            }
        },
        "results": []
    }

## Ejemplos de Peticiones y Respuestas

* [GET /articulos](#get-articulos)

* [GET /articulos/[id]](#get-articulosid)

* [POST /articulos/[id]/comentarios](#post-articulosidcomentarios)

### GET /articulos

Ejemplo: http://ejemplo.gob/api/v1.0/articulos

Respuesta:

    {
        "metadata": {
            "resultset": {
                "count": 123,
                "offset": 0,
                "limit": 10
            }
        },
        "results": [
            {
                "userId": 1,
                "id": 1,
                "title": "sunt aut facere repellat provident occaecati",
                "body": "quia et suscipit suscipit recusandae consequuntur expedita."
            },
            {
                "userId": 2,
                "id": 2,
                "title": "qui est esse",
                "body": "est rerum tempore vitae sequi sint nihil reprehenderit dolor."
            }
        ]
    }

### GET /articulos/[id]

Ejemplo: http://ejemplo.gob/api/v1.0/articulos/[id]

Respuesta:

    {
        "userId": 1,
        "id": 1,
        "title": "sunt aut facere repellat provident occaecati excepturi optio",
        "body": "quia et suscipit suscipit recusandae consequuntur expedita."
    }

### POST /articulos/[id]/comentarios

Ejemplo: Crear – POST http://ejemplo.gob/api/v1.0/articulos/[id]/comentarios

Cuerpo de la solicitud:

    {
        "postId": 1,
        "id": 1,
        "name": "id labore ex et quam laborum",
        "email": "pedro@ejemplo.com",
        "body": "laudantium enim quasi est quidem magnam voluptate ipsam eos."
    }

## Datos de prueba

Cada recurso DEBE aceptar un parámetro 'mock' en el servidor de prueba. Pasando este parámetro debe devolver una respuesta de datos simulada (sin pasar por el backend).

La implementación de esta función en la primer etapa del desarrollo asegura que la API exhibirá un comportamiento coherente.

Nota: Si el parámetro ‘mock’ está incluido en una solicitud para el entorno de producción, debe mostrar un error.

## Seguridad

### Siempre usar HTTPS

Cualquier API que se cree DEBE usar *[HTTPS encryption](https://en.wikipedia.org/wiki/HTTPS)* (TLS/SSL). HTTPS provee:

* **Seguridad**. El contenido de las peticiones están encriptadas a través de Internet.

* **Autenticidad**. Una garantía más fuerte de que un cliente se comunica con el API real.

* **Privacidad**. Privacidad mejorada para las aplicaciones y usuarios que usan la API. Las cabeceras HTTP y los parámetros *query string* (entre otras cosas) serán encriptadas.

* **Compatibilidad**. Más amplia compatibilidad del lado del cliente. Para solicitudes CORS a la API para trabajar en los sitios web HTTPS - para no ser bloqueado en forma de contenido mixto - esas peticiones deben ser a través de HTTPS.

HTTPS DEBE estar configurado aplicando las mejores prácticas, incluyendo cifrado que soporte *[forward secrecy](https://en.wikipedia.org/wiki/Forward_secrecy)* y Seguridad de transporte HTTP estricta ([HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)).

Para APIs existentes que corren sobre HTTP, el primer paso es agregar soporte HTTPS y actualizar la documentación aclarando que es la configuración por defecto, usarlo en los ejemplos, etc.

Luego, evaluar la posibilidad de deshabilitar o redireccionar a peticiones HTTP.

## Claves API

Es importante que las APIs tengan la forma de poder identificar qué aplicación quiere acceder a los recursos. Para esto se utiliza una clave que va junto con el *request*.

Ejemplo API’s de Google:

https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY

### ¿Por qué es útil?

* Previene peticiones de usuarios anónimos.

* Previene que datos sensibles sean expuestos.

* Se puede aplicar *rate limiting *dependiendo el cliente.

## CORS

Para que los clientes puedan usar una API desde el front de una aplicación, la API DEBE tener [habilitado CORS](http://enable-cors.org/).

Para el más simple y común caso de uso, donde toda la API entera deba ser accesible desde el navegador, habilitar CORS es tan simple como incluir esta cabecera HTTP en todas las respuestas:

    Access-Control-Allow-Origin: *

Esto tiene soporte por todos los [navegadores modernos](http://enable-cors.org/client.html) y simplemente funciona en todos los clientes JavaScript, como jQuery.

Para una configuración más avanzada, ver la [especificación de W3C](https://www.w3.org/TR/cors/) o la [guía de Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS).

## Documentación

La API debe tener su documentación detallada y con ejemplos.

Estas son algunas de las herramientas que recomendamos usar:

* [MkDocs](http://www.mkdocs.org/)

* [Aglio](https://github.com/danielgtaylor/aglio)

## Referencias

* [White House Web API Standards](https://github.com/WhiteHouse/api-standards)
* [18F API Standards](https://github.com/18F/api-standards)
* [Best Practices for Designing a Pragmatic RESTful API](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)
