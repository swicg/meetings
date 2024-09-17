# August SocialCG Meeting 2024-08-02

Archived: https://www.w3.org/wiki/SocialCG/2024-08-02

https://meet.jit.si/social-web-cg

## Present

* Dmitri Zagidulin
* [Ted Thibodeau](https://github.com/TallTed) (he/him) (@TallTed@mastodon.social)
* Ryan Barrett
* Lisa Dusseault
* a
* AaronNGray
* Bob Wyman (@bobwyman@mastodon.social)
* Bumblefudge
* Johannes Ernst ([@j12t@j12t.social](https://j12t.social/@j12t))
* Tantek Çelik ([@tantek.com](https://tantek.com/))
* Steve Bate
* Emelia Smith

## Agenda

1. IP Protection Note Reminder:
  a. Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
  b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
4. Task Force Updates
   * Webfinger TF
   * HTTP Signatures TF
   * Portability TF
   * Forums and Threaded Discussions TF
   * End-to-End Encryption (E2EE) TF
   * AP Testing TF
5. Issue Processing
   * https://github.com/w3c/activitypub/issues/317 errata
   * https://github.com/w3c/activitypub/issues/297 errata
   * https://github.com/w3c/activitystreams/issues/444 errata
   * https://github.com/w3c/activitystreams/issues/445 errata
   * https://github.com/w3c/activitystreams/issues/448 errata
   * https://github.com/w3c/activitystreams/issues/482 errata
   * https://github.com/w3c/activitypub/issues/434 report
   * https://github.com/w3c/activitypub/issues/310 report
   * https://github.com/w3c/activitypub/issues/424 needs input

## Announcements

Sep 24-27, TPAC 2024 in Anaheim -- we should encourage implementers to attend! https://www.w3.org/events/tpac/2024/

## Minutes

### Task force updates

Lisa (updating on Portability TF): No updates, went to IETF though.  I owe scheduling another meeting to focus on it.

Evan: Question for Lisa, where do I send people to, Portability wise?

Lisa: LOLA document has been improved from comments from bumblefudge and others, so that's a good place to start. Now seeking implementer comments.

Evan: Ok, sounds like best contributions are comments/issues on LOLA doc. Are we at a point where implementation can start?

Lisa: I'm sure there's stuff missing, but we won't know until implementation starts. So, yes!

Evan (updating on E2EE): Over the last month, lots of activity in the E2EE sector / TF. We've done a big list of usecases, some addressing different architectural approaches, as well as integration options. Where we stand: Expectation that our next step is to layer an abstract E2E messaging protocol, on top of ActivityPub. Three major candidates: OpenPGP, Signal Protocol, and MLS (IETF).
https://github.com/swicg/activitypub-e2ee/blob/main/abstract-protocols.md

... Each has its pluses and minuses; there's a document in the TF repo (at Note level). We had a meeting last week, would like to have another one in August. Biggest contribution people can do is — comment on the user stories, review the abstract protocol doc.

... I have a grant (Summer of Protocols) for E2EE, hope to have a draft end of the summer.

a (updating from Forum TF): We spent yesterday discussing the use of Context, which has been implemented in at least Discourse and NodeBB, to indicate what conversation a post belongs to.  What gaps still exist, where do we go from here? Should it include Activities or Objects? The FEP it's based on is agnostic; it could go either way. I favour Objects in the context collection, Activities in the outbox collection.  Next, how do you verify something is in a Context collection?  Anybody can state that a message is part of a thread or topic. This is a problem that also exists with Replies — anybody can state that something is in ReplyTo, even if the reply is not accepted, and the way we deal with this is by looking at the replies collection.

Aaron: [missed this; volume too low]

... The [0391 FEP](https://codeberg.org/fediverse/fep/src/branch/main/fep/0391/fep-0391.md) has the concept of a stamp.  There's still a drawback that we don't know if something was later removed from a collection. I'd appreciate ideas and where to go from there.

Ryan (udpating on HTTPSig): We have some github stuff remaining? Dimitri has this on his plate...

Julian (updating on threaded discussions): Our conversation yesterday on context, I presented some of the work I've been doing. We will be doing a report or FEP on our findings.

Em: Tangentially applying to ActivityPub because we rely on OAuth; I presented [the OAuth draft](https://github.com/aaronpk/draft-parecki-oauth-client-id-metadata-document) I've been working on at IETF.

Evan: Noting that while the OAuth work is not technically a task force, it would be wonderful for that work to come in, and an OAuth profile for AP would be good for us to take on.

Em: Agree.

### Process question — "needs FEP" handling

Dimitri: We have a number of issues that we labeled "Needs FEP" because we think this would be good work outside the scope of the two main documents. Do we want to keep these open? I propose we close these issues and link to the (filter) list of "Needs FEP" issues.

Evan: There may be a few that need mentioning in a future version of the specs, but most are really about spinning off separate docs.  I agree they should be closed.

Em: There is also a tag "FEP written", maybe that's when we close these issues.

Evan: Same proposal, but also keep a "Needs FEP" master list issue open.

Em: Messaging is important, we need to make sure we're not giving people the message that this input wasn't wanted or is being ignored.

Lisa: "Yes and" to all the above (messaging is important).  I think there's no problem editing closed issues, e.g., to point to a FEP.  It's helpful to point people to where the work is being done, so they can create issues where those issues are most helpful, to modularize and direct work.

Dimitri: Yes, we'll communicate why we're closing these and include links in intros, etc.  That's the consensus so far. Ryan points out that a master list isn't necessary because there's a simple search URL that finds them all.  

Evan: Yeah, the master issue is nice to have in people's faces, and THAT can just contain the dynamic search link.

Dimitri: Would anybody like to maintain a list of FEPs in a sticky post? does that solve any remaining issues?

Evan: To clarify, I *DO* agree we should have an open list explaining where these went, with the dynamic link.

Dimitri: Resolution passed.

### Issue triage - issues requiring community input

Evan: I'm discussing these here because we have a responsibility to collectively decide, even if some of these seem trivial.

#### https://github.com/w3c/activitypub/issues/317 errata

This correctly identified a contradictory definition of the `liked` collection.  The erratum is already open: https://www.w3.org/wiki/ActivityPub_errata/Proposed

Brings into line with definitive version of spec language

PROPOSED: Accept erratum for issue 317, to standardize the definition of the `liked` collection.

(no objections)

RESOLVED: Accept erratum for issue 317, to standardize the definition of the `liked` collection.

(@evan PR needs to be created, wiki page needs to be updated move it from proposed to errata)

#### https://github.com/w3c/activitypub/issues/297 errata

Already accepted: https://www.w3.org/wiki/ActivityPub_errata

#### https://github.com/w3c/activitystreams/issues/444 errata

Errata is in a PR at https://github.com/w3c/activitystreams/pull/585.  

PROPOSED: Accept PR 585.  

(No objections)

RESOLVED: Add type to example as suggested.

#### https://github.com/w3c/activitystreams/issues/445 errata

Errata is in a PR at https://github.com/w3c/activitystreams/pull/590

PROPOSED: Accept PR 590.

(no objections)

RESOLVED: add missing Z to `startTime` example

#### Postponed issues

* https://github.com/w3c/activitystreams/issues/448 errata
* https://github.com/w3c/activitystreams/issues/482 errata
* https://github.com/w3c/activitypub/issues/434 report
* https://github.com/w3c/activitypub/issues/310 report
* https://github.com/w3c/activitypub/issues/424 needs input

### ```Rel=author``` topic revived from last Meeting

Tantek: we talked about having this in activitypub issue #310 (https://github.com/w3c/activitypub/issues/310).  I was able to easily implement it on my own site. It's easily publishable, technically compatible.  I'd like the group to offer opinions about it. The proposal is at https://github.com/mastodon/mastodon/pull/30398#issuecomment-2205071362.

Em: The Mastodon server needs to mark the domain as one that can trend. They wanted a custom attribute because they wanted a fediverse interaction, rather than just a links page.

Tantek: I think the implementation targets that exact use case, but using the `rel=author` attribute and saying specifically this is an Actor that can be followed with ActivityPub. I think it communicates the same information as the `Meta` tag, but with a special use of an existing standard.  If there's no objections, let's say this is a good idea and we agree with this proposal.

Em: It's an in-development feature, not widely available.  They (mastodon) have certain needs that they needed to have met, with large publishers in mind, not so much the individual blog owner or person maintaining their own blog.

Tantek: I think the proposal in the PR satisfies those constraints.

Em: I would agree.

Evan: This is an interesting and important question: given an HTML page, what object is this in the Fediverse, and also what's the representation of that object in the Fediverse? This seems right in the wheelhouse. Should it be a Task Force?

Tantek: I think there's a level of urgency to respond to this one-off OGP thing, ask folks to switch to the `link rel`, same place they would have put the `meta` tag, and save the world from one more one-off `meta` tag.

Em: `Meta` tags sometimes are author/editor controllable within the software, whereas `link` tags may not be. Big CMS like TechCrunch might already be using editable `meta` tags. Maybe that's why `meta` tag is used?  Not to diminish the `link` tag, but we may not have all the context of why this is chosen.

Tantek: I agree there may be additional information, but given the information that we know today, can we reach a decision? As usual, if somebody provides new information, we can reopen the discussion.  Note that the `href` must be the Profile link, we don't get to control what goes in that.

Em: When discovering and resolving the Actor behind that URL, are we saying that one uses WebFinger (and `.well-known`) to find out what that is, rather than parsing the URL?  We'd say that whatever the `href` value in the `link` tag is, you follow that, and how do you determine it's an Actor?

Evan: Proposal 1: We prefer the use of `link rel=author` to identify authors of Web resources;  Proposal 2: task force on discovery.
  
Tantek: To build on Evan's first proposal, I'd also add use of the link with type `application/activity+json`, to indicate that the resource "supports" ActivityPub, left vague in order to support Em's suggestion.

PROPOSAL: We prefer the use of rel=author for identifying authors of web resources.

PROPOSAL: that proposal + `type=application/activity+json` means that the `href` supports ActivityPub discovery and following (modulo open question about which specific discovery mechanisms)

PROPOSAL: Open a task force to focus on a discovery of ActivityPub actors and objects from HTML.

All 3 RESOLVED

Tantek will take the task of adding to the rel-author spec so people can start, and we can gather more data about specific resolution.

Emelia: On tantek's proposal, I'm a +0, in that I would want that open question resolved
