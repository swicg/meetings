---
title: ActivityPub API Task Force 15 Jan 2026

---

# ActivityPub API Task Force 15 Jan 2026

## Present

- Evan Prodromou <acct:evanp@socialwebfoundation.org>
- Aurélien <acct:opsocket@mamot.fr>
- a <trwnh.com>

## Agenda

- Meeting schedule
    - "3rd Thursday, 16:00 UTC"
    - Seems OK
    - Meetings seem like a good idea!
- Explainer
    - [Explainer explainer](https://www.w3.org/TR/explainer-explainer/)
        - > An explainer introduces a problem that a group of people are trying to solve, and helps everyone with an interest in the target problem find consensus on a good way to solve it.
    - A document that describes the problem that you're working on, possible solutions, alternative solutions, who is working on the problem, and how they are collaborating
    - Living document that evolves and changes
    - NOT a standard or specification
    - Use GitHub flow
    - More committers to the task force
- Implementation work
    - E2EE development: https://github.com/swicg/activitypub-e2ee
        - Uses ActivityPub API
        - Bonfire & Emissary are building this into their platforms
        - https://socialwebfoundation.org/2025/12/19/implementing-encrypted-messaging-over-activitypub/
    - DD: [Progressive Web App](https://github.com/mediaformat/c2s) 
        - Working with different projects
        - Pleroma
        - Had to build a proxy
        - Fedbox
        - Bonfire
        - WP AP!
        - onepage.pub
    - Aurelien
        - Polling app (Selene paper) verifiable / non-coercion polling, voting, ranked voting, weighted ranked voting (!)
            - [Selene: Voting with Transparent Verifiability and Coercion-Mitigation](https://inria.hal.science/hal-01242690v1)
        - Federated replacement to [Discogs](https://www.discogs.com) (Vinyl records database and marketplace)
    - EP
        - https://acct.swf.pub/ Webfinger Browser
        - https://checkin.swf.pub/ Geosocial Checkin
        - [Web Component library for Activity Streams and ActivityPub](https://github.com/social-web-foundation/ap-components) 
        - https://github.com/evanp/ap
    - a: Publishing activities to an activity stream on my website
        - my main project is a sort of "fundamentalist" approach to ActivityPub for the purpose of publishing activities to an activity stream. the uri will probably be something like https://trwnh.com/activity which is currently conceptualized as an HTML page of whatever i've been up to recently, and this can be also translated into an Atom feed, but given that the use case here is "publishing activities", ActivityPub seems like it's worth considering! the whole exercise has revealed a lot of gaps (and led to a lot of issues being filed!) that i would love to have documented so that other applications can implement "the ActivityPub API" and publish activities to my outbox. in the immediate sense, this means an auth-scheme (to be used with HTTP WWW-Authenticate and Authorization headers) and some understanding of what will happen with the POST to outbox (constraints, behaviors, and so on). 
    - https://delightful.coding.social - https://codeberg.org/fediverse/delightful-fediverse-experience/issues/130
- Notable issues...?
    - [Is AP the everything API?](https://github.com/swicg/activitypub-api/issues/19)
        - [AtomPub](https://en.wikipedia.org/wiki/Atom_(web_standard))
        - Does ActivityPub let you do everything a platform API would do?
            - a: It can be one of a suite? "Publish activities" and "Read notifications" are already 2 separate endpoints (outbox and inbox). APIs should enable the use cases around whatever you want the interfaces to include. Step 1 is identifying those use cases and needs, then designing an API to address those needs and use cases.
        - Start with a kernel (AP API, CRUD + Social Graph, Reactions)
        - Enhance with (optional?) extensions
    - [OAuth profile](https://github.com/swicg/activitypub-api/issues/1)
        - How do you log in?
          - a: HTTP has WWW-Authenticate header (to advertise any supported auth-scheme for use with Authorization header). There are other ways to advertise relevant metadata (OAuth has their various metadata RFCs, HTTP Message Signatures has the Accept-Signature header), but the actual definition of -- and formal specification of -- a fully constrained auth-scheme has mostly been neglected so far. the Bearer auth-scheme has you doing everything out-of-band to get a token. the Basic auth-scheme has you encode a string of your username and password. It would be beneficial to have an auth-scheme defined in enough detail that you can unambiguously authorize any HTTP requests made to AP API endpoints!
        - Best practices for servers
            - [OAuth Authorization Server Metadata](https://www.rfc-editor.org/rfc/rfc8414)
            - [CIMD](https://client.dev/)
        - Best practices for clients
            - Client IDs
                - ActivityPub object as client ID (https://w3id.org/fep/d8c2)
                - Dynamic registration (https://datatracker.ietf.org/doc/html/rfc7591)
                - Mastodon API registration?
                - ...?
            - Endpoint discovery
                - ActivityPub actor
                  - a: the actor resource should be the entrypoint for any further discovery, imo. optionally, if the actor id isn't known, something like WebFinger could be used to allow discovery of the actor resource, but it would be better to already have a URI or DNS name since that can be (and in many cases, is!) easier to communicate to others in a social setting if kept simple. ("visit foobar dot com for more information" or "username dot tumblr dot com" are common sentence constructs in other contexts, but "i am localpart at domain dot example" is also commonly used enough to be worth considering support)
                - ...?
                - a: we have as:endpoints which is a bit underdeveloped but could in theory be refined to handle more of this. right now the main endpoint being used is as:sharedInbox probably? it makes sense to (re)consider the processing model (and semantics) for as:endpoints... at least in practice, it seems like the range of as:endpoints is an "endpoint mapping", which may be shared with other actors e.g. "server-wide endpoints" almost as a mini-version of host metadata. i think that formalizing this (or some variant of this) as an actual way to specify a link to host metadata could be useful.
        - [Activity Diagram](https://github.com/swicg/activitypub-api/blob/main/OAuth%202.0%20for%20ActivityPub%20Activity%20Diagram.png)
    - Future meeting agenda
        - EP: OAuth profile document
        - DD: Demo!