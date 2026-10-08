# Geosocial Task Force, 2026-06-11

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Jeremiah Lee, [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah) (he|they)
- Mike Waggoner @herebox@social.coop
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

- Review [previous minutes](https://hedgedoc.socialweb.coop/qWFxbFVJRm-nz1HFmXMWVA)
- Review [PR 31: Geosocial Microsyntax](https://github.com/swicg/geosocial/pull/31)

## Minutes

### PR 31: Geosocial Microsyntax

- Evan: Microsyntax: small win that can be used now without requiring server adoption
- When considering options, we removed commercial
- Settled on 2 different syntaxes:
    - Plus Codes / Open Geo Code
        - Lat/long doesn't identify places within a human vocabulary (e.g., which cafe?)
    - Open Street Map identifies
        - Distinctive, concise format
        - Precision of location — an actual space, not just a location
        - Also not in human vocabulary, but can be expanded to it
- Other options considered for less pre-processing:
    - Considered `L:` prefix, but no closing indicator
    - Geoslash: `/Slash/` allows for delimiting
    - Both have specificity problem (`/Berlin/` in DE, or Cafe Berlin in San Juan?)
- Mike: Adding reference to the explainer
- Evan & Mike: Next step is to start using it and trying it out
    - Mike: First implementation, just use it in a post
    - Jeremiah: Can we add the regex to docs?
    - Evan: One idea is to use relays/public-feeds and put people's heads on a map as they use it.
    - Evan: https://fediversemap.com/ shows servers, not people
        - Jeremiah: Maybe uses https://globe.gl/
            - Nope: https://maplibre.org/
- Mike: What about #hastagLocations?
    - Evan: Should we 'pave the cowpaths' (*à la* Tantek)? It's something people already do or have done.
    - Mike: No obvious reason to avoid using hashtags.
    - Evan: Recently worked on a [hashtag server](https://tags.pub/) to follow a hashtag across servers. An individual's Mastodon community server will only show the posts that the server has encountered, not a global view. This boosts posts and uses server and relay feeds. Opt-in from users, servers, and relays. ~6000 servers so far.
        - Jeremiah: Could Tags.pub be adapted to do regex for the other microsyntaxes?
            - Evan: Yes, it's possible.
- Evan: Maybe Ben Pate interest? He made the [Atlas demo](https://atlasdemo.emissary.social/home)
    - Jeremiah: [Looks like it uses](https://browser.pub/https://atlasdemo.emissary.social/6904320ba4d4eabea70d531e) `location` object
- Evan: Terence Eden been posting [Swarm checkins](https://mastodon.social/@Edent/116730711941462905)
    - Jeremiah: [asked him for more info](https://alpaca.gold/@Jeremiah/116732704999237765)
    - Evan: We should invite and ask him to join next meeting.
    - Mike: He wrote a [blog post](https://shkspr.mobi/blog/2024/02/a-tiny-incomplete-single-user-write-only-activitypub-server-in-php/) and made proof of concept in the past
- Mike: Merging PR 31 - Completed


## Action items

- [Next meeting is on 2026-07-09](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20260709T130000/)
- EP: I'd like to try making a map interface for tags.pub
- Invite guest speakers
- Jeremiah: Meeting notes into https://github.com/swicg/meetings
