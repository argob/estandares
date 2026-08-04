# Estándares de APIs

**Secretaría de Innovación, Ciencia y Tecnología**
- Subsecretaría de Tecnologías de la Información y las Comunicaciones
  -   Dirección Nacional de Servicios Digitales

Versión: 1.1

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

* Poner el número de versión mayor de la API en la URL (ej. `/v1/`, `/v2/`). No acepte ninguna petición que no especifique el número de versión mayor ([más info](#versiones)).

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

* http://www.ejemplo.gob/api/v1/articulos?year=2016&sort=desc

### **Ejemplo NO válido**

* http://www.ejemplo.gob/api/v1/articulos?anio=2016&orden=desc

## RESTful URLs

### Lineamientos generales

* Una URL identifica un recurso.

* Las URLs DEBEN incluir sustantivos, no verbos.

* Use sustantivos en plural solamente para consistencia (no sustantivos en singular).

* Use los verbos HTTP apropiados (GET, POST, PUT, PATCH, DELETE) para operar en las colecciones y elementos.

* No necesita ir más allá de resource/identifier/resource

* Ponga el número de versión mayor en la URL, por ejemplo: http://ejemplo.gob.ar/v1/path/to/resource

* Especificar campos opcionales como una lista separada por coma.

* Para indicar el formato de respuesta utilizar el campo content-type del header siendo por defecto el formato JSON. Por ejemplo:
XML: Content-Type: application/xml
JSON: Content-Type: application/json; charset=utf-8

* El formato DEBE ser: api/v2/resource/{id}

### Ejemplos válidos de URLs

* Lista de artículos:

  * GET http://www.ejemplo.gob/api/v1/articulos

* Filtrando con query string:

  * GET http://www.ejemplo.gob/api/v1/articulos?year=2016&sort=desc

* Un artículo en formato JSON:

  * GET http://www.ejemplo.gob/api/v1/articulos/1234

* Todos los comentarios de un artículo en particular:

  * GET http://www.ejemplo.gob/api/v1/articulos/1234/comentarios

* Especificar campos opcionales en una lista separada por coma:

  * GET http://www.ejemplo.gob/api/v1/articulos/1234?fields=title,body

* Agregar un comentario a un artículo específico:

  * POST http://ejemplo.gob/api/v1/articulos/1234/comentarios

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

* Usa camelCase para las claves (por ejemplo, userId, developerMessage). Diferentes lenguajes usan diferentes convenciones. JSON usa camelCase.

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

Las respuestas de errores DEBEN utilizar los códigos de estado HTTP apropiados y devolver un cuerpo JSON estructurado con información clara tanto para el desarrollador como para el usuario final.

### Códigos de estado HTTP recomendados

Utilice los códigos estándar según corresponda a la situación:

#### Éxito (2xx)
* **200 OK**: La solicitud tuvo éxito.
* **201 Created**: El recurso se creó exitosamente (respuesta a POST).
* **204 No Content**: La solicitud se procesó con éxito pero no devuelve contenido (respuesta común en DELETE o PUT/PATCH sin retorno).

#### Error del cliente (4xx)
* **400 Bad Request**: La solicitud es inválida o los parámetros son incorrectos.
* **401 Unauthorized**: La solicitud requiere autenticación previa o las credenciales no son válidas.
* **403 Forbidden**: El cliente no tiene permisos suficientes para acceder al recurso solicitado.
* **404 Not Found**: El recurso solicitado no existe.
* **409 Conflict**: La solicitud entra en conflicto con el estado actual del recurso.
* **422 Unprocessable Entity**: La sintaxis de la solicitud es correcta pero contiene errores semánticos o de validación de datos.
* **429 Too Many Requests**: Se excedió el límite de peticiones permitido (*rate limiting*).

#### Error del servidor (5xx)
* **500 Internal Server Error**: Error no esperado en el servidor.
* **502 Bad Gateway**: Error en la comunicación con un servicio upstream o backend.
* **503 Service Unavailable**: El servicio no está disponible temporalmente (ej. en mantenimiento).

> [!CAUTION]
> **Seguridad en respuestas de error:** Por razones de seguridad, las respuestas de error en producción **NUNCA DEBEN exponer trazas de código (*stack traces*)**, consultas a bases de datos o detalles internos de la infraestructura backend.

### Estructura de Respuesta de Error

    {
        "status" : 400,
        "developerMessage" : "Detallar una descripción clara del problema. Proveer a los desarrolladores sugerencias de cómo resolver sus problemas.",
        "userMessage" : "Este es el mensaje para el usuario final.",
        "errorCode" : "444444",
        "moreInfo" : "http://www.ejemplo.gob.ar/developer/path/to/help/for/444444"
    }

## Usar UTF-8

Usar [UTF-8](http://utf8everywhere.org/)

Esperar caracteres acentuados o comillas en la salida de la API, aún cuando no se espere.

Una API debe informar a los clientes de esperar UTF-8 mediante la inclusión de una notación de caracteres en la cabecera Content-Type para las respuestas.

Una API que retorna JSON DEBE usar:

* Content-Type: application/json; charset=utf-8

## Versiones

* Toda API DEBE definir una estrategia de versionado clara para garantizar la estabilidad de los consumidores.

* **Versionado SemVer en Documentación**: Siga el esquema de Versionado Semántico (`vX.Y.Z`) para la gestión interna del código y el contrato expuesto en la documentación OpenAPI/Swagger o cabeceras HTTP (`X-API-Version`):
  * **MAJOR (X)**: Cambios no retrocompatibles en la API.
  * **MINOR (Y)**: Nueva funcionalidad retrocompatible.
  * **PATCH (Z)**: Corrección de errores retrocompatible.

* **Versión Mayor en la Ruta URL**: En la ruta de la URL de producción se DEBE incluir únicamente la versión mayor (ejemplo: `/v1/`, `/v2/`). Esto evita romper las URLs de integración ante parches o mejoras menores.

* Ejemplos de URLs de API:
  * **Válido**: `http://ejemplo.gob.ar/api/v1/articulos`, `http://ejemplo.gob.ar/api/v2/articulos`
  * **No válido** (no incluir versión minor/patch en la ruta URL): `http://ejemplo.gob.ar/api/v1.0.0/articulos`

* **Soporte de Versiones**: Se debe brindar soporte al menos a la versión mayor anterior previa a su depreciación.


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

Ejemplo: http://ejemplo.gob/api/v1/articulos

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

Ejemplo: http://ejemplo.gob/api/v1/articulos/[id]

Respuesta:

    {
        "userId": 1,
        "id": 1,
        "title": "sunt aut facere repellat provident occaecati excepturi optio",
        "body": "quia et suscipit suscipit recusandae consequuntur expedita."
    }

### POST /articulos/[id]/comentarios

Ejemplo: Crear – POST http://ejemplo.gob/api/v1/articulos/[id]/comentarios

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

## Autenticación y Claves API

Es fundamental que las APIs puedan identificar y autenticar a las aplicaciones y usuarios que acceden a los recursos.

> [!WARNING]
> **Prohibición de Secretos en URL**: Queda estrictamente prohibido transmitir contraseñas, *API keys*, secretos o tokens de acceso a través de la URL o parámetros *query string* (ejemplo prohibido: `?key=YOUR_API_KEY`), ya que quedan expuestos en registros de proxy, servidores y navegadores.

### Mecanismos de Autenticación Permitidos

Las claves o tokens DEBEN transmitirse únicamente a través de cabeceras HTTP seguras:

1. **Cabecera Authorization (Recomendado)**:
   * Tokens Bearer (OAuth 2.0 / JWT): `Authorization: Bearer <token>`
   * Claves API en cabecera estándar: `Authorization: Api-Key <key>`
2. **Cabeceras Personalizadas Seguras**:
   * `X-API-Key: <key>`

### Niveles de Seguridad según la Sensibilidad de la API

* **Bajo Riesgo / Datos Abiertos Públicos (Nivel 1)**: Uso opcional de API Keys en cabecera HTTP para identificación y control de cuotas (*rate limiting*).
* **Medio/Alto Riesgo o Datos Sensibles/Registrales (Niveles 2 y 3)**: Requiere autenticación obligatoria mediante OAuth 2.0 / OpenID Connect, mTLS (TLS Mutuo) y/o restricción por lista de IPs autorizadas.

### Almacenamiento Seguro de Tokens

Un token **NUNCA DEBE guardarse en texto plano** en la base de datos como fuente de verdad.
* **Hashing Obligatorio (SHA-256)**: Se debe almacenar únicamente el hash **SHA-256** indexado del token (`token_hash`).
* **Comparación en Tiempo Constante**: Para prevenir ataques de sincronización (*timing attacks*), la verificación del hash en el servidor DEBE realizarse mediante funciones de comparación de tiempo constante (`hash_equals`).
* **Visualización Única**: El token en claro se DEBE mostrar **una sola vez**, al momento de su generación.

### Entropía y Prefijos para Secret-Scanning

* **Generación Segura**: Los tokens DEBEN generarse utilizando generadores de números aleatorios criptográficamente seguros (CSPRNG) con al menos **256 bits de entropía** (mínimo 43 caracteres aleatorios base62).
* **Prefijos de Sistema**: El token DEBE incluir un **prefijo público por sistema** (ejemplo: `mun_` para sistema Mundial, `arg_` para Argentina.gob.ar). Esto permite activar herramientas de escaneo automático de secretos (*secret-scanning*) en repositorios Git y pipelines de CI/CD para revocar tokens expuestos accidentalmente.

### Prevención de Enumeración de Credenciales

Las respuestas `401 Unauthorized` DEBEN ser genéricas y no deben especificar si el problema fue "token inexistente", "token vencido" o "cliente inactivo", evitando que atacantes enumeren identificadores válidos.

## Permisos Granulares (Abilities / Scopes)

Para garantizar el principio de mínimo privilegio en APIs autenticadas:

* **Formato Estándar**: Los permisos DEBEN definirse con la sintaxis **`recurso:accion`** en minúsculas (ejemplos: `articulos:read`, `tramites:write`, `usuarios:delete`).
* **Acciones Estándar**: Las acciones permitidas son: `read`, `write`, `delete`, `admin`.
* **Regla por Endpoint**: Cada endpoint DEBE requerir **exactamente una *ability***.
* **Respuesta 403 con Detalle de Permiso**: Si un token no posee la *ability* requerida para el endpoint, la API DEBE responder **HTTP 403 Forbidden** e incluir en el JSON de error el permiso faltante:

```json
{
    "message": "El token no posee la habilidad requerida para realizar esta acción",
    "required": "articulos:write"
}
```

## Identificación del Cliente (Cabecera X-Client-Agent)

Para evitar la falta de información de los `User-Agent` genéricos de clientes HTTP en aplicaciones móviles o de escritorio, los consumidores DEBERÍAN enviar la cabecera personalizada **`X-Client-Agent`** con el siguiente formato:

```http
X-Client-Agent: <NombreApp>/<version> <SO>/<versionSO> <dispositivo>
```
*Ejemplo:* `MiArgentina/2.4.1 iOS/17.5 iPhone14,3`

Esto permite a los sistemas receptores clasificar el tráfico por plataforma (`ios`, `android`, `web`, `desktop`, `bot`) y versión en sus registros de auditoría.

## Trazabilidad y Logging de Llamadas

* **Logging Pre-Autenticación**: El registro de auditoría de llamadas (*api_call_logs*) DEBE capturar **toda** petición entrante **antes** de la evaluación del middleware de autenticación, asegurando que las llamadas rechazadas (401, 403, 429) también queden registradas.
* **Minimización de Datos y Secretos**: **NUNCA** se deben guardar en los registros de auditoría el token, la cabecera `Authorization` completa ni cuerpos JSON con datos personales sensibles o contraseñas.
* **Inmutabilidad y Retención**: Los registros de llamadas DEBEN ser inmutables (sin modificación posterior) y DEBEN contar con un proceso de retención automatizado (diario) con un plazo recomendado de **90 días**, luego del cual los registros antiguos se depuran.

## CORS (Cross-Origin Resource Sharing)

Para permitir el consumo de APIs desde aplicaciones web en el navegador, se deben definir políticas CORS acordes a la sensibilidad de la API.

### Políticas CORS por Nivel de Seguridad

1. **APIs Públicas de Datos Abiertos (Nivel 1)**:
   Para APIs de consulta pública no autenticadas (ej. catálogos públicos, datos abiertos), se permite y recomienda habilitar origen universal:
   ```http
   Access-Control-Allow-Origin: *
   ```

2. **APIs con Datos Personales, Registrales o Sensibles (Niveles 2 y 3)**:
   Queda estrictamente prohibido utilizar `Access-Control-Allow-Origin: *`. Se debe:
   * Restringir el origen mediante una lista blanca (*whitelist*) explícita de dominios autorizados de la APN (ej. `Access-Control-Allow-Origin: https://tramites.gob.ar`).
   * Para integraciones exclusivamente servidor a servidor (*backend-to-backend*), se deben deshabilitar las cabeceras CORS para evitar consumo directo desde navegadores cliente.

Para más detalles de configuración, consultar la [especificación de W3C](https://www.w3.org/TR/cors/) o la [guía de Mozilla sobre CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS).

## Documentación

La API debe tener su documentación detallada y con ejemplos.

Estas son algunas de las herramientas que recomendamos usar:

* [MkDocs](http://www.mkdocs.org/)

* [Aglio](https://github.com/danielgtaylor/aglio)

## Referencias

* [White House Web API Standards](https://github.com/WhiteHouse/api-standards)
* [18F API Standards](https://github.com/18F/api-standards)
* [Best Practices for Designing a Pragmatic RESTful API](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)

