# March SocialCG Meeting 2025-03-07

SocialWG on Fedi: https://w3c.social/@socialcg

Archived: https://www.w3.org/wiki/SocialCG/2025-03-07

## Present

* Dmitri Zagidulin
* [Johannes Ernst](https://j12.org/)
* [Jeremiah Lee](https://alpaca.gold/@Jeremiah) 
* Emelia Smith (https://hachyderm.io/@thisismissem)
* [Darius Kazemi](https://friend.camp/@darius)
* [Ted Han](http://an.errant.cloud/@ted)
* [Lisa Dusseault](https://mastodon.geekery.org/@lisarue)
* [Ryan Barrett](https://snarfed.org/)
* a <trwnh.com>
* Alex Kulikov (@alexeyqu@mastodon.social)
* Tantek Çelik (https://tantek.com/)
* [TallTed // Ted Thibodeau](https://github.com/TallTed/) (he/him) (OpenLinkSw.com) (https://mastodon.social/@TallTed)


# Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
4. Task Force Updates
5. Review - Adopted Social Web CG Charter
    * Chair Election clarifications (revert to boilerplate, add ranked choice election)
7. ActivityPub 1.1 Working Group Charter Planning and Discussion
8. [W3C 2025 Breakout Day](https://www.w3.org/2025/03/breakouts-day-2025/)
    * Evan's proposal: https://github.com/w3c/breakouts-day-2025/issues/4

# Minutes

## Intros

Ted Han - Formerly Mozilla product/eng, worked on Mozilla Social

## Community Announcements

* [FediForum](https://fediforum.org/) is coming up - April 1-2

* [IIW](https://internetidentityworkshop.com/) in April 8-10

* Fediverse Schema Observatory - invite link for Social Web CG participants: https://observatory.cyber.harvard.edu/login?code=swicghello

### Other Events

* SXSW Fediverse House this weekend - Evan will be there
* W3C Breakouts Day coming up: https://github.com/w3c/breakouts-day-2025/blob/main/README.md

## Task Force Updates

### Signatures

Ryan Barrett: Mastodon announced last month that they're planning on supporting the latest RFC of HTTP Signatures (upgrade from the Cavage draft)

Emelia: Same with Fedify. Double-knocking is when the message gets signed by the old cabbage draft approach if the new approach doesn't work. Code for implementing this can be separated from the rest of the implementation, so this might become a useful library. Motivation came from Fediscovery work not using OAuth and instead use the signatures if updated to standard.

### Threads

A: there are a handful of projects publishing and consuming threads. We worked on priority sorting. See [notes]( https://community.nodebb.org/topic/18689/minutes-from-6-march-2025-wg-meeting). Top priority is backfilling context, so a newcomer to a thread can catch up.  Then forking conversation.

Emelia: For forking, will there be a link back to the original collection? That doesn't currently seem to be there yet

A: We haven't finalized any protocol yet; we're defining what we'd like to see at this point.  We're building a better idea of what a thread looks like and what goes in there.

Emelia: I was thinking cloning collections could be useful? Somebody copies your list and they have all the same items, but the original creator knows it has been copied.

### T&S

Emelia: Not much progress to report, but we're trying to still make progress. One issue comment that may interest some is on the Content Warnings topic:

Emelia: https://github.com/swicg/activitypub-trust-and-safety/issues/1#issuecomment-2698559515

### [Geosocial](https://github.com/swicg/geosocial)

Jeremiah: Mike is working on first draft of explainer. Still collecting use cases. Next meeting on [Thursday, March 13, 2025](https://www.w3.org/events/meetings/ed630a3d-7581-4053-9978-75949ad42f2a/20250313T130000/).

### Data portability

Lisa: Not much to report; we're waiting for [LOLA](https://swicg.github.io/activitypub-data-portability/lola.html) to make it to the front of implementor backlogs then surely we'll hear more about it.

Dmitri: Also note the work on cryptographically identifying moved content (FEP) — no recent progress but still exists.


## Main Agenda

### CG Charter 

Dmitri: In our last call, we had a proposal to accept the community group charter. We had some requests for changes to the chair selection process so those changes are in progress — two PRs pending: [PR#66](https://github.com/swicg/potential-charters/pull/66) and [PR#67](https://github.com/swicg/potential-charters/pull/67).

Emelia: The new language seems pretty loose — CG can use whatever process they can prefer? What we had before laid out an actual process to avoid confusion.

Dmitri: We can certainly tighten this up.

Emelia: A recent change removed some stuff that we had agreed to.

Dmitri: We agreed to adopt everything but the chair selection in the last meeting.  Loose as it is, the charter is enough for a CG historically within the W3C.

Johannes: We've spent a lot of time on chartering the CG. We have other things to do. There doesn't actually seem to be much objection. Why are we spending so much time?

Dmitri: Because if we're spinning up a WG, as well as a CG, we want good relationships between those, so it complicates the governance of the CG somewhat.

Tantek: So do we have an overall approved charter and also a chair selection section that has consensus? 

Dmitri: Let's find out. Does anybody have strong objections?

Emelia: I think we should not go with the results of the PR, nor the removal of that whole PR, which would take us back a step, but to actually have better language.

Dmitri: I agree with you on the goal but not the approach; we can iterate on the "code" of the charter as engineering teams do.

Darius: +1 to Johannes, I'd like us to be able to discuss technical things.

Dmitri: The Task Forces are where lots of technical work gets done and continues to get done anyway, not just these meetings.

_Call for consensus_: are there objections adopting the PRs for the CG charter? No, with caveat that no election takes place until election process is clarified 

### WG Charter

Dmitri: For the WG charter, we have two distinctly different approaches to consider: narrower and broader scope. The CG charter meanwhile has a staging process that allows work to be bumped up to the WG. Any discussion before we dive into the detail of the WG charter options?

- https://swicg.github.io/potential-charters/stage-process
- https://github.com/swicg/potential-charters

We have the most consensus for building ActivityPub 1.1.

Emelia: Once we have consensus, can we move these into an official place? On ActivityPub 1.1, it's more of a SWICG 1.1 — only addressing amendments and adjustments that need to be made to the group's original deliverables. A wider tent, full-on, would possibly open us up to trying to write ActivityPub 2.0, which I don't think is necessarily the right focus right now. Even if it's two WGs, one after the other, 1.1 should come first. We should focus on errata and republish first. 

Tantek (chat): None of the proposed WG charters had scope for an AP2.0 so that's not actually on the table. The "wider tent" charter was exactly what Emelia said: incorporate errata on all Social WG specs and then iterate.

Dmitri: We probably won't be able to come to consensus on the two charters in the next 20 minutes, but our goal is to do this work in the next month on the usual asynch channels. Let's lay out the topics, and discuss and vote on them during the month. We'll look for the most consensus and adoption (having editor volunteers is important).

Tantek: +1. Volunteer editors are important. That said, errata can still be included in a charter even if we don't have a volunteer to edit — we may attract a volunteer if it's a real WG and a real deliverable.  My understanding of the "big tent" metaphor is that it's about the set of deliverables rather than what class of changes to allow in specifications — topic breadth rather than change impact. I think both charters are more about errata than about new stuff.

One of the charters had more up-votes and conversation than the other, and I would take that as an indicator of consensus.
* [Initial Social Web Maint WG charter template](https://github.com/swicg/potential-charters/pull/3): 6 upvotes
* [Initial ActivityPub Maint WG charter template](https://github.com/swicg/potential-charters/pull/2): 2 upvote

Dmitri: With the staging process, we absolutely can include errata or notes by including in the charter, regardless of what makes it through the staging process. So we don't have to have editor volunteers in advance.

Emelia: I'd like the number of errata and number of volunteer editors available as data to make the decision, as an indicator of folks implementing and running into issues. Issue count is a rough proxy for implementor interest.

Dmitri (chat): Previous deliverables listed here: https://swicg.github.io/potential-charters/social-web-maintenance-wg-charter.html

Tantek (chat): https://www.w3.org/wiki/SocialCG/WG_Charter_Discussion#Deliverables

Tantek: I can update that table with columns for number of issue and errata. I count issues for the repos. I don't know a methodology for counting errata so perhaps other folks can fill those out.

Emelia: Counting errata could be literally counting bullet points.

Philippe: I could update these to include tentative deliverables if that would be helpful. Also reminder I'd like to see charters in April... will officially propose something at W3C level then anyway.

[Philippe is a [W3C Strategy & Project lead](https://www.w3.org/People/LeHegaret/)]

Dmitri: Let's add another live discussion in two weeks on charter. We want to have a charter in April.  This is both high stakes and low stakes, because as long as we have something, it's better than nothing.

Emelia: I think the next step's here — the assessment of deliverables at the next call 

A: You say this is low stakes; who are the stake holders?

Tantek: My own opinion is that the more stakeholders we can include that implement these specs, the more we can get done technically in our work. That's a bias I recommend bringing in. 

Dmitri: I want to push back on that — after a point, the wider the scope, the less likely to successfully make the deliverables. We want to find a sweet spot. The wider focus of the CG allows us to still have more involvement and work and still a narrower focus in the WG.

Emelia: IndieAuth? Can we publish it for real? Wider tent?

Tantek: It's a Note currently in the prior deliverables, but we could shift it to being REC-track with proper Working Drafts, CRs, test suite, etc.

