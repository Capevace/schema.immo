# Schema.immo

`schema.immo` is an experimental, modern data standard for the real estate sector.

This documentation describes the data types used in the `schema.immo` data standard.

> `schema.immo` is currently in development and **NOT** licensed for public use. It will eventually be available
> as an open and living data standard, most likely licensed under the MIT license. However, we want to discourage its use before the initial version is > finalized.
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
