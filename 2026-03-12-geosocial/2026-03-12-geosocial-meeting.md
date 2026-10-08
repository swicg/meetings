# Geosocial Task Force, 2026-03-12

## Present

- a <trwnh.com>
- Evan P
- [Jeremiah Lee](https://alpaca.gold/@Jeremiah)
- [Mike Waggoner](https://social.coop/@herebox)

## Agenda

- Mike: Geosocial explainer PR [#30](https://github.com/swicg/geosocial/pull/30)
- Mike: W3C Geolocation group for updates to browser getting location: https://github.com/swicg/geosocial/pull/30
- Mike: Usage questions Places OrderedCollection
    - https://swicg.github.io/geosocial/personal-places.html
    - Example 7: need to remove dangling comma for JSON
    - New term for "places" collection
    - Evan: Problem: unclear who (client or server) is responsible for creating this collection and adding this property
        - Server could have this for you and server would add places you use your places collection
        - Or could be up to the client. When it sees there is no collection, create the collection, update the actor to have the collection, and then every time a person uses a place add it to the collection.
            - A: Wouldn't be any different from other collection you create on your own
        - This is an open question in other areas too.
        - If you want the server to do this automatically, there should be a way for signalling that it would do this and that is not something that has a defined pattern for doing.
            - Evan: Could indicate on the actor like serverManagesPlaces (strawman example)
            - A: managedBy property could be a list of similar things
        - Evan: recommends leaving up to client for now. Assume the client knows.
            - A: agreed, until a way to know, client just has to deal with the uncertainty
    - Intent to implement from Evan and Mike
        - Could extend Evan's work or Mike could do on the checkin app to have 2 implementations for a more robust recommendation. Mike will need to investigate.
    - Mike: thoughts on storage of these places overhead?
        - Evan: Likely limited set (< 100)
        - Evan: ActivityPub API has expectation that client can create these
- Upcoming events
    - W3C breakout days: 2026-03-25–26 https://github.com/w3c/breakouts-day-2026
        - Evan: Came out of TPAC, good for cross-working group discussions
        - Deadline was 03-10 to propose topics, but form still open.
        - Evan has a session about ActivityPub API proposed
    - ATmosphere: 2026-03-26–29: https://atmosphereconf.org/
        - https://atprotocol.dev/location-data-on-at-protocol-the-second-community-fund-project/
        - Potentially extending for venues in events ATProto service https://smokesignal.events/
    - FediForum 2026-04-28: https://fediforum.org/2025-06/
        - Jeremiah: Want to coordinate on a session? Could we set a goal for showing the explainer and implementations.
        - Mike: Next task force meeting is April 9, so decide then and ask Johannes about demoing or coordinate on a session
- Evan: Are there low-hanging fruit wins?
    - Challenge is that so much of current work is dependent upon API support on the server
        - [issue #26](https://github.com/swicg/geosocial/issues/26) Mastodon compatibility. Anything we could do right now for regular Mastodon users.
    - [Issue #16](https://github.com/swicg/geosocial/issues/16) microsyntax for locations
    - What microsyntax ID to recommend?
        - Plus.codes: `74X2+WJ`
            - Google-made, but not Google-dependent https://en.wikipedia.org/wiki/Open_Location_Code
        - Open Street Map ids: W370672707
        - What 3 Words: proprietary
        - /Slash Syntax/ http://microsyntax.pbworks.com/w/page/20869381/FrontPage
        - https://indieweb.org/microsyntax
        - Airport codes SFO > ARN or SFO ✈️ ARN
            - IATA codes are always 3 letters. ICAO are 4 letters.
    - Jeremiah: Is there a prefix needed, like #, @, $? 'LOC:'?
        - Does it become DID-like with specifying the location id authority? eg for Open Streem Map: LOC:OSM:W123466
        - Evan: Doesn't have to be. We could provide the regex to match.
            - OSM ids matching: `[RWN](\d+)`
            - What 3 Words seems matchable: `///bond.respects.reading`
    - Evan: Could propose it, get people using it, and hope Mastodon adopts like Twitter did for hastags and cashtags
        - Could document and talk to client developers, like Phanpy
        - Wondering if Mastodon would be interested. Pixelfed uses Places directly.
        - https://github.com/mastodon/mastodon/issues/11748
        - https://github.com/mastodon/mastodon/issues/281
    - Evan volutneers to take on a draft at a proposal next meeting

## Action items

- [Next meeting is on 2026-04-09](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20260409T130000/)
