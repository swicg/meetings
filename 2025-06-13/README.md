# June SocialCG Meeting 2025-06-13

SocialCG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Zagidulin
* Johannes Ernst https://j12t.org
* nigini https://nigini.me
* [TallTed // Ted Thibodeau Jr](https://github.com/TallTed) (he/him) [mastodon:@TallTed](https://mastodon.social/@TallTed) (OpenLinkSw.com)
* theia
* a <trwnh.com>
* Bob Wyman
* Tantek Çelik [@tantek.com](https://tantek.com/)

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
5. Task Force Updates
6. Touch base on WG charter
7. FediForum report out
8. (Proposal) Remixing and Aggregation TF
  > From Evan P.:
  > I think this is an interesting enough pattern that we should open up a Task Force at the SocialCG to investigate standardizing some of these features. Important questions to ask are:

> * How should an aggregated feed appear on the Fediverse? Is it just another Actor that Announces activities and content that meet its requirements? Or is there another structure?
> * How do we handle ordering of feeds? Some feeds might not be reverse chronologically ordered, but use some other algorithmic ordering.
> * How can feeds be transparent about what the sources are? Actors, search terms, hashtags, etc. What is coming into this feed? Can consumers inspect the sources?
> * Is the feed replicable elsewhere?

## Announcements

(Evan)
1. https://FediCon.ca in Vancouver Aug 1 & 2
2. HOPE (Hackers On Planet Earth) Fediverse Village https://hope.net Queens NY, Aug 15-17th

(Johannes)
3. #FediForumFriday: update the community on your progress on projects discussed at FediForum: https://bushnellcommunitysolutions.com/fedi-forum-friday/


## Introductions and Reintroductions
none

## Task Force Updates

(Evan)
E2EE TF: https://swicg.github.io/activitypub-e2ee/
https://swicg.github.io/activitypub-e2ee/mls
Pre-draft draft of "MLS over AP" messages
Please review and comment. Looking for experimental implementations!
Time to start regular monthly meetings for the E2EE TF.

(Johannes)
WebSite TF:
Had our first meeting yesterday. We have repo write access to ActivityPub.rocks website. We put together a rough plan/outline (in the README).
It's a static site; github issues -> PRs -> automatic deploys
We welcome GH Issues and PRs!

(Evan)
other update - HTML Discovery TF (for identifying and defining finding an AP object from HTML doc and vice versa, also identifying authors of a doc as AP actors)
https://swicg.github.io/activitypub-html-discovery/
We want to encourage more inter-linking between HTML and AP, esp in the "Best Practices for Publishers".
Would love to take this to a draft CG report in the next month, since it's been incubating for a few months.

(Johannes)
We should add a list of current TFs to the website.

## Main Items

### WG Charter Updates

PLH: Diff: https://services.w3.org/htmldiff?doc1=https://swicg.github.io/potential-charters/social-web-wg-charter.html&doc2=https://w3c.github.io/charter-drafts/2025/social-wg.html (between what the CG submitted and the current charter)

Scope section: we used to have a 'no class 4 changes' clause, PLH removed it (since the line between adding it in a new spec and an existing spec is fuzzy). All items are already subject to CG Staging Process anyway.

2 changes to Tentative Deliverables: 1) explicitly added LOLA report to the list of Tenative Deliverables. 2) Add a sentence to be explicit - WG is expected to follow CG Proposal stages!

Section 3.1, one of the fields is 'expected completion' - hard to predict the future of course, so no worries.

Section 4 (Success Criteria) - we recently approved the Privacy Principles document, as a Consortium, so we're adding that to this Charter.

Added SWICG to "Groups to be coordinated with". (Shifted from Section 5.1)

No extra organizations at the moment in the coord section.

Section 6 - another change from the Charter Template, need to look at the level of contribution from the outside the WG, consider inviting them as Invited Experts. (An encouragement, to be welcoming.)

Section 7 - we're using both the mailing list and GH issues as channels for technical contributions.

Section 8 - currently, decision period is 1 week.

Section 11.1 - linking to the old WG charter, for history.

PLH: Horizontal review of charter started.

Evan: what's our realistic timeframe to kick off the WG?

PLH: mid-September.
Also, TPAC is in November 10-14 - will the WG want to meet at TPAC? (Need an answer by Jun 20th).

Evan: we've met as the CG at TPAC for the last few years. Makes a TON of sense to meet as a WG.

https://github.com/w3c/tpac2025-meetings/issues/25

### (Proposal) Remixing and Aggregation TF

Evan: We've seen a number of new features and services launching recently, having to do with aggregating and remixing feeds. Surf, Channel.org from Newsmast. There's interest in illustrating/declaring the "recipe" of what went into the feed. (accounts, hashtags, algorithm). So that it can be reused, forked, and son on. The idea of the TF would be to investigate the concept of remix/aggregate, and how to best share it.

Johannes: Did I hear right that the Flipboard people would be interested in participating in this?

Evan: Definitely, this is great opportunity to bring them in.

Bob W: Wherever there's aggregation, there's always the demand to select subsets of aggregation. Which begins to sound like Search (which is still sensitive issues in the community)

Theia: also relevant as a feed aggregator/filterer (also draws in from other protocols/apis):
https://gobo.social/
https://publicinfrastructure.org/2022/11/09/gobo-2-0-all-your-social-media-in-one-place/
 
Dmitri: Volunteers to lead? 

Evan: I'd love to co-lead with Bob.

Bob: OK.

### Other

a: I want to bring up the issue of Protocols from earlier. https://lists.w3.org/Archives/Public/public-swicg/2024Nov/0010.html
(infamous "Chess Protocol") how do you know if a recipient supports a given activity?
I know this has been out of people's minds for a while, but I wanted to bring it up again.

Evan: AP was designed to be very general purpose, for any sort of activities through the networks. It's up to clients to decide what, if anything, to do with an activity (ignore it, etc). I'm concerned about segmenting the network into fragments (this is micro-blogging, this is chess, etc).

Tantek: There's some experience here we can draw from. I would separate some of the thinking here -- a server talking to another random (untrusted/unfamiliar) server, vs when there's familiarity between two endpoints. 
One of the most well-implemented Micropub extensions is roughly "what posts do you support?" - has allowed for richer/ more dependable client interactions with servers, since users choose both their clients and their server(s) and thus have agency to make them work well together (which is not the case with server-to-server). For server-to-server, the straw proposal is to always use plain text in the "summary" as the universal fallback for any new posts / activity types so that all servers can do something with it. (Also touches on the subject of Summary field being used mostly for Content Warning).

a: I'm more interested in behaviors / what to do with an activity.

Evan: could we expand the scope to -- explore how we build classes of apps on AP?

Tantek: I think the proposal from 'a' is specific enough that it might be better as an AP issue, rather than restarting a discussion on the mailing list.



