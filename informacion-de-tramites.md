# Información de trámites provinciales

**Ministerio de Modernización**

Dirección Nacional de Servicios Digitales

Versión: 0.1 


## Índice:

* [Objetivo](#objetivo)
* [Planificación](#planificación)
* [Requisitos](#requisitos)
  * [Categorías](#categorías)
* [Ejemplo](#ejemplo)

## Objetivo: 

Dentro de las plataformas de Mi Argentina y Argentina.gob.ar tenemos el objetivo de acercarle al ciudadano los trámites y servicios que puede acceder por parte de los Estados provinciales y municipales.

Con esta finalidad generamos un estándar para compartir información básica de estos servicios y que los ciudadanos puedan accederlos cómodamente desde su perfil ciudadano, o al navegar la web oficinal del Estado Nacional.

## Planificación

- [x] Definir el estándar de datos a compartir
- [ ] Implementar el listado de los trámites provinciales en Argentina.gob.ar
- [ ] Mostrar los trámites de la provincia del usuario en Mi Argentina

## Requisitos

- Los archivos deben estar alojados en el sitio web oficiale de Estado local, con el nombre `tramites.json` en el directorio raíz.
  Por ejemplo: `www.provincia.gob.ar/tramites.json`
- El archivo debe estar en formato json y no debe tener errores de sintaxis. La etructura del archivo puede verse en [este ejemplo](https://github.com/argob/estandares/blob/master/recursos/tramites.json).
- La especificación geográfica tiene que basarse en la [guía de entidades interoperables](http://paquete-apertura-datos.readthedocs.io/es/stable/guia_interoperables.html#geograficas).


### Categorías

- Ambiente, agro y alimentos 
- Beneficios sociales 
- Ciencia, tecnología e innovación 
- Comercio interior y exterior 
- Comunicaciones 
- Cultura, educación y deporte 
- Derechos humanos, seguridad y justicia 
- Documentación ciudadana 
- Finanzas e impuestos 
- Salud 
- Sociedades, industria y negocios 
- Trabajo 
- Transporte 
- Turismo y migraciones

## Ejemplo

``` javascript
{
    "metadata": {

        // Estándar de especificación geográfica definidas en la guía de entidades interoperables
        "provincia_id": 06,
        "provincia_nombre": "Buenos Aires",
        "spatial": [
            "ARG",
            06 
        ],
        
        // Accesos web generales
        "homepage": "https://www.gba.gob.ar",
        "tax": "http://www.arba.gov.ar/",
        "tourism": "http://www.buenosaires.tur.ar/",

        // Organismo editor del archivo
        "publisher": {
            "name": "Organismo provincial",
            "mbox": "email organismo provincial"
        },

        // Version, fecha de creación y fecha ultima modificacion
        "version": 1.0,
        "issued": "2017-02-20",
        "modified": "2018-04-18",

        // Cantidad de trámites listados
        "count": 2,

        // Listado de categorías, debe respetar las definidas en el estándar
        "themeTaxonomy": [
            {
                "id": "doc",
                "label": "Documentación ciudadana",
                "description": "Documentos generados por el Estados para los ciudadanos."
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
            "theme": "doc"
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
            "theme": "doc"
        }
    ]
}
```
