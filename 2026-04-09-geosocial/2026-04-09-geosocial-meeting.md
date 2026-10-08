# Geosocial Task Force, 2026-04-09

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- [Jeremiah Lee](https://alpaca.gold/@Jeremiah) (he|they)
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

- Mike: async updates
- Evan: microsyntax proposal followup from last meeting
- Jeremiah: Session ideas for next FediForum on [April 28–30](https://fediforum.org/2026-04/)

## Minutes

- Mike unavailable for meeting today, but sent an update about the AT Protocol conference "[ATmosphere](https://atmosphereconf.org/)" last weekend.
  > - My takeaway from atmosphere is that [places.pub](https://places.pub) is on the right track and it makes sense to iterate and improve the search interface for various use case. Props on getting it live with such low infra overhead.
  > - The [AT Protocol Community Fund](https://atprotocol.dev/community-fund/) sponsored work into geosocial over the past year and created a service similar to [places.pub](https://places.pub) as a reverse proxy into three sources of POI data: Overture maps; Foursquare places; and Open Street Map. The available API also allows queries to return suggested results based on location and keywords. Docs are up at [atgeo.org](https://atgeo.org/)
  >   - ATproto "core" lexicons has defined four [location lexicons](https://lexicon.garden/browse/community.lexicon.location): `address`, `geo`, `fsq` (Foursquare), [`hthree`](https://h3geo.org/).
  >   - However the protocol does not natively support activities (arrive, leave, etc.) in the same way.  So that does not translate directly.
  >     - I put some of the above together on the atproto service Leaflet at https://here.leaflet.pub/ as an excuse to try leaflet.
  >         - More conference notes: https://here.leaflet.pub/3mi44mrpaus2h
  >     - Semi-unrelated, but also worth mentioning is https://panproto.dev/ - tutorial at https://panproto.dev/tutorial/ .  This kind of software might be helpful in translating schemas across geosocial services.
    - Evan: Interested in compatibility for bridging, but not information on the social aspect of the places data. Would be interesting to learn if there is a microsyntax being usined on the Bluesky side

- Evan: Microsyntax for location, [issue #16](https://github.com/swicg/geosocial/issues/16)
    - Value is the lightweight ability to add location data to posts without evolving client/server data structures
    - Discussion previously focused on notation formats
    - Evan shared doc proposal in [pull request #31](https://github.com/swicg/geosocial/pull/31)
    - Examples
      - Example 1 (section 2.1 in doc): Identification and linking can happen server side or client side
      - Example 2 (section 2.2 in doc): Conversion to Activity Streams Place object
    - Licensing issues with place databases:
        - [Mapcodes](https://www.mapcode.com/): commercial use requires licensing
        - [What3Words](https://what3words.com/about): proprietary for private and commercial use
        - [Plus Codes](https://maps.google.com/pluscodes/): freely licensed
    - Evan: Discussion question: Do we stick with a broad spectrum of syntax options or do we keep it simple?
    - Jeremiah: What about OSM ids?
        - Evan: Is there anyone doing a similar microsytax for OSM? Likes that it's easily linkable and we could make a places.pub id with it. Have to include the OSM type, not just id.
            - Jeremiah: Is the `///` microsyntax a What3Words thing?
                - Evan: yes
    - Jeremiah: I like the two options of a client-only solution and a server-option for when servers like Mastodon decide to support location better.
    - Jeremiah: Licensing of Mapcodes and What3Words rules out their inclusion for me. When does something become commercial? I think they could be included, but not recommended. Not sure we have leverage to get licensors to adjust their  terms.
        - Evan: Argument for not including: Maybe just document in the issue and take an opinionated stance for using options with an open license. Could be non-normative text.
            - Jeremiah: I like this. Document that it was discussed and considered, but not chosen.
    - Jeremiah: So reduce to Plus Codes and OSM?
    - Evan: We might not need any prefix. OSM has an identifable format: ``\b[R|N|W]\d+\b`` Only concern is with false positives like W3 (our convening org), R0 (epidemiology), N8 (goodnight in DE, FR)
    - Decision: Reduce to OSM ids and Plus Codes.

- FediForum ideas:
    - Jeremiah & Evan: Would like to collaborate with the AT Proto community on geosocial work to align
    - Evan: Let's propose a session with the explainer and microsyntax PR, advertise it early, do outreach to AT Proto people.
    - Mike proposed possibly doing a demo of check-ins. Need to follow up with him.

- Evan: Working Group starting on new ActivityPub work. W3C suggested a practice for using GitHub issues for assembling meeting agendas.
    - Example: https://github.com/swicg/activitypub-e2ee/issues/72
    - Agreement from Ted and Jeremiah to start this practice
    - Ted: Consider using wiki instead because the issues have (ahem) issues with multiple contributors editing an item.
        - Jeremiah: Great point, will use the GitHub wiki

## Off Topic
- [Shishi-odoshi (鹿威し)](https://en.wikipedia.org/wiki/Shishi-odoshi)

## Action items

- [Next meeting is on 2026-05-14](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20260514T130000/)
- Evan: Update pull request to only use Plus Codes and Open Street Map ids
- Jeremiah: Ask Mike if can do outreach to AT Proto geosocial folks for FediForum
- Jeremiah: Write FediForum session proposal and ask Johannes to promote ahead of time
- Jeremiah: Start using GitHub wiki for agenda creation
    - Done: https://github.com/swicg/geosocial/wiki/2026%E2%80%9005%E2%80%9014-agenda
