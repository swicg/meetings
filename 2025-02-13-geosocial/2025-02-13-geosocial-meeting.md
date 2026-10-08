# Geosocial Task Force, 2025-02-13

## Present

- Jeremiah Lee [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah) (he|they)
- Matt Terenzio @librenews@mastodon.social
- [TallTed](https://github.com/TallTed/) // Ted Thibodeau (he/him) (OpenLinkSw.com) (https://mastodon.social/@TallTed)

## Agenda

- [Microsyntax for location](https://github.com/swicg/geosocial/issues/16)
- Matt: Setting location on profile user story
- (Any update from Mike from [last meeting](https://hedgedoc.socialweb.coop/s/D7yKLjJQs)?)

## Minutes

- Microsyntax for location
    - Jeremiah: Curious about the interest and the use case. Seems to be limited to specific coordinates (not broader concept of location: a specifc entity at the space, a region with boundary), unless using some other "canonical" location id. We have an object for referencing location richly, so what use case does this solve best?
    - Matt: How do we recognize a tag references the same place? Seems to require something in the UI to translate the location to the string.
    - Ted: Precision challenges (e.g., someone who wants to tag their location as precisely as possible, such that rescuers can find them on the hiking trail, for instance, vs. someone who wants to tag only generally such that their stalkers cannot find them too easily...)
- Matt: wanting to add location object to profiles, not just the profile fields
- Matt: Any community news on importing Foursquare data into OpenStreetMaps?
    - Jeremiah: Not aware. Would be good to have alsoKnownAs, but not sure about wholesale import.
    - Ted: Quality issues from user generated ("Dave's home")
- Concluded at 32 minutes

## Action items

- Matt will add user story to Github repo
