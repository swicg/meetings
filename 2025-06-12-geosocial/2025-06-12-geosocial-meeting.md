# Geosocial Task Force, 2025-06-12

## Present

- Bob Wyman
- Evan Prodromou <web+acct:evan@cosocial.ca>
- Jeremiah Lee, [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah) (he|they)
- Mike Waggoner [@herebox@social.coop](https://social.coop/@herebox)
- [TallTed // Ted Thibodeau Jr](https://github.com/TallTed) (he/him) [mastodon:@TallTed](https://mastodon.social/@TallTed) (OpenLinkSw.com)

## Agenda

- Mike: Fediforum recap
- Evan: Experimental implementations with geosocial
- Jeremiah: Anyone else attending [EU Next Generation Internet Forum](https://ngi.eu/ngi-forum25/) in Brussels next week?

## Minutes

Fediforum recap:
- Notes not yet published on Fediforum site. Usually come a few weeks later.
- Shared Places.pub and current draft of explainer
- Fedimeteo.com place and weather: identity for a place's weather to follow and get updates
- Question from Fediforum session: Schema.org place: how does AS2 recommend including details beyond the spec?
    - Evan: useful entities from vCard for Places, referenced in core spec: https://www.w3.org/TR/activitystreams-core/#object
    - Bob: It's a Schema.org "Location." One kind of location can be Place. See: https://schema.org/location vs https://schema.org/Place
    - Examples of address
- Bob: Did anyone mention the Use Case of hiking on the Moon or Mars? (Not currently possible with AS/AP.)
    - Strava-like use case of recording hike, bike are planned as part of the explainer
    - Note: Schema.org assumes the WGS 84 Coordinate Reference System (CRS) and thus, like AS/AP, is not useful for recording non-terrestrial locations. AS/AP should include a CRS (Coordinate Reference System) that defaults to WGS_84 on Earth. CRS values that should be supported can be found on https://spatialreference.org/
- Mike: Want to compare to OSM list of types of Places to FourSquare's, https://docs.foursquare.com/data-products/docs/categories
- Tools session: Samir and Fedica wanted to connect us with people working on location for AT Proto, Bluesky.
    - Evan: Seems to be happening outside of Bluesky corp, a community group. Might be worth reaching out to Bridgy Fed folks to make sure the location is correctly translated. Would be good to invite people working on that to a future meeting here to discuss collaboration.
- Fediforum attendee expressed concern about which mapping services linked to and if they adhere to EU GDPR. Someone needed to host their own tile server as a result of whatever logging the US provider was doing.
    - Jeremiah: Which service were they concerned about?
        - Mike: Unsure, maybe OSM itself.
    - Bonn.jetzt might be hosting its own tiles
        - gancio.org: Shared agenda for local communities
- Evan: Some questions at Fediforum were about things that already exist, some were about what people wanted to exist. Differentiate those 2 things in the explainer.
    - For example, Schema.org has info, how do I include that in my ActivityPub Places, this is how.
- Mike: How did Microformats and Schema.org influence AS2's development?
    - Evan: Activity Streams predates Schema.org, which came out ~2011. Activity Streams in Atom, Activity Streams 1 in JSON.
        - Bob: Schema.org is an initiative launched on June 2, 2011, by Bing, Google and Yahoo
    - AS2 included the Place structure, but not all the details. At the time, the licensing of Schema.org did not permit using beyond the search engine-specific use cases of spidering. Eventually, they came to an agreement with W3C.


Experimental implementations with geosocial
- Evan presented places.pub 2 meetings ago. Has continued to work on emitting events, but not shareable yet.
- ap-components: https://github.com/social-web-foundation/ap-components
    - https://socialwebfoundation.org/2025/05/28/ap-components/
- https://acct.swf.pub/ Demo of Webfinger Browser. Plans to use same tool for sending checkins and seeing friends' checkins
- ap: CLI extending tool from book: https://github.com/evanp/ap Will add check in, out, travel vocabulary to emit some activities
- Mike: With relying on places.pub, is it based on last known good data from Google in 2022.
    - Evan: Has asked Google to update
- Jeremiah: Would be good to get these objects with location into Fediverse Observatory, as this is used to track object properties and the servers using them. These are then used by another project for generating test data for ActivityPub server implementations. Not sure how to get new data into it. https://observatory.cyber.harvard.edu/
    - Background: https://asml.cyber.harvard.edu/2024/10/25/fediverse-observer/

Evan: Social CG tomorrow. Would be good to do a report out.

Jeremiah: Attending EU NGI Forum next week. NGI program funded NLnet, who then funded many social web apps. Unfortunately, EU ended funding of open source to focus on EU "AI" initiatives.

Evan: Are there geo-related events this group should be attending?
- RIP [O'Reilly Where 2.0](https://wiki.openstreetmap.org/wiki/Where_2.0) conference. Do we need a new conference for Geo Hipsters?
- Esri, July 14-18, 2025: https://www.esri.com/en-us/about/events/uc/overview
- State of the Map, Boston, June 14: https://openstreetmap.us/events/state-of-the-map-us/2025/

Next meeting: 2025-07-10 https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20250710T130000/
