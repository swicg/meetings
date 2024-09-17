# SocialCG Meeting 2024-06-07

link - https:// meet.jit.si/social-web-cg

## In attendance

* Dmitri Z
* [Johannes Ernst](https://j12t.org/)
* Julian Lam
* Aaron Gray
* Damon
* [TallTed](https://github.com/TallTed/) (he/him) ([OpenLink Software](https://www.openlinksw.com/))
* Ryan Barrett
* Bob Wyman
* a <trwnh.com>
* bumblefudge
* Matthias Pfefferle
* Tantek Çelik (https://tantek.com/)
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
   * AP Testing TF
5. (Johannes) FediTest / FDN results report out
6. (if time) Specs issue processing

## Minutes

### Introductions / Re-Introductions

n/a

### Announcements

DWeb Camp! https://dwebcamp.org/

### TF reports

#### HTTP Sig task force

Ryan: Brief update on HTTP Sig, last month was gathering more feedback from implementers; Mastodon took a look at it, said it looks good. Microblog; Matthias; Threads Security team.
More reviews from more implementers.

Evan: Last month, our agenda was to take HTTP Sig and WebFinger to CG Report status. We decided to hang back for a month, reached out to major implementers. It sounds like that work's been done? I wonder if there's anything else we need to do, before publishing the final reports. Are we ready to go?

PROPOSED: Publish the ActivityPub HTTP Signatures profile as a CG Final report.

(all +1s)

RESOLVED: Publish the ActivityPub HTTP Signatures profile as a CG Final report.

Evan: Now that we have this report, is there more work for the TF to do?

Ryan: We can disband for now.

Johannes: When are we going to upgrade this to newest HTTP Sig RFC? Makes a bad impression when we reference an old spec draft. Would be great to have a transition / upgrade plan?

Ryan: The report describes _how_ to upgrade. The herding cats part is out of scope.

Bob: Other than the goodness of being current on specs, what's the value of upgrading?

Evan: I'd like to try and answer Bob's question. One benefit is that the state of the art on using the 'security' namespace/ `@context` is falling behind (many of the terms are deprecated etc). Other thing I was thinking for the TF (if Nightpool & Ryan are willing) is -- coordinate with testing.

Ryan: Yeah, I think working with FediTest folks would be a great way to do it.

JE: useful to have some kind of roadmap that sets expectations for upgrading e.g. HTTP Signatures. This is the kind of thing that we can give some leadership on.

Evan: A roadmap is a big item. Another question is: Do we want to develop the next profile of HTTP Sig, that's based on the HTTP Sig RFC (Message Signatures)? Is that something that we as a group want to do?
Esp. since we describe the upgrade/backwards compat approach in the report? (I'm not trying to volunteer Ryan for this.) I'll phrase it as a proposal.

PROPOSED: The SocialCG create a next-generation profile of ActivityPub and HTTP Message Signatures including backwards-compatibility mode.

Evan: It's a lot of work; I'd rather folks discuss this than vote immediately.

Johannes: We should recruit more people for this group. (Maybe FLipboard, Meta, Ghost?). Invite people with specific asks.

Ryan: Another thing that'd be useful for us to do, is a similar report to the one we have, but for LD Sigs. (HTTP Sigs provide maybe 3/4 for what we need.) Inbox forwarding uses LD Sigs, etc. Would that be just as useful?

DZ: There's a good FEP on this already, https://w3id.org/fep/8b32 -- take a look and see if it's sufficient?

Evan: We can start this work w/o volunteer editors, and find volunteers? This'd be a continuation of the existing TF.

Ryan: Makes sense. Looks like a great proposal, but doesn't describe how it's done in the older style, currently.

Lisa D: I'd be interested in contributing, but not primary editor.

RESOLVED: The SocialCG create a next-generation profile of ActivityPub and HTTP Message Signatures including backwards-compatibility mode. [call for volunteers to edit and write the report]

#### Threaded Discussions/Forum TF

Julian: We had a great discussion on our monthly call yesterday; the Group Federation FEPs. We discovered through survey reports that's it's 2/3 FEP 1b12, and 1/3 FEP 400e.

a: asterisk on the 1b12 support. Some groups Announce, but don't follow 1b12, and just Announce the _object_ (instead of the activity). [more like 1/3, 1/3, 1/3]

Julian: Yeah, we want to discuss that - whether that's compliant / in spirit, or not.
Notes vs Articles: Almost everyone sends out Notes (due to Mastodon limitation); I'm going to reach out to Mastodon folks about this. We want the flexibility for each implementer to do what they want / address Mastodon's handling of Articles.

Use of `context` property in objects for threading. No consistent usage in implementers. We have an opportunity to set a standard. Using a _resolvable_ context for the purposes of context syncing.
Part of that is the discussion on how to extend parts of AP (to introduce a new property) -- what does that look like? Dmitri was on the call, reminded us of the Extension Policy report, etc. https://swicg.github.io/extensions-policy/

Evan: Yeah, we have that Extension Policy report in progress, we're trying to get it to final, that'd be a great place to start.

Johannes: Julian, what would you like to see from a testing perspective?

Julian: Testing would be great, of course. So far we were just researching how implementers are handling this now; we didn't want to step on toes. As we move forward, it would be good to keep FediTest in the loop. Our first step is to try and give recommendations for resolvable threading `context` property.

Johannes: This would be useful for the Fediverse in general, the question of "where did my reply go?". Do you see broader applicability to Fediverse?

Julian: Definitely (if implementers choose to support it). This is relevant for threaded conversations in general. This is what we mean by 'resolvable context', for syncing. We'll see if there's interest. I know there's a lot of emphasis of this being a push-based protocol, whereas this is a pull-based technique.

Tantek: I think the UI issues you're raising are interesting, worth documenting -- what are different implementations currently doing? Logged in vs not. The simplest possible unit is -- what happens when you're just looking at a reply on its own permalink? I'll drop a link to a place where the IndieWeb community gathers examples and UI brainstorming on Reply Contexts (IW name for it) https://indieweb.org/reply-context. Could be the entire reply chain, or short snippet. Lots of room to experiment. I'd love to see possible mockups / screenshots on this, documenting variance. The job of the protocol would be to support many different UIs

Julian: Right, understood.

Tantek: One quick approach to making a flat thread -- sort all replies in the reply tree to a post by time published.

Evan: AP is _not_ a Push-based protocol :) It really was designed to support BOTH push and pull (that's why the IDs are resolvable etc).

Julian: Got it, that was just my general impression initially, good to know.

a: Speaking of pull based mechanisms and 'where does the conversation live', we have two things - the `replies` collection, and the `context` property which COULD be an AS2 Collection. These are orthogonal, but could be related - you could sort `context` as flat by time, or construct a reply tree (purely inside or extending outside of the `context`), etc.

Julian: yeah, we're trying to approach this one small step at a time. Hopefully we can take small bites / small steps forward, define a recommendation. I'd love to work with both of those mechanisms (`context` and `replies`)

#### Account Portability TF

Lisa: I published a version of the LOLA proposal (Live Online Account Portability), would love more comments. Please review, add issues. https://swicg.github.io/activitypub-data-portability/lola.html
Take a look, tell us what's missing.

Evan: Lisa, I wanted to ask -- one great way to find out if it's a good spec is to implement it, see if it works. Do you think it's at a point where we can start soliciting implementations? Or does it need to cook some more.

Lisa: I think it's ready.

Bob: Is there a testing plan / strategy? A test server?

Lisa: It's more that existing implementations have to commit to it, so we can at least test portability between two different instances.

Bob: A Testing server would help here, would give a report card.

Tantek: A good way to frame it is - a call for implementer feedback (even if they just look at the spec, that's still useful)
+1 Bob's suggestion of a test server of some sort, it could not do anything in terms of UI, but would implement and test the protocol. (Round-tripping portability, did the migration come back exactly the way you left it, etc).

Lisa: Good point, it could be narrowly scoped just to the migration part.

Aaron: We can open an issue with Mastodon (asking for a review of the spec)

Emelia: I've already seen the LOLA draft (as a Mastodon implementer), gone through it, will look more.

a: To quickly interject, let's do a proposal on the WebFinger TF, lets do that?

Evan: Can you update us on status?

##### Request for comments - OAuth URI `client_id`s

Emelia: Quick note on OAuth things -- I am work with Aaron Parecki on an IETF draft (I-D) for Client Identifiers as URIs specifically for the Fediverse and decentralised OAuth use-cases; looking for reviewers:

https://drafts.aaronpk.com/draft-parecki-oauth-client-id-metadata-document/draft-parecki-oauth-client-id-metadata-document.html

#### WebFinger TF

a: We put the spec in front of implementers, Mastodon said "yep, that's how we do things", not much feedback from others. No outstanding issues.
The question came up of - should WebFinger be used to do MORE in the Fediverse (other than just link to actor); the report doesn't say much about that. If somebody was to propose something, we could add more to the report on these nebulous use cases.

Evan: I think all the issues on WebFinger have been cleared except one on testing; can we move it to the Testing TF?

a: Yes, let's do that. We can wrap up the TF (unless somebody requests otherwise).

Tantek: I appreciate we're documenting current implementation interoperability with WebFinger; I'd ask about any potential expansion beyond that -- whether that's a path we want to pursue. In the past, this group tended to pursue "follow your nose"(https://indieweb.org/follow_your_nose) style discovery (citation of resolution: https://www.w3.org/wiki/Socialwg/resolutions#Socialwg/2015-03-18-minutes), rather than continue building on WF.

a: Yes, I'm comfortable leaving the report as is right now, if some other proposal comes up, we can handle it then.

Tantek: Thanks.

PROPOSED: Publish the ActivityPub WebFinger profile as a CG Final report.
RESOLVED.

PROPOSAL: Wind down WebFinger TF (until further use cases etc)

Evan: One issue that I've seen, with implementers is the friction of learning JRD just for WebFinger. And one proposal I've seen is using a well-known URL instead of WebFinger. Anyways, I'm in favor of winding down the TF.

(all +1s so far)

RESOLVED: Wind down WebFinger TF

### Main Agenda

#### FediTest update

Johannes: Meeting recording at https://feditest.org/blog/2024-06-05-early-results-webfinger/
FediTest first draft WebFinger results -- we have a test matrix, the framework is working, we can report things: https://feditest.org/assets/2024-06-05/webfinger-server-all-wellknown-saas-imp.testmatrix.html
We have specific WebFinger tests identified, annotated, cross-linked etc.
We have some non-obvious results (like, people returning `application/json` instead of JRD/json), some gray areas. We're trying to be relatively nuanced about reporting it.

Evan: Just to check in, this is focused on WebFinger specifically, not WebFinger+AP?

Johannes: Yes, that was our starting point / low hanging fruit. We're looking at testing the AP-specific parts currently, like 'can App A follow App B?'

Evan: Yes, I was going to suggest testing against the WebFinger AP report.

Emelia: There could be some activities to test against, like the Reply activity...

Johannes: We absolutely welcome issues and PRs! (We're working on a v0.2 release of the framework, too)
