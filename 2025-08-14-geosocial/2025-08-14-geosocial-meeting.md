# Geosocial Task Force, 2025-08-14

## Present

- Jeremiah Lee, [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah) (he|they)
- Mike Waggoner, [@herebox@social.coop(https://social.coop/@herebox)]
- Ted Thibodeau Jr (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda


## Minutes

- Evan away at [HOPE](https://hope.net/)
- Another event of interest to follow: [WHY](https://why2025.org/)

- [FediCon videos](https://spectra.video/c/fedicon_videos/videos) from earlier this month

- Mike just attended DWeb Cascadia Vancouver with a good amount of geosocial discussion [DWeb](https://dwebyvr.org/). About 50 engaged people.
    - Interested in surveying larger population for persistent location sharing (family, loved ones). Not many there did. Almost everyone used Apple's Find My.
    - [Meshtastic](https://meshtastic.org/) appears to have modified defaults to obscure precise location.
    - ATProto work on events and venue focused geosocial apps based on Foursquare data set as starting point
        - https://atprotocol.dev/location-data-on-at-protocol-the-second-community-fund-project/
- Mike targeting end of next week for explainer. October FediForum nice to have in place deadline nearing.

- [FediForum Fall 2025](https://fediforum.org/news/2025-08-06-fediforum-fall-announced/): October 7-8. Do we want to plan any session? Anyone planning to demo anything geosocial related?
    - Mike and Jeremiah attending

- Instagram Map [launched](https://techcrunch.com/2025/08/08/how-to-use-instagram-map-and-protect-your-privacy/) to major privacy concern
    - Not yet available in Europe
    - Use cases align with the user stories we've defined for our explainer
    - Mike: How to represent real time moving data?
        - Announce -> JSON-LD link to a feed of location data
        - Jeremiah: Don't want to flood people's feeds with lat/long coordinates. Need the right type of server/client processing to deal with it.
        - Mike: https://h3geo.org/ -> https://hex.camp/ below

- ESRI User Conf report - Mike attended. Not much public geosocial discussed. Working on a point of interest database with other companies (Here Maps) to take on Google Places.
    - Incorporating Open Street places as a starting point. Uses open data, but is closed and commercial focused.
        - ESRI joined as partner to contribute to Overture maps as open data set to sit next to Google Places
        - https://overturemaps.org/
        - https://www.esri.com/arcgis-blog/products/arcgis-living-atlas/announcements/overture-maps-data-in-arcgis
    - Example of closed dashboard using open spec - GTFS - https://gtfs.org/
        - GTFS came out of Google. https://github.com/google/transit
        - Phoenix, AZ example of city licensing transit data well
 - h3geo use case where hexes are membership oriented circles for sharing open social web data e.g. https://hex.camp/
     - Use a hexagon to create sharing groups
     - Jim Pick discussing at DWeb

- complementary (and complimentary!) dataset — [Foursquare Open Source Places (“FSQ OS Places”)](https://foursquare.com/resources/blog/products/foursquare-open-source-places-a-new-foundational-dataset-for-the-geospatial-community/)

## Other related topics
- one path to recent OpenLink MCP offerings —
    - Generic MCP Server for ODBC (https://github.com/OpenLinkSoftware/mcp-odbc-server)
    - Generic MCP Server for JDBC (https://github.com/OpenLinkSoftware/mcp-jdbc-server)
    - Generic MCP Server for pyODBC (https://github.com/OpenLinkSoftware/mcp-pyodbc-server)
    - Generic MCP Server for SQLAlchemy (https://github.com/OpenLinkSoftware/mcp-odbc-server)
    - MCP server for ADO\.NET (https://github.com/OpenLinkSoftware/mcp-adonet-server/)


## Action items

- [Next meeting is on 2025-09-11](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20250911T130000/)
