# Información de trámites provinciales

**Secretaría de Innovación, Ciencia y Tecnología**
- Subsecretaría de Tecnologías de la Información y las Comunicaciones  
  -   Dirección Nacional de Servicios Digitales

Versión: 0.1 


## Índice:

* [Objetivo](#objetivo)
* [Planificación](#planificación)
* [Requisitos](#requisitos)
  * [Categorías](#categorías)
* [Ejemplo](#ejemplo)
* [Versiones](#versiones)

## Objetivo: 

Dentro de las plataformas de Mi Argentina y Argentina.gob.ar tenemos el objetivo de acercarle al ciudadano los trámites y servicios que puede acceder por parte de los Estados provinciales y municipales.

Con esta finalidad generamos un estándar para compartir información básica de estos servicios y que los ciudadanos puedan accederlos cómodamente desde su perfil ciudadano, o al navegar la web oficinal del Estado Nacional.

## Requisitos

- Los archivos deben estar alojados en el sitio web oficiale de Estado local, con el nombre `tramites.json` en el directorio raíz.
  Por ejemplo: `www.provincia.gob.ar/tramites.json`
- El archivo debe estar en formato json y no debe tener errores de sintaxis. La estructura del archivo puede verse en [este ejemplo](https://github.com/argob/estandares/blob/master/recursos/tramites.json).
- La especificación geográfica tiene que basarse en la [guía de entidades interoperables](https://datosgobar.github.io/paquete-apertura-datos/).


### Categorías

Estas son las categorías definidas en el estándar para segmentar los trámites.
Solo pueden usarse las que están definidas en esta documentación y no se permitirá tener unas diferentes en el archivo json.


| Nombre                                     | Descripción                                    | Id             |
|--------------------------------------------|------------------------------------------------|----------------|
| **Ambiente, agro y alimentos**             | Sanidad animal y vegetal, químicos.            | ambiente       |
| **Beneficios sociales**                    | Familia, jubilación, discapacidad.             | beneficios     |
| **Ciencia, tecnología e innovación**       | Marcas y patentes, licencias, capacitación.    | ciencia        |
| **Comercio interior y exterior**           | Autorizaciones, licencias.                     | comercio       |
| **Comunicaciones**                         | Habilitaciones, licencias.                     | comunicaciones |
| **Cultura, educación y deporte**           | Títulos, bibliotecas y museos, becas.          | cultura        |
| **Derechos humanos, seguridad y justicia** | Resolución de conflictos, registro de bienes.  | derechos       |
| **Documentación ciudadana**                | DNI, pasaporte, antecedentes.                  | documentos     |
| **Energía**                                | Reclamos por servicios.                        | energia        |
| **Finanzas e impuestos**                   | Monotributo, declaración jurada, CUIT.         | finanzas       |
| **Salud**                                  | Obras sociales y prepagas, habilitaciones.     | salud          |
| **Sociedades, industria y negocios**       | Inscripciones, registros, autorizaciones.      | sociedad       |
| **Trabajo**                                | Seguros, aportes, formación.                   | trabajo        |
| **Transporte**                             | Particular, profesional, empresas.             | transporte     |
| **Turismo y migraciones**                  | Servicios turísticos, entrar y salir del país. | turismo        |
| **Inmuebles y vivienda**                   | Habilitaciones, Registros y proyectos.         | vivienda       |

## Ejemplo

``` javascript
{
    "metadata": {

        // Estándar de definición geográfica definidas en la guía de entidades interoperables 
        // https://datosgobar.github.io/paquete-apertura-datos/guia-interoperables/#geograficas

        "provincia_id": 6,
        "provincia_nombre": "Buenos Aires",
        "spatial": [
            "ARG",
            6
        ],
        "homepage": "https://www.gba.gob.ar",

        // Organismo editor del archivo
        "publisher": {
            "name": "Organismo provincial",
            "mbox": "email organismo provincial"
        },

        // Version, fecha de creación, fecha ultima modificacion y versión del estandar implementado.
        "version": 1.0,
        "issued": "2017-02-20",
        "modified": "2018-04-18",
        "standardVersion": 2,

        // Cantidad de trámites listados
        "count": 2,

        // Listado de categorías, debe respetar las definidas en el estándar
        "themeTaxonomy": [
            {
                "id": "turismo",
                "label": "Turismo y migraciones",
                "description": "Servicios turísticos, entrar y salir del país."
            },
            {
                "id": "transporte",
                "label": "Transporte",
                "description": "Particular, profesional, empresas."
            },
            {
                "id": "trabajo",
                "label": "Trabajo",
                "description": "Seguros, aportes, formación."
            },
            {
                "id": "sociedad",
                "label": "Sociedades, industria y negocios",
                "description": "Inscripciones, registros, autorizaciones."
            },
            {
                "id": "comunicaciones",
                "label": "Comunicaciones",
                "description": "Habilitaciones, licencias."
            },
            {
                "id": "comercio",
                "label": "Comercio interior y exterior",
                "description": "Autorizaciones, licencias."
            },
            {
                "id": "ciencia",
                "label": "Ciencia, tecnología e innovación",
                "description": "Marcas y patentes, licencias, capacitación."
            },
            {
                "id": "social",
                "label": "Beneficios sociales",
                "description": "Familia, jubilación, discapacidad."
            },
            {
                "id": "cultura",
                "label": "Cultura, educación y deporte",
                "description": "Títulos, bibliotecas y museos, becas."
            },
            {
                "id": "derechos",
                "label": "Derechos humanos, seguridad y justicia",
                "description": "Resolución de conflictos, registro de bienes."
            },
            {
                "id": "salud",
                "label": "Salud",
                "description": "Obras sociales y prepagas, habilitaciones."
            },
            {
                "id": "finanzas",
                "label": "Finanzas e impuestos",
                "description": "Monotributo, declaración jurada, CUIT."
            },
            {
                "id": "energia",
                "label": "Energía",
                "description": "Reclamos por servicios."
            },
            {
                "id": "documentos",
                "label": "Documentación ciudadana",
                "description": "DNI, pasaporte, antecedentes."
            },
            {
                "id": "ambiente",
                "label": "Ambiente, agro y alimentos",
                "description": "Sanidad animal y vegetal, químicos."
            },
            {
                "id": "vivienda",
                "label": "Inmuebles y vivienda",
                "description": "Habilitaciones, Registros y proyectos."
            }
        ]
    },
    "services": [
        {
            // Organismo editor de este servicio
            "publisher": {
                "name": "Registro civil",
                "mbox": "email organismo"
            },

            // Título y descripción del servicio
            "title": "Partidas de nacimiento",
            "description": "Podés solicitar cualquier partida de la provincia de Buenos Aires de forma online.",

            // Urls de referencia del trámite para la guía, turnos y trámite online.
            "guide": "https://www.gba.gob.ar/registrodelaspersonas/solicitud_de_partidas",
            "appointment": "https://www.gba.gob.ar/registrodelaspersonas/solicitud_de_partidas",
            "online": "https://www.gba.gob.ar/registrodelaspersonas/solicitud_de_partidas",

            // ID de la lista de taxonomias que se definio arriba
            "theme": "documentos"
        },
        {
            "publisher": {
                "name": "Registro civil",
                "mbox": "email organismo"
            },
            "title": "Partidas de nacimiento",
            "description": "Podés solicitar cualquier partida de la provincia de Buenos Aires de forma online.",
            "guide": "https://www.gba.gob.ar/registrodelaspersonas/solicitud_de_partidas",
            "appointment": "https://www.gba.gob.ar/registrodelaspersonas/solicitud_de_partidas",
            "online": "https://www.gba.gob.ar/registrodelaspersonas/solicitud_de_partidas",
            "theme": "documentos"
        }
    ]
}
```

## Versiones

- [[26/07/2018](https://github.com/argob/estandares/blob/7870f16f9664e4622899e8cfb6f1437db1710888/informacion-de-tramites.md)] v1: Primera versión
- [11/12/2018] v2: Se agregó la categoría *Inmuebles y vivienda* y el metadato **standardVersion** que especifica la versión del estándar utilizada.
