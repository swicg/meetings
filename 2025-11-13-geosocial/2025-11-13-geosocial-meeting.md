# Geosocial Task Force, 2025-11-13

## Present

- Ben Pate, @BenPate@mastodon.social
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Jeremiah Lee [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah)
- Mike Waggoner <@herebox@social.coop>
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

- Mike: CoMotion Conference updates
- Ben: Atlas work demo
- Upcoming event sharing

## Minutes

- Mike: Hopscotch Labs [BeeBot](https://djbeebot.com) app soft launched for iOS and US only. [Concept description](https://dens.medium.com/say-hello-to-dj-beebot-592cdc1f1704)
- Mike: [CoMotion Conference](https://www.comotionglobal.com/comotionla2025) update from Los Angeles
    - Government focused
    - Lots of robots surveiling places and providing updates to their operators. One possible non-creepy use is updating Open Street Map data in an automated way.
    - https://www.openmobilityfoundation.org/ trying to create an open Mobility Data Specification (MDS) for micro-mobility, taxis, car shares, delivery robots, etc.
        - Being used by several companies and cities. Unsure about use in EU.
            - Its GDPR page: https://www.openmobilityfoundation.org/using-mds-under-gdpr/
    - Not sure yet how location data is being represented.
    - Evan: Is it a path? An object like a bus on a path? Or a conceptual place (as opposed to lat/lon)?
    - Mike: Some city use cases for reporting scooters knocked over, parking violations, loading zones, preventing delivery robots from stopping in no-stopping zones, using the sensors that are rolling around to keep maps updated.
    - Curb Data Specification: data spec for what happens at curbs
    - Evan: ActivityPub is an authenticated data exchange. Individuals could be concerned about their data being used. ActivityPub doesn't have an anonymous way to share location data for other uses.
    - Mike: An interesting trend is that hardware is doing data processing on the device to remove some information from images/video, such as blurring faces.
        - Ted: There are situations where this is undesireable, such as law enforcement abuse prevention.
        - Evan: Similarly, context can be used to identify people by correlating movement patterns of a single person.
    - Evan: Any new issues or use cases for us / the taskforce?
        - Mike: There are many delivery robots and self-driving taxis rolling around. Letting them check in socially? They're trying to deliberately advertise their location and don't have privacy concerns of sharing due to their non-person-ness.
        - One use case is checking into riding transit. Possible in DE, but not LA due to licensing issues.
        - Ben: One use case of looking for activity around an area. Could be useful to be able to see autonomous devices nearby. What happens when you see a bunch of police in one spot and want to know what's happening/happened?
            - Ted: There was an app that supposedly reported police activity. Perhaps some data integrity issues based on frequency of reports, but lack of evidence in physical world. Another app listening to police radios, transcribing.
            - Mike: Seems like it would depend on the data sharing in the area.
        - Mike: Socially share road closures quickly to inform re-routing. Or overload to use for events.
- Evan: FourSquare has private places that let me associate a place like "At Mom's" that's only meaningful to me and my friends, but not others.
- Ben: Can places.pub get a check-in location to a train / transit route?
    - Ted: Complexity example. T-line train route is not an actual train, but is path run by different cars.
    - Evan: OSM may have entities for some things like bus/train lines. Longer train lines might not. OSM focuses on appearance of map rather than maintaining an id for something. Interesting question that needs to be dug into more.
    - https://gtfs.org/documentation/schedule/examples/shapes/
    - Example: https://www.transit.land/operators/o-9q5-metro~losangeles#stops
- Ben: A place or location has lat/lon, but not address. How is best to geocode it?
    - Evan: Places.pub uses vCard. AS2 vocabulary has an example using vCard. Seems to work well with address formats in many countries, but probably not all.
    - Ted: There is no single standard for addresses. https://github.com/kdeldycke/awesome-falsehood?tab=readme-ov-file#postal-addresses
- Ben: Atlas map demo: https://atlasdemo.emissary.social/
    - Goal is to make it as easy as possible to share an ActivityPub Note on a map.
    - Notes go into search engine to get posts from multiple servers. Still working on relaying.
    - Emissary is a general purpose service that can be configured in various ways. Atlas is one such configuration.
    - Ben has added geocoding services and tile servers. Doesn't want to make an open source service dependent upon one single server.
    - QR codes for sharing
    - Emissary has the ability to allow people to follow a search result. Creates a new Actor for a search result. Every time a new result is added, it's pushed to followers.
    - Interested in collaborating with people who want to have Notes on a map and their use cases: @BenPate@mastodon.social
- Evan: Social CG meeting later today via Zoom (see email)
    - https://www.w3.org/events/meetings/853f023a-d5ce-44ec-a222-3b4c8ec849a9/
        - Uses Zoom today instead of Jitsi, sign in to see


## Other related topics

- Upcoming events
    - Nov 19: https://www.eurosky.social/eurosky-live
        - AT Proto focused but some geosocial stuff likely happening
    - Dec 13-14: San Diego: Indie Web in person meetup https://indieweb.org/2025/SD
- "Transit vigilante" created a real-time bus tracker for his neighbors https://mastodon.green/@light_bulbs/115543902687060969

## Action items

- [Next meeting is on 2025-12-11](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20251211T130000/)
