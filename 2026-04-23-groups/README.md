# ActivityPub Groups TF 2026-04-23

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- @mayel@bonfire.cafe
- a <trwnh.com>
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
- Dmitri Zagudulin (listen only / reply via chat)
- Ben Pate
- Julian Lam (@julian@activitypub.space)

## [Agenda](https://github.com/swicg/groups/issues/37)

1. Introductions and administrative
   - Code of conduct https://www.w3.org/policies/code-of-conduct/
   - CLA https://www.w3.org/community/about/process/cla/
2. About this task force
   - founding resolution
   - user stories
   - high-level explainer (README.md) - initial freewrite, expected to iterate together
   - Publish a report on groups in ActivityPub
   - Implement
   - Relationship to FEP 1b12 https://codeberg.org/fediverse/fep/src/branch/main/fep/1b12/fep-1b12.md
3. User stories
   - join a group #1
   - leave a group #2
   - get group members #6
   - post content privately #13
   - Who can perform actions #26



## Minutes

### About this Task Force

Initially resolved via https://github.com/swicg/meetings/blob/main/2024-11-08/README.md that a Groups TF would be established for "Rigorous definition of Group/Join/Leave/members/inbox/outbox etc."

Repo: [https://github.com/swicg/groups/](https://github.com/swicg/groups/)

Deliverables:
- bumblefudge: Should we focus on UX guidelines for how to deal with groups? So that people know what user expectations are for this syntax, and can implement Groups some other non-colliding way if they can't or won't meet those expectations cross-implementation?
* Ben Pate (via chat): UX + semantics would be great.
* Evan: based on user stories, last fall I went through user stories to give basic ideas of how user stories could be satisfied with the basic activity types built into Activity Streams 2.0. https://github.com/swicg/groups/issues?q=is%3Aissue%20state%3Aopen%20label%3A%22user%20story%22
* Group user stories were in original AS [vocab](https://www.w3.org/TR/activitystreams-vocabulary/#motivations)
* Evan: lots of open questions. existing explainer might not be fully specced protocol right now, but offers directions. our next step as a TF is to work through these

### FEP 1b12 congruity/backwards-compat?

- very public-only
- Follow/unfollow instead of join/leave
- a: more of a relay system than a "group", since all public and all Announced; I would argue it's offtopic or orthogonal for us - could dovetail, cuz you could "follow" a group you're not in
- mayel: FEP is limited/incomplete for everything that a group is or can be, but IMO backwards compatibility is quite desirable and possible
- BF: are they "namesquating" Group?
- a: 1b12 kinda squats/overdetermines the AS "Group"; unclear if impl 1b12 ASSUMES all Groups are 1b12 Groups... unclear compat with more general as:Group semantics
- Evan; One option is cleanly making it work BOTH ways (either is optional if you implement the other); One option is nuke it
- Matthias in chat: WP and I believe NodeBB implement it, in addition to the list in the FEP (Lemmy, Friendica, Hubzilla, Lotide, Peertube)
- a: i think the energy right now seems to be you can opt into both profiles -- Groups TF focuses on managing membership, like Forums TF focuses on threading posts, and 1b12 is a distribution strategy for using Announce

### Scoping/Which User Stories

- Evan: I think parity with Facebook Groups is a good starting point/default case
- a: Guild in Discord is similar. Forums TF is for grouping posts into threads and forums; Groups TF is for grouping people/actors/users/etc into "groups". I would say this TF's summary is "who's in, how do they get in, what can they do".
- Mattias: WP might be misusing/stretching Groups semantics currently: we link blog (as actor) to each blog's users (as group of additional actors), outside world can Follow but only group members can invite a group member; is that in scope?
- Evan: base profile can be very open, but i will be mad if i can't build a Facebok Groups clone on top of the base
- Mayel: Every kind of group should be buildable on this base; cross-impl Actor membership is the core functional req maybe (i.e. if WP can invite a Masto user to a group, that would qualify basically).
- Evan: currently there is a tendency to treat the "instance" as group for "local timelines" and other usecases; that seems an infra-locked, single-group model; makes multi-group more possible

### Issues to triage

- Base foundation: join/leave, enumerate members (where appropriate), nonpublic content are all open discussions
- Join/leave, naïvely, can just be as simple as as:join(Group)/as:leave(Group)
- Follow/accept(Follow) model doesn't have removal uniform (Mayel, in chat: Undo(Follow) and Undo(Accept)?
- Matthias:
- Matthias: How to deal with already-implemented prior art? Consider Inheriting membership in Lemmy?
- a: I'd rather have a distinct membership system vs followership. Sort of a "roles" that you can add "members" into instead of collapsing it all into just following binary state
- Matthias: "implicit join"?
- Matthias: Somehow detecting old model/profile might be smooth and solve WP's prior problem with Friendica (where follow===join every time)

- Evan: Leave is a separate use case, and Removing someone is another usecase, Block is another...
- a: state machine diagram good for a starting point
- bf: base profile needs remove, doesn't it? i don't wanna interoperate with an instance that implemented "basic profile" but i can't boot their members if i need to!
- a: yeah basic profile + extensions should work, full "membership controls" feel base to me. voluntary (join + leave) as well as controller-wise (add/invite + remove)
- Mayel: in Bonfire, we already have Groups on a very FB-parity model w/ACLs, discoverability options, etc.; we have all the UX dialed in, but NOT federated (same-instance-only)
- We use both Follow and Join in distinct ways;
- a: should be fully disjoint: "member that doesn't follow" and "follower that isn't in the group" should BOTH work imho
- Evan: Crucial wire-format/ontology question: is a Group an Actor or an Object? Some user stories req it to be an Actor, but maybe
- bf: making it an Actor definitely SHOULD be at least an optional profile; if base profile doesn't require an inbox/outbox, easy way to signal which groups are "advanced" and which are "base"
- a: actor seems natural? give it an inbox and say it follows some protocol for managing the group. give it an outbox and it can publish activities according to however it wants (maybe 1b12, maybe something else)
- bf: +1 love it, that's a good semantic model.
- mayel: +1, making them an Actor seems fine
- Julian: two of the biggest 1b12 implementers arent here and likely wont ever be; asking them to drop Announce() won't work well, definitely "sniff" for legacy/1b12 and special-case if needed; Announce as distro model seems super important to them all
- Julian: [Capability sniffing FEP](https://fediverse.codeberg.page/fep/fep/844e/) might help figure out forward- and backwards-compat sniffing
- Mayel: +1, we already use 844e for RFC-9421 support discovery
- a: not requiring or disallowing Announce activities; we just wanna align on base-level membership management and any actor can choose to deliver activities or manage its outbox however it wants. in the Social Web WG we can hopefully explore "protocol negotiation" so that actors have a way to say they are following 1b12 or not.
- Evan: participation doesn't just mean coming to the meetings, async is good! It behooves us to keep door open to indirect or informal "chiming in"
- Matthias Pfefferle says:but we should be sure to not have incompatibility in the end. because most of the implementation "look" very similar, but might behave differently.
- bumblefudge says:^ breaking UX, security, or privacy requirements is a good argument for making partial compatibility impossible! those are many implementations with many users
- Julian: Follow versus Join  backwards compat also hard: Follow(group)/Accept(Follow) is currently async (usually manual/human-interactive)
- a: we are already targeting join and follow both being supported and disjoint (like Mayel already implemented); Evan: not sure the use cases in the repo reflect that!
- Julian: Last thought on rimu from piefed or guy from lemmy, post a copy of the minutes on activitypub.space, they will see the signal
- a: Can you do that Evan? Evan: Yup, I'll do it.
- Announcement: SocialCG Google/w3.org Calendar is definitive, NOT github, if they ever conflict again!
- Action Items:
- a: I'll start the state machine diagrams before the next meeting and we can discuss
- everyone else: please look at the user stories and comment where appropriate, or if a user story is missing then please file an issue
