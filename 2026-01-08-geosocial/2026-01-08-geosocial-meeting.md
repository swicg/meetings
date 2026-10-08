# Geosocial Task Force, 2026-01-08

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Jeremiah Lee [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah)
- Mike Waggoner [@herebox@social.coop](https://social.coop/herebox)
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

- Evan: Personal Place API
- Mike: Working group charter and task force impact

## Minutes

- Evan: Personal Place API
    - Swarm-like behavior where people can create personal places that may only be useful for individuals and their connections
    - User stories
        - https://github.com/swicg/geosocial/pull/29
        - Create: https://github.com/swicg/geosocial/issues/21
        - List: https://github.com/swicg/geosocial/issues/22
        - Edit: https://github.com/swicg/geosocial/issues/23
        - Delete: https://github.com/swicg/geosocial/issues/24
        - View/read: https://github.com/swicg/geosocial/issues/25
    - Similar CRUD-like use as with Notes
    - Proposal for new `places` property with value of ordered collection on the Actor
- Mike: What is the privacy consideration? Are these browseable/check-in-able by others?
    - Evan: Uses same methods as Notes, `to` property
    - Also can contain `radius` property
- Mike: `alsoKnownAs` property?
    - Could also link to an Open Street Map place, but it's alaised as something personal, like "work" or "home"
    - `alsoKnownAs` mostly used today for when things are moved from old server to new server
- Ted: Seems more likely that someone would want to permit a curated list of people that the person sharing maintains, rather than "anyeone who follows (watches) me".
    - Evan: Agreed and can use similar mechanism as Notes and other types
- Mike: How would this work with places.pub?
    - Evan: Should use same mechanics. Gave example with check-in app, the personal places could be intermixed with the personal places.
- Mike: How might a client handle public personal places?
    - Likes idea of being able to browse them to see other people's social vocabulary for public places
    - Collaborative editing of a place probably would not exist, but doesn't exclude that
    - Could lead to editing of OSM data and also potential addition of new OSM data type
    - Evan: Similar to Street Complete
- Evan: Next step is to implement into the check-in app
    - Jeremiah: launch at FOSDEM, like FourSquare at SXSW?? ;)
- Evan: FOSDEM: Social Web track again this year. Full day, up from half-day last year.
    - Part of Open Source Week: https://opensourceweek.eu/
    - Live streamed, so anyone can join
    - Evan, Jeremiah attending

- Mike: What impact will the proposed Working Group have on this task force?
    - Evan: Proposed at the end of summer, went into review, had much community feedback. Goal was to have ready by TPAC (W3C's invite-only convention), but that didn't happen.
    - There are waiting periods for comment as standard W3C policy. Public feedback period ended January 6, 2026. It's meant to be a time for formal objection collection.
    - Public announcement of outcome expected soon. Working group status/next steps will be discussed if/when approved.
- Mike: Would this group supercede the community group?
    - Evan: There is a common W3C practice for community+working groups
    - Staged process:
        - https://swicg.github.io/potential-charters/stage-process
        - Ideas come in from community group, discussed in a task force, then be raised to working group for formal action
- Evan: Goal for him would be to maintain backwards compatibility and address known issues and areas of clarification.
    - For geosocial, if we could get ~5 client implementations following the best practice guidance in the document, then the working group could put an official stamp on recommending
- Mike: So the community group sits alongside the working group? It doesn't "own" the community group.
    - Evan: Correct


## Upcoming events

- [FOSDEM 2026](https://fosdem.org/2026/), Jan 31–Feb 1
    - [Social web track](https://fosdem.org/2026/schedule/track/social-web/)
- Mike attending [PyCascades Vancouver](https://2026.pycascades.com/) and Atmosphere (AT Protocol) in March to advocate for interoperability


## Action items

- [Next meeting is on 2026-02-12](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20260212T130000/)
