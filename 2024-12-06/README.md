# December SocialCG Meeting 2024-12-06
Archived: https://www.w3.org/wiki/SocialCG/2024-12-06

https://meet.jit.si/social-web-cg

## Present

* Dmitri Zagidulin
* Damon
* nigini (https://nigini.me)
* Darius Kazemi (@darius@friend.camp)
* Tantek Çelik (https://tantek.com/)
* Evan Prodromou <acct:evan@cosocial.ca>
* [Ted Thibodeau](https://github.com/TallTed/) (he/him) https://mastodon.social/@TallTed
* Angelo Gladding https://ragt.ag
* a <trwnh.com>
* Ryan Barrett (https://snarfed.org/)
* Emelia Smith (https://hachyderm.io/@thisismissem)

# Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
4. Task Force Updates
5. Social Web CG Charter PR and issue processing
    - Aim to get the CG Charter ready to vote on for the January meeting. This means:
    - Go through [existing PRs](https://github.com/swicg/potential-charters/pulls) and update status
    - Go through [CG-related issues](https://github.com/swicg/potential-charters/issues?q=is%3Aopen+is%3Aissue+label%3A%22CG+Charter%22)
6. Social Web CG Staging Process discussion - integrating it with the Charter.
7. (if time, from previous meeting) C2C protocol TF -- https://lists.w3.org/Archives/Public/public-swicg/2024Nov/0010.html | document protocols built on top of ActivityPub, including how to negotiate protocols client-to-client or actor-to-actor. signalling server behaviors, client behaviors, actor behaviors. generating one or more reports for possible profiles.

# Minutes


## Intros
## Community announcements

* Dec 7 & 8 - IndieWeb San Diego! https://indieweb.org/2024/SD
* Fosdem (in Brussels) - including an ActivityPub breakout sessions https://fosdem.org/2025/
* Darius: folks are encouraged to beta test the Fediverse Observatory https://asml.cyber.harvard.edu/fediverseobservatory/ ; send an email to fediverseobservatory@cyber.harvard.edu to request to join

## TaskForce Updates

* Portability/Export TF: meeting in the next hour, right after this call! https://www.w3.org/events/meetings/d5a517d8-2e0b-41ce-8611-956217745157/

* HTML Discovery report — new versions, please review. https://github.com/swicg/activitypub-html-discovery
    * Evan will coordinate with Tantek on triaging issues, e.g., assigning `rel=me` isssue to Tantek to prioritize
    * Next meeting this month: (scheduling in progress, Evan to coordinate on meeting time with Dmitri and Tantek)

* Forum/Threaded-Discussions TF — continued discussion on non-Note updates. More to report as the work progresses. Discussed the existing FEPs and how to converge them. So far, the recommendation is to use the `context` field for grouping objects together (not to be confused with `@context`).
    * Talked about future directions for 2025. Need User Stories for how to "backfill" activities in a discussion thread or collection of objects.
    * Also would like to explore using the Outbox collection for more stable backfill via Activity log.

* Previous meeting, agreed to start a Group Task Force. Repo over at https://github.com/swicg/groups
    * Collecting requirements, setting scope
    * Would like to invite people to contribute User Stories — open issues on Github!

* Geosocial TF — https://github.com/swicg/geosocial working on Explainer, proposed monthly meeting on mailing list.

* Approved a draft Extensions Policy in April this year. Before we take the Policy to final, we want to do some testing.
    * Historically, extensions were collected within the Miscellany document at https://swicg.github.io/miscellany/
    * Need more consumers/publishers using this context.
    * If you have an AP implementation using these popular terms, it's a great time to use this via the link (vs. defining inline in the object)
    * Sebastian: What about `alsoKnownAs`?
    * a: That's been added to the `@context`. The documentation is in the DID Core spec.
    * Emelia: Is there a difference between the published AP spec and the errata?
    * a: No, it's not defined in the vocab file, just in the AP `@context` and namespace.
    * Emelia: Should we add it to the Miscellany context?
    * a: Not sure?
    * Evan: Let's open an issue on GH to discuss

* Trust and Safety TF — Set up initial scope of work, have multiple workstreams. General focus is on Content Labeling, Formalizing the Flag Activity. Meetings every 2 weeks, next one on Dec 10. (Skipping 24th Dec)

## Social Web CG Charter PR and issue processing

* https://github.com/swicg/potential-charters/pulls
    * skipping pulls re: effective start dates
    * [define Committer role](https://github.com/swicg/potential-charters/pull/51)
        * Evan: It's expected there would be a role of Committer as discussed prior; I added a definition for a Committer as "a person authorized to make changes to Github repos managed by the group"
        * Dmitri: For clarification, what's the relationship between Committer, or Editor of a report or note, or Task Force leader?
        * Evan: Good question. We use terms like "Task Force lead" and "editor on the report". These are almost always the same person and are also usually roughly equivalent to someone with commit role on the github repo. 99% of the time these are identical terms for us.
        * Tantek: Can we not introduce a new term and just re-use the w3c notion of "editor"
        * plh: I would recommend being careful here. there is [an open issue in the w3c about editors](https://github.com/w3c/process/issues/948). Depending on context, it can mean different things. If you want to avoid that pitfall, "committer" is a good word for the CG.
        * Dmitri: "Committer" is less formal than editor.
        * Evan: Also the possibilty of producing software test cases, reference implementations, etc. in which case a committer would be generating software and not touching documents.
        * a: "Contributor"?
        * bumblefudge: "Contributor" has an IP implication
        * a: I don't think the IP thing relates to names; it is about membership in the group, and to be a committer/contributor you probably need to be a member of the group.
        * plh: This could be a long conversation. Here is an example of a Contributor definition in a previous WG: <https://www.w3.org/Signature/Contributor.html>. It's not related really to your definition.
        * Dmitri: The tooling/github part is incidental; it's more about contributing to the work of the group.
        * tantek: plh's examples are good, but they are scoped to Working Groups. That level of formalism makes sense for a WG; not sure we should overindex on formalism for a CG. Let's not add to the number of terms and roles. Lowers the barrier to participation to have less special wording.
        * a: My second suggestion is "authorized user", because it sounds like it's about commit rights to github repos?
        * evan: I think there's another issue about uniting these terms. We use champion, task force lead, editor.... Maybe we deal with this async.
        * Dmitri: We'll follow up on this, async.
    * https://github.com/swicg/potential-charters/pull/52
        * Relatively minor PR, reached consensus and merged
    * https://github.com/swicg/potential-charters/pull/53/
        * plh: Staging process is about process and group collaboration. You might want to change it frequently, and it's better to keep it separate from the main charter to make this easier to change.
        * Dmitri: There's strong consensus to not copy the staging process text into the charter. Do we reference it in the charter at all, or do we leave it out?
        * plh: I am hoping you reference the CLA in the CG charter. I don't want you reinventing the IP process
        * Emelia: It is important for the staging process to say there is an IPR policy if you want things to move up to the CG or the WG. There's a problem where people do work, and then they think they are going to move forward. Then they realize their employer has a problem with it.
        * plh: it's fine to provide a reminder in the staging document, I have no problem with that. it's important that when you contribute to the CG you know you are implicitly giving permission to move it to the WG.
        * Emelia: but the staging process is before the CG
        * Dmitri: we have a couple decisions for us to make. Does anyone have objections to this specific pull request? The second question is do we mention IP requirements in the group charter?
        * plh: It would be good for the CG charter to mention IPR
        * Evan: it's already the case
        * Dmitri: any objection that we merge the clarification in this pull request to the staging process?
            * no objection, merged
    * https://github.com/swicg/potential-charters/pull/54
        * Dmitri: I understand that WG charters have lists of groups to liaise with. Do we even need that for a CG?
        * plh: You don't need to mention that in the CG charter. The reason WG charters do that is we want to make clear for the staff when a WG moves forward towards a spec, we actually check to make sure there is communication. But we don't monitor CGs at that level and no one is going to call you on this.
        * Tantek: I suggest simpler/shorter is better. If you look at the guidance in the comments, this is about significant dependencies. I don't think this CG has significant dependencies on other groups. I don't think updating this list should block the CG charter.
        * Evan: +1 to tantek
            * Closed PR
        * Tantek: added a PR to drop that "significant dependencies" boilerplate: https://github.com/swicg/potential-charters/pull/57

### Issues

* Dmitri: We are running out of time in the meeting. I encourage people to look at these issues between now and the January meeting. The main item of discussion has been around the staging process and whether it should be linked in the charter.
* Bumblefudge: A lot of these issues are smaller things that can be handled async. The next meeting should focus on staging process.
* Evan: It would be good to get wider review on the document so we can come into the next meeting with a strong consensus on adopting it. I suggest publishing on the mailing list, SocialSG account, SocialHub, blogs, etc.
