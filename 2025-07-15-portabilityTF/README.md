# Data PortabilitY Task Force Call 2025-07-15

## Attendees

* Lisa D.
* Dmitri Z.
* Ted Thibodeau Jr (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
* bumblefudge

## Agenda

* Issue review?
* Implementor progress
* Coordination — main readme pages, drafts listed in one place
* [if time allows] report out from a Mastodon.social-->GTS migration
    * used the new [slurp CLI](https://github.com/VyrCossont/slurp) — mostly "one shots" (within the scope described by erin kissane!)
    * interesting design decisions and [post-migration UX](https://codeberg.org/superseriousbusiness/gotosocial/issues/2) 
* Hollo identifiers for packing

## Minutes

### Coordination/discovery pages

* multiple landing pages/URLs with SEO
    * https://www.w3.org/community/socialcg/ (generated by w3 tooling automatically; populates list of deliverables when finalized)
    * https://github.com/swicg/activitypub-data-portability
    * https://github.com/swicg

TODOs:

* Lisa will Add LOLA link and the data export format draft to `/activitypub-data-portability/README.md` — change the page text to reflect where we think this is actually going — the "Latest editor's draft" we can describe as an anchoring document about the scope of the TF
  * Lisa will describe the "Latest editor's draft" as a _report_ — a descriptive map of current situation
  * BF opened a PR on this already actually during a lull in the meeting 
* Dmitri will update the pinned post at the w3's community page to point to the portability TF page that Lisa's updating
  * done on the call

### LOLA issue review

- Emelia's OAuth qualms
    - Client Secrets p common, non?
    - Dima: YES, for "secure clients", but dynamically-registered clients, SPAs, etc,
        - Lisa: but the text in question (lola.html ~ll.576-583 in current draft) just mentions manually-copying-over client secret as one option;
        - Lisa: if we want people passing PRIVATE data between servers, couldn't we maybe use S2S keys/HTTPSigs, etc? use DPOP to authN that key, maybe? 
        - Dima: seems reasonable, not knowing Mastodon's key handling offhand 
    - TODO — Lisa will follow up with Emelia about what is likely/possible/probable/best for Mastodon's OAuth

- Other random issues — closed https://github.com/swicg/activitypub-data-portability/issues/30 for example as we're going to use the README.md in the github activitypub-data-portability repo to direct/inform folks about active work and available drafts

### Slurp, GotoSocial, export/import tool

* Requires the Mastodon client interface or compatible
    * Imports specific TO GTS API only; imports Mastodon and Pixelfed exports
* Interesting promising work — clearly still in-progress (some killer errors known)
* Looks very useful for some use cases that aren't just "moving account from server A to server B"
    * e.g., ability to synchronize follows between two accounts that aren't otherwise synched
* Copied-over posts aren't federated — server doesn't "understand" imported/backdated data or link to previous URL
* We compared this approach to S2S
    * Definitely complementary and interesting and useful!
    * We still think the S2S features that are enabled when the server KNOWS that an account migration is happening, are important. That includes back-dating posts, knowing that they were already published, keeping breadcrumbs of what a post was previously known as, and providing a path to fix up follows and likes in both directions.
        * is there a previousURL property or is a FEP needed for clients to know how to display migrated posts? Consider using PROV-O attribute?

### Export/Import Formats

- One simmering issue/design debate: portable/location-independent identifiers for
    - [RFC 6920](https://www.rfc-editor.org/rfc/rfc6920.html) for example 
    - emelia's issue: Mastodon uses UUIDv7 (snowflake-like sortable timestamped UUID);
    - dima: UUIDv8 is also content-hashed AND timestamp-prepended for sorting
    - lisa: reminds me of email WGs at IETF having the same problem with syncing across two servers with diff UIDs — does client have to know multiple UIDs?