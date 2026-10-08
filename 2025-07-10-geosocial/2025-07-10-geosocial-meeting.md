# Geosocial Task Force, 2025-07-10

## Present

- Evan Prodromou
- Jeremiah Lee, [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah) (he|they)
- Mike Waggoner
- Ted Thibodeau Jr (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

- Evan: inquiring minds want to know about mysterious posts
- Mike: Update on posting paths
- Mike: Posting locations in plain text, [issue 16](https://github.com/swicg/geosocial/issues/16)

## Minutes

- Evan: [Check-in proof of concept](https://github.com/social-web-foundation/checkin) demo
    - Continuation of discussion from last meeting on making a checkin app
    - Goal is to get to basic Swarm-like features
    - Using client to server ActivityPub API
    - Checkin uses places.pub to get the closest places from the browser location API. Gets every boundry box nearby.
    - Mastodon seems to ignore this kind of post (sadly expected). It doesn't know how to handle an Arrive activity.
    - https://onepage.pub/ Evan's ActivityPub API home server, primary user account  @evan@onepage.pub
        - Evan's server that supports C2S: https://github.com/evanp/onepage.pub
    - https://checkin.swf.pub/ is a client app. No database. Purely client-side.
    - https://cosocial.ca/@evan/114827062509476515 links to the checkin activity of https://onepage.pub/arrive/9lt7vKoZItLS5WYULIBkr
        - An Arrive activity
        - Location id is the places.pub location
        - [checkin-main.js](https://github.com/social-web-foundation/checkin/blob/main/js/checkin-main.js) Gets client's outbox, then posts an activity to the out
    - Plans to work on UI next
    - Jeremiah: What would ideal display look like in Mastodon et al?
        - Evan: Create Activity with an unknown type still has common elements: title, summary, URL, timestamp, actor. These are good enough substitute for understanding what the object is. Having a link is better than nothing.
        - Article type (longform text) in Mastodon 4.4 is getting better, but for unknown Activity types (like Checkin) it just throws it away at the moment.
- Mike: Discussion of [Client-to-Server ActivityPub API](https://www.w3.org/TR/activitypub/#client-to-server-interactions)
    - The challenge of using new types of data is that many servers don't know how to deal with new types
    - Mastodon only uses server-to-server ActivityPub API. It had its own API that predates ActivityPub.
    - Mastodon does not allow posting activities to your outbox.
    - Mastodon only accepts some kinds of Activities it receives from the server-to-server API. It converts some activities into its own microblogging format.
    - Only a few servers support C2S at the moment: OnePage.pub, Pleroma, maybe Pixelfed
        - Darius, Hometown Mastodon fork maintainer might be open to supporting the other types
- Mike: Microsyntax for location discussion, [issue 16](https://github.com/swicg/geosocial/issues/16)
    - Jeremiah: Need to add comment about using the OSM ids with a prefix like OSM:[Open Street Maps location id]
- Mike: Traewelling.de
    - You can sign into Traewelling with a Mastodon identity, but not posting much location data yet.
    - Working on checking into "paths"
    - Traewelling pulls data from https://www.transit.land/ GTFS feeds
    - https://help.traewelling.de/en/faq/

- General discussion:
    - Jeremiah: NLnet podcast about how Cyber Resilience Act might increase funding to FOSS: https://open.spotify.com/episode/7lbuof8WYp7ByZ8JHqjecj?si=09bcc19c2b2145a1
    - Jeremiah: Ghost does a great job with differentiating between Article and Note. Not sure about other types. [Recent discussion with long-form ActivityPub users](https://activitypub.ghost.org/the-longformers/)

## Action items

- Ask Evan for a key if you want to test with OnePage.pub

- [Next meeting is on 2025-08-14](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20250814T130000/)
