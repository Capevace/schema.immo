`schema.immo` is an experimental, modern data standard for the real estate sector.

This documentation describes the data types used in the `schema.immo` data standard.

> `schema.immo` is currently in development and **NOT** licensed for public use. It will eventually be available
> as an open and living data standard, most likely licensed under the MIT license. However, we want to discourage its use before the initial version is finalized.
>
> It will also feature first-class library support for:
> - TypeScript / JavaScript
> - PHP
> - Java


## Contact

The `Contact` class represents a contact person associated with an estate.

#### Fields

- `name` (string, required): The name of the contact person.
- `role` (string, optional): The role or position of the contact person.
- `email` (string, optional): The email address of the contact person.
- `phone` (string, optional): The phone number of the contact person.
- `mobile` (string, optional): The mobile phone number of the contact person.
- `address` (Address object, optional): The address of the contact person.

## Estate

The `Estate` class represents a real estate property.

#### Fields

- `id` (string, required): The unique identifier of the estate.
- `slug` (string, required): The slug or URL-friendly identifier of the estate.
- `name` (string, required): The name or title of the estate.
- `address` (Address object, required): The address of the estate.
- `features` (array, optional): Additional features or characteristics of the estate.
- `texts` (Texts object, optional): Textual descriptions and information about the estate.
- `media` (Media object, optional): Media files (images, videos) associated with the estate.
- `location` (Location object, optional): Geographic location information of the estate.
- `certifications` (Certifications object, optional): Certifications or ratings related to the estate.
- `social` (Social object, optional): Social contacts associated with the estate.

## Address

The `Address` class represents a physical address.

#### Fields

- `street` (string, required): The street name of the address.
- `number` (string, required): The house number of the address.
- `postal_code` (string, required): The postal code of the address.
- `city` (string, required): The city or locality of the address.
- `country` (string, optional): The country of the address.
- `coordinates` (Coordinates object, optional): Geographic coordinates (latitude and longitude) of the address.

## Certifications

The `Certifications` class represents certifications or ratings related to an estate.

#### Fields

- `dgnb` (DGNB certification enum, optional): The DGNB certification level of the estate.
- `co2_neutral` (boolean, optional): Indicates if the estate is CO2 neutral.

## Coordinates

The `Coordinates` class represents geographic coordinates (latitude and longitude).

#### Fields

- `latitude` (float, required): The latitude coordinate.
- `longitude` (float, required): The longitude coordinate.

## Location

The `Location` class represents geographic location information of an estate.

#### Fields

- `places` (array of Place objects, required): Places of interest near the estate.

## Place

The `Place` class represents a place of interest near an estate.

#### Fields

- `type` (string, required): The type or category of the place.
- `name` (string, required): The name of the place.
- `coordinates` (Coordinates object, required): The geographic coordinates of the place.
- `address` (Address object, optional): The address of the place.
- `directions_from_estate` (Directions object, optional): Directions from the estate to the place.

## Directions

The `Directions` class represents directions from one location to another.

#### Fields

- `from` (Coordinates object, required): The starting coordinates.
- `to` (Coordinates object, required): The destination coordinates.
- `distance_air` (float, required): The air distance between the starting and destination coordinates.
- `walking` (Route object, optional): Walking route information.
- `cycling` (Route object, optional): Cycling route information.
- `driving` (Route object, optional): Driving route information.
- `public_transport` (Route object, optional): Public transport route information.

## Route

The `Route` class represents route information.

#### Fields

- `duration` (float, required): The duration of the route in minutes.
- `distance` (float, required): The distance of the route in kilometers.

## Texts

The `Texts` class represents textual descriptions and information about an estate.

#### Fields

- `slogan` (string, optional): A slogan or catchphrase describing the estate.
- `description` (string, optional): A detailed description of the estate.
- `location_text` (string, optional): Textual information about the location of the estate.

## Media

The `Media` class represents media files (images, videos) associated with an estate.

#### Fields

- `thumbnail` (Image object, optional): The thumbnail image of the estate.
- `gallery` (array of Image objects, optional): The gallery of images associated with the estate.
- `logo` (Image object, optional): The logo image associated with the estate.
- `videos` (array, optional): Video files associated with the estate.
- `scans` (array, optional): Scan files associated with the estate.

## Social

The `Social` class represents social contacts associated with an estate.

#### Fields

- `contacts` (array of Contact objects, required): Social contact persons associated with the estate.


# Example `Estate` data:

```json
{
    "id": "f9d7a798-0d9a-4dc7-b5a3-49ff68e43283",
    "slug": "ludwig-meissner-strasse-91",
    "name": "Lindenstraße",
    "address": {
        "street": "Lindenstraße",
        "number": "30",
        "postal_code": "23558",
        "city": "Lübeck",
        "country": "Deutschland",
        "coordinates": {
            "latitude": 53.86423545,
            "longitude": 10.66994001
        }
    },
    "features": {
        "elevators": true,
        "led_lighting": true,
        "block_heating": true,
        "rentable_area": true,
        "address": true,
        "distance_airport": true,
        "plot_area": true,
        "gas_heating": true,
        "distance_main_station": true,
        "green_courtyard": true,
        "lighting_with_motion_detection": true,
        "distance_port": true,
        "washing_clothes": true,
        "social_tenant": true,
        "places_for_socializing": true,
        "parking_garage": true,
        "nearby_sports": true,
        "fiberglass_connection": true,
        "smart_metering": true,
        "electric_vehicle_charging_station": true,
        "pkw_slots": true,
        "marketing_website": true,
        "greened_roof": true,
        "greened_facade": true,
        "water_retention": true,
        "bees": true,
        "urban_gardening": true
    },
    "texts": {
        "slogan": "Flexibles Gewerbeobjekt mit nachhaltiger Ausstattung",
        "description": "<p>Willkommen in der \"Lindenstraße\", einem prägnanten Gewerbekomplex in der Lindenstraße 30, 23558 Lübeck. Diese flexibel nutzbare Immobilie besticht durch ihre nachhaltige Ausstattung, darunter ein effizientes Blockheizkraftwerk, eine umweltfreundliche LED-Beleuchtung und nicht zuletzt fünf E-Ladestationen. Innerhalb des Gebäudes erleben Sie eine Gesamtmietfläche von 20,0 m², gewährleistet durch die Anwesenheit von zwei Personenaufzügen. Zudem profitieren Sie vom Komfort von 200 PKW-Stellplätzen.</p>",
        "location_text": "<p>Unser flexibles Gewerbeobjekt befindet sich in prominenter Lage an der <strong>Lindenstraße 30, 23558 Lübeck</strong>, mit optimaler Anbindung an alle wichtigen Standorte. Der <strong>Lübecker Hauptbahnhof</strong> liegt nur knappe fünf Gehminuten entfernt, was sowohl Mitarbeitern als auch Geschäftspartnern eine reibungslose An- und Abreise ermöglicht. Der <strong>Flughafen Lübeck</strong> ist in etwa einer Stunde erreichbar und bietet internationale Verbindungen, ideal für Business-Trips oder internationale Partner.&nbsp;</p><p>Die umgebende Infrastruktur lässt keine Wünsche offen. In nur wenigen Gehminuten erreicht man zahlreiche Restaurants wie das \"Fünf &amp; Sechzig\", \"Zollpackhof\" und \"Subway\", die eine breite Auswahl an Mittagsoptionen bieten. Für den schnellen Einkauf nach dem Feierabend sind Supermärkte wie \"Edeka\" und \"PENNY\" direkt in der Nachbarschaft.&nbsp;</p><p>Die Körper- und Gesundheitsbewussten profitieren von der Nähe zu Fitnessstudios wie dem „Crossfit Mitte“ und „High 5“, die in weniger als zehn Gehminuten erreichbar sind.&nbsp;</p><p>Für erholsame Pausen im Freien finden Sie den <strong>Lindenpark</strong> und die <strong>Wallanlagen</strong> in direkter Umgebung, die jeweils in weniger als zwanzig Gehminuten erreicht werden können.&nbsp;</p><p>Das maritime Flair der Stadt wird durch die Nähe zum <strong>Travemünde-Hafen</strong>, der etwa dreieinhalb Stunden entfernt ist, unterstrichen.&nbsp;</p><p>Die hervorragende Lage, die Nähe zu allen wichtigen Verkehrsanbindungen und die Fülle an umliegenden Annehmlichkeiten machen dieses Gewerbeobjekt zu einem erstklassigen Standort.&nbsp;</p>"
    },
    "media": {
        "thumbnail": {
            "src": "https://umbrella.domos.test/tenancy/assets/9cb0d686-3543-4e06-ad6b-2f7480706243/03d8af03-5852-43b2-94e4-0620239eccd6.jpeg",
            "alt": null
        },
        "gallery": [
            {
                "src": "https://umbrella.domos.test/tenancy/assets/23b52fcf-a667-4392-aaf5-d3388f8e332d/03d8af03-5852-43b2-94e4-0620239eccd6.jpeg",
                "alt": null
            },
            {
                "src": "https://umbrella.domos.test/tenancy/assets/9cb0d686-3543-4e06-ad6b-2f7480706243/03d8af03-5852-43b2-94e4-0620239eccd6.jpeg",
                "alt": null
            }
        ],
        "logo": {
            "src": "https://umbrella.domos.test/tenancy/assets/3eee251e-8ea3-4f35-8311-0a5b5ccbe527/c4-header-neu.jpg",
            "alt": null
        },
        "videos": [],
        "scans": []
    },
    "location": {
        "places": [
            {
                "type": "restaurant",
                "name": "Fünf & Sechzig",
                "coordinates": {
                    "latitude": 52.5400018,
                    "longitude": 13.3527311
                },
                "address": null,
                "directions_from_estate": {
                    "from": {
                        "latitude": 53.86423545,
                        "longitude": 10.66994001
                    },
                    "to": {
                        "latitude": 52.5400018,
                        "longitude": 13.3527311
                    },
                    "distance_air": 231.50225339126257,
                    "walking": null,
                    "cycling": null,
                    "driving": null,
                    "public_transport": null
                }
            },
            {
                "type": "restaurant",
                "name": "Zollpackhof",
                "coordinates": {
                    "latitude": 52.5212821,
                    "longitude": 13.3668503
                },
                "address": null,
                "directions_from_estate": {
                    "from": {
                        "latitude": 53.86423545,
                        "longitude": 10.66994001
                    },
                    "to": {
                        "latitude": 52.5212821,
                        "longitude": 13.3668503
                    },
                    "distance_air": 233.58330437982553,
                    "walking": null,
                    "cycling": null,
                    "driving": null,
                    "public_transport": null
                }
            }
        ]
    },
    "certifications": {
        "dgnb": "silver",
        "co2_neutral": true
    },
    "social": {
        "contacts": [
            {
                "name": "Lukas Mateffy",
                "role": "Head of Software & IT",
                "email": "lukas@inframe.de",
                "phone": null,
                "mobile": null,
                "address": {
                    "street": "Scharnhorststraße",
                    "number": "1a",
                    "postal_code": "21335",
                    "city": "Lüneburg",
                    "country": "Deutschland",
                    "coordinates": {
                        "latitude": 53.2297852,
                        "longitude": 10.40502005
                    }
                }
            }
        ]
    }
}
```

##### Copyright
© 2023 Lukas Mateffy
