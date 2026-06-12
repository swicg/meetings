# Remix Task Force 12 Jun 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
- Matthias Pfefferle <acct:pfefferle@mastodon.social>

## Agenda

- Introductions/administrative

- Progress and implementation reports

- Issues:
  - #1 Followable list of actors
  - #2 Follow a hashtag

- Add comments below to modify or add to the agenda.

## Notes

- Code of conduct: https://www.w3.org/policies/code-of-conduct/
- CLA https://www.w3.org/community/about/process/cla/

- Introductions:
  - EP is solo (?) lead on this tf, BW may participate in the future
  - Ted Thibodeau of OpenLink Software, Virtuoso, contributions to specifications for clarity
  - Matthias Pfefferle, WordPress, remixing and aggregation are part of the blogging experience
  - TT: long relationship with WP, including remixes, license terms ("copy with attribution")
  - EP: AP plugin for WP has an aggregation aspect, aggregating all authors into a blog actor

  - Proposal discussion: https://github.com/swicg/meetings/blob/main/2025-06-13/README.md#proposal-remixing-and-aggregation-tf
   - "The idea of the TF would be to investigate the concept of remix/aggregate, and how to best share it."

- Implementations
  - surf.social (Flipboard)
  - channel.org (Newsmast) hashtags, authors
  - Collections or Starter Packs in Mastodon (?)

- User story:
    - https://github.com/swicg/activitypub-remix/issues/1  "As an ActivityPub user, I would like to follow a list of actors, so that I don't have to find and follow them all separately."
    - WP aggregation of authors on a blog into a "blog feed" or "blog actor"
   - Starter packs for Mastodon
   - TT: I usually want to follow the activity of every member of the list, not the activity of the list itself (the list is not an actor, it is an acted-on) — or in some cases, I *may* want to follow the list itself (additions, subtractions, *reasons* for those, etc.)
   - List in Mastodon: the creator of the list can view activities of all actors in the list, but cannot share the list with other users
   - X.com: can create lists of users, and make them public (anyone can view and follow (?)), or private (only creator can view)
    - Bluesky: can make lists of users, public by default (is this distinct from a starter pack?)
    - Organizations that have a "brand" account that boosts or retweets or announces important posts by its org members (automatically?)
    - Server actor, such as a Mastodon server, that can be followed to share all public content from users on that server
        - How can you tell which actors are being aggregated?
        - WP: aggregation actor (blog actor) is a `Group`, and members of the group (who is being aggregated) are in `moderators`
        - TT: Similar functionality in LJ and DW: "friends list" = aggregation of personal lists, "public friends lists" = aggregation available to the public
        - Yahoo! Pipes: aggregation and remixing and filtering service from Yahoo for RSS, maybe Atom? feeds
        - RSS feeds: "planets" concept
        - TT: OPML is another way to "export" RSS subscriptions, to move from one aggregation provider (or tool) to another, or to share your subscription list with others
        - type? `Group` or a new one?
        - property? `moderators` or a new one?
        - overlap with groups tf?
        - TT: Commentator, Curator, Moderator/Editor, Collector, Accumulator — all of these are different kinds of aggregation actions and/or aggregating actors
       - Is aggregation different from group membership, or do we treat them the same, same types and properties?
       - "As an ActivityPub user, I want to aggregate all my personal accounts into one account that my friends and family can follow."

- User story:
    - "As an ActivityPub user, I want to follow a hashtag, so if anyone posts using that hashtag, I can see it."
    - Mastodon: follow a hashtag locally (including remote content from other users, following lists, relays, replies, shares. ...), varies from server to server
    - X: follow a hashtag
    - TT: Where to follow the hashtag? Twitter, example. Hashtags can be overloaded by other users, like #odbc
    - WP: category RSS feeds, category actor? tag RSS feed?
    - https://tags.pub/ - ActivityPub global hashtag server, aggregates (using relays or other mechanisms) content from across the Fediverse, and has aggregator actor, so that #example posts are shared by example@tags.pub
    - https://relay.fedi.buzz/ Similar to tags.pub, but actor is tag-example@relay.fedi.buzz
    - Bluesky: follow a hashtag
    - Hashtag stuffing
    - TT: disaggregating

- 