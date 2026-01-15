# October SocialCG Meeting 2025-10-03

SocialCG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Zagidulin
* Lisa Dusseault (@lisarue@mastodon.geekery.org)
* [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
* Darius Kazemi
* Evan Prodromou <web+acct:evanp@socialwebfoundation.org>
* plh
* Tantek Çelik (@tantek.com)

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
4. Task Force Updates
5. Charter updates if relevant.
6. Main Agenda
    - TPAC


## Minutes
 - Evan will take point on an IETF Montreal meetup for the CG
 - Should be a CG/WG session at TPAC

### Announcements

- IIW coming up week of Oct 20th
- FediForum is Oct 7th and 8th!
- IndieWebCamp Berlin Nov 1st & 2nd at Mozilla Berlin office. Everyone is welcome! https://indieweb.org/2025/Berlin

### TF Updates
- Portability task force
    - Quiet task force, waiting for implementers to find issues. Ben Pate of Bandwagon.fm, an AP music discovery service, is implementing LOLA. Our DTI engineer, Aarón, is implementing LOLA in a testbed implementation.
- ActivityPub API
    - Repository set up with user stories at https://github.com/swicg/activitypub-api/issues
    - Need to gauge interest for meeting cadence, or for meetings at all
    - Dmitri: what's the scope of the TF?
    - Emelia: it's called ActivityPub API. We do need to update the readme with scope of work. We need a way to do auth from client to server; that needs to be figured out. We need APIs for things that apps commonly need to do like uploading media, filtering collections. The sorts of things that a PDS-like thing for ActivityPub would need. There's a discussion point in there about identity in and of itself, like bringing a domain to a service with identity resolution involved. Whether that's webfinger or something else, there are some options there. To make it possible to do functional and semi-fast client to server. If you look at the [article by Dan Abramov on social apps](https://overreacted.io/open-social/) it provides a good baseline to see where ActivityPub API could fit in a larger ecosystem
    - https://overreacted.io/open-social/
    - Evan: here are the minutes where we talked about scope last month: https://github.com/swicg/meetings/blob/main/2025-09-05/README.md#activitypub-api--oauth and we should consider these enumerated tasks to be in scope
- Trust & Safety
    - Didn't meet, possibly still calendar confusion, no one turned up
- 

## Main Agenda

- Working Group charter
    - We passed consensus in Sep after email list CfC
    - plh: I have two changes to make to the charter. I'm assuming both are uncontroversial, but if I'm wrong we should do a new CfC. We had received a comment from TAG to the coordination section. It was a bit lightweight for them. https://github.com/w3c/charter-drafts/pull/699
    - plh: there is prior coordination around `alsoKnownAs` with the DID group so we need to note that. There should be coordination listed with HTTP and IndieWeb. Another possible thing is to note coordination with the FEP community (via CG)
    - evan: for this consultation or coordination, does that require affirmative assent?
        - plh: no. best case scenario is they say "sure" and worst case is they don't answer at all and we time out after a period of six weeks. If they do answer with comments then we address them. having this in the charter would help us remember to look at a check list and be reminded, "Right we should inform these groups about these changes"
    - plh: the other change is less substantive. The TAG commented to say "there should have been an explainer", which is a document you're supposed to have when you request review from TAG. We will need to do an Explainer when it's time for horizontal review from TAG. The Charter is also missing an "Other Deliverables" sections. Usually we have that section that says "other non-normative cases like tests suites, use cases, etc may be included." That might also be a place to put an Explainer https://github.com/w3c/charter-drafts/pull/700
    - Emelia: on the additional documents, how much emphasis is there on the Chair of the WG to review all the additional documents?
        - plh: it's up to WG discretion. Whether it's listed in the charter or not doesn't change your ability to do it, since it's a MAY in the charter. If we are afraid Darius will forget such a list, I wouldn't suggest other forms of wording in the charter. If we believe we really don't need use cases, primers, best practices, we can remove those
        - Emelia: I'm concerned by the WG being tied up reviewing additonal documents that aren't the real focus of the WG
        - plh: Test implementation report and Explainer are going to be required for horizontal review no matter what, though.
    - plh: I'm giving this to TAG because they gave us comments at the end of July. They said "we should be specific that the charter lets us do major changes and 'maintain' is too vague" but I think the vagueness is helpful and lets us do all sorts of things that we need to get done. There is no "out of scope" section because I don't want to clarify that. If it's not prohibited, then it's allowed.
    - plh: nowadays if you push a document forward, you are expected to have security considerations, privacy consideration sections in a document. It's needed to pass horizontal review.
    - Emelia: is there a process document we can just link to?
        - plh: we already link to the guidebook about wide review, so... again, the more explicit we become in the charter the more it triggers questions like what about the other charters that didn't say anything.
    - plh: they say that while the charter focuses on maintaining prior work, what if it includes future work and a tentative deliverable? we do have LOLA as a tentative deliverable, but not anything else. 
    - emelia: I think there are documents that should be lifted up to be standard documents, like the document on HTTP Signatures, that could be included alongside LOLA.
    - Dmitri: we don't want too much scope creep and delays. it's been hard enough to get consensus for this narrow scope.
    - evan: we had long discussions about what was going to be in and out of scope, and there was a lot of concern from different factions about it.
        - plh: this is why I didn't write a PR, I just didn't want to touch that section
    - evan: HTTP signatures report is already an official report though
    - Emelia: it's not normatively included in the AP spec; we should link to these from a future spec
    - Dmitri: in a non-normative section we can do that
    - Dmitri: philippe, do we need to reply to those issues?
    - plh: no I gave the reply now that I've gotten feedback from you all. We do need to put out another CfC for these changes
    - Action item, Darius: CFC to SWICG list, link to the two PRs (699 and 700), link this comment too https://github.com/w3c/strategy/issues/435#issuecomment-3366604190

- TPAC
    - Evan: will we be meeting as a WG or not? is there a path where this charter is approved by TPAC?
    - plh: Given the new CFC, we will be in review during TPAC. You'll have a reserved room as a CG, so you can do the work, but you won't be meeting as a WG in name.
    - Emelia: just to double clarify, there will not be a working group by the time of TPAC?
    - plh: correct
    - Darius: I can take point on TPAC events since I will be there in person
    - plh: I'll be the team contact for the WG. For TPAC, the main thing is coming up with an agenda for the meeting. Don't forget to remind people to register. We have an event in the calendar created. We just need to add links to an agenda. The room is set up with Zoom and it will be a pain to use something else.
    - plh: there is registration required for hybrid/remote people.
    - Action item: Dmitri & Darius draft an agenda, inform the CG that this is going to replace the usual monthly call
    - Dmitri: I think it should be the usual, introduction to the work if we get people from other groups. 
    - plh: another thing to talk about is maybe what happens between TPAC and publication of the next version of the AP spec, as Community Group that is starting to think as a nearly-real Working Group. Details about version numbers and that kind of thing.
    - Social Web meeting at TPAC: https://www.w3.org/events/meetings/5ce4d187-2916-4efc-9c22-5650e1794105/
    - Evan: I do want to say that looking at the ActivityPub repository, we have about 45 changes that are too big for Errata but are within scope for discussion. There's an equivalent ActivityStreams changes list and combing through to separate between a 1.1 and 2.0 is a good discussion topic.
 - Evan: We should also figure out when and where we have a fediverse meetup at TPAC, but we can figure that out on the list
 - Action item: Figure out the meetup

- Evan: inspired by this week's voluntary patent pledge from BlueSky. There is of course W3C IPR as well. The FEP portion of the community doesn't have the same IPR protections (copyright but not patent, etc). I wonder if we can have a process that brings certain FEPs under the CG's CLA as a kind of licensing process. It would be nice for us to do for the rest of the community and a show of good faith.
- Dmitri: That makes sense. We already have the pathway for that in our incubation stages document. We explicitly say FEPs -> CG -> WG, so the groundwork is there.
- Darius: are there other WGs or CGs that do something similar?
    - plh: the short answer is that people submit those proposals to the CG, and that would put them under the CLA. Now the CLA says you're only committed if it becomes part of a recommendation. We may not have a solution if it's not intended to become part of a recommendation and the authors would have to simply make their own IPR statement. Like sometimes we have documents submitted to CGs to make them easy to talk about without external worries.
    - evan: is there a standard wording we have for that, or does the author have to look it up themselves?
    - plh: author would have to look it up themselves.
    - evan: okay, I'm somewhat disappointed that putting things under our CLA is not a magic solution but it looks like there's a path forward.
    - evan: we did have an activitypub extensions repository suggestion from years ago. that might be the palce to put it.
    - dmitri: would a single repo for generic extensions make more sense or a separate repo for each one?
    - evan: maybe we bring the proposals in to the relevant task forces.
    - tantek: separate repo for each extension might be better? to allow different maintainers etc. no strong opinion to be clear.


## Action items

 - Action item: Dmitri & Darius draft an agenda, inform the CG that this is going to replace the usual monthly call
 - Action item: Figure out the TPAC fediverse social meetup
 - Action item, Darius: CFC to SWICG list, link to the two PRs (699 and 700), link this comment too https://github.com/w3c/strategy/issues/435#issuecomment-3366604190