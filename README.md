# geocatalunya

L'objectiu d'aquest repositori és proporcionar un fitxer [JSON](https://ca.wikipedia.org/wiki/JSON) que permeti de manera senzilla accedir a la informació dels municipis i comarques de Catalunya per al seu ús en qualsevol mena d'aplicatiu que pugui emprar fitxers JSON com a font de dades.

## Estructura

S'inclou per a cada comarca un objecte amb el nom i el [codi](https://www.idescat.cat/codis/?id=50&n=10&lang=ca) establert per l'Institut d'Estadística de Catalunya, seguit d'un *array* amb tots els municipis que en formen part, incloent el nom oficial del municipi i així com, de nou, el seu [codi](https://www.idescat.cat/codis/?id=50&n=9) proporcionat per l'IDESCAT.

A tall d'exemple:

```
{
    "Vallès Oriental (41)": [
        {
        "city_name": "Granollers",
        "city_code": 80961
        }
    ]
}
```
## Recomanacions d'ús

Donat que s'han incorporat els codis de municipi i de comarca, es recomana el seu ús en cas que s'hagin de desar en bases de dades, de tal manera que si es produeix una actualització del nom de l'entitat aquesta es pugui actualitzar sense generar cap inconsistència en les dades.

En cas que s'estigui utilitzant JavaScript, es recomana l'ús de la següent [expressió regular](https://ca.wikipedia.org/wiki/Expressi%C3%B3_regular) per a extreure el codi de la comarca de la cadena de text corresponent: 

``(/\((\d+)\)$/)``

## Font de les dades

Per a generar el fitxer JSON s'ha emprat la informació posada a disposició al portal de dades obertes de la Generalitat de Catalunya: [Municipis Catalunya Geo](https://analisi.transparenciacatalunya.cat/Urbanisme-infraestructures/Municipis-Catalunya-Geo/9aju-tpwc/about_data). 

***Versió de les dades:*** *28 de desembre de 2023*

## Metodologia

El tractament de les dades s'ha realitzat de manera automatitzada mitjançant l'eina [ChatGPT](https://ca.wikipedia.org/wiki/ChatGPT) ([GPT-4](https://ca.wikipedia.org/wiki/GPT-4))

## Motivació

En el moment de la creació d'aquest repositori no s'ha trobat cap d'altre que proporcioni en format JSON la informació mínima per a poder generar de manera senzilla i sense dades innecessàries formularis per tal que els usuaris puguin indicar la seva comarca i municipi.
