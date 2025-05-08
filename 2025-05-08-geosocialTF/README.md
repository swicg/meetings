# Geosocial Task Force 2025-05-08

Geosocial issue tracker: https://github.com/swicg/geosocial

[Next meeting](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/#next) scheduled 12 June 2025, 13:00–14:00 Eastern Daylight Time

Archived: https://github.com/swicg/meetings

## Present

* Bob Wyman
* Dmitri Z
* Evan Prodromou
* [TallTed // Ted Thibodeau Jr](https://github.com/TallTed) (he/him) [mastodon:@TallTed](https://mastodon.social/@TallTed) (OpenLinkSw.com)
* [Mike Waggoner](https://herebox.org)

# Agenda

* places.pub updates
* Next steps -> check-in app
* GeoSocial Explainer progress
* ..

---

# Minutes

## https://places.pub/ service release

_a collection of Place objects suitable for use in geosocial applications on the ActivityPub network._ with initial version announcement at https://socialwebfoundation.org/2025/04/29/places-pub/

Evan: Activity Pub objects are supposed to have a live JSON-LD URI with additional information.  This requirement makes it difficult to work with places in the world.  The point of places.pub is to be fallback or default for working with places based on OSM.

Example Rodgers center - https://places.pub/way/364535169

Multityped AS2 Object
 - Place
 - geojson:Feature

Discussion on places.pub
* Lat/Long have no meaning without reference to a Coordinate Reference System. You need a "`crs:`" property to specify CRS which shouild default to `"WGS-84"` or `"EPSG:4326"`.
  * This sounds like a good addition.  New issue added to places.pub repo
  * IAU values on https://spatialreference.org/ support non-terrestrial values within our solar system — e.g., on Mars, or Moon — but not in orbit or between bodies.
    * See an example for Earth's moon (i.e., first moon of third planet from Sol): https://spatialreference.org/ref/iau_2015/30115/
  * OpenStreetMap's default Coordinate Reference System (CRS) is WGS 84 (EPSG:4326). See: 
  * When traveling between an origin and a target, it is possible that origin and target have different coordinate systems. (i.e. When travelling from Earth to Moon.)
* Multityped in AS2 object, e.g., `"type":["Place","geojson:Feature"]`
  * Multitype is supported in AS2, and allows additional detail including OSM element type geojson
  * OSM defines three element types [relation, way, node]
* What is the consequence if <https://places.pub/> service disappears?
* How stable/up-to-date is Google Cloud Public Datasets?  Licensing?
  * Running on Geosocial Google Account
  * Data set has not been updated since 2022, Evan.
* Use of geopolitical containers, e.g., country?

## Check-in app

* Login as a client to activity pub server
* Check-in as an "Arrive" activity with a places.pub uri as JSON-LD

Ideal - ActivityPub API
 - Geosocial apps will use the _ActivityPub API_

Practical - Mastodon API 
 - Uncertain how an Arrive activity might exist in the Mastodon ecosystem.
 - Adding a _location_ attribute is supported today and partially implemented as an author on some services like Pixelfed ( well known cities only )

## Explainer updates

Explainer work in progress in hedgedoc from 2025-03 task force meeting at https://hedgedoc.socialweb.coop/kUPvzmd4SjyN1oGxyrzskQ

Explainer Todos
* Update refs to places.pub to indicate it is one of multiple possible providers for @id?
* Add detail on "also known as" for handling multile @id attributes describine the same place
* Ephemereral places support
* Are "@id" attributes required?
  * Yes, although the id can be flexible
  * It is possible to register a few semantic @ids that are flexible to handle "ephemeral" locations
  * Like "as:Public" in the _to_ or _cc_ fields of an AS2 activity

```
    "to": [
        "https://example.com/user1/followers",
        "as:Public"
    ],
```

## Followup notes
* Evan: Considering software architecture for check-in app driven by fediverse clients
* Mike: Publish explainer work so far to https://github.com/swicg/geosocial
* Mike: Publish call notes to https://github.com/swicg/meetings