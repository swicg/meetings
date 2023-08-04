# 2023-05-19 W3C SocialWeb Incubation Community Group Agenda and Call Notes

### Participants
- hellekin
- nightpool
- Dmitri Z.
- Robert W Gehl
- [Johannes Ernst](https://reb00ted.org/) (irc: j12t)
- Evan Prodromou (irc: eprodrum)
- [Matthias Pfefferle](https://notiz.blog/) (irc: pfefferle)
- Jan Wildeboer
- [David Blue](https://bilge.world)
- Peter Zingg
- Bob Wyman
- [Sarven Capadisli](https://csarven.ca/#i)
- [Tantek Çelik](https://tantek.com/), Mozilla & IndieWeb, implementer: Webmention, contributor: BridgyFed (AP)
- [a](https://trwnh.com)
- Kainoa Kanter
- indieterminacy
- Manton Reece
- [Melvin Carvalho](https://melvincarvalho.com/#me) ([nostr:npub1melv68](https://primal.net/profile/npub1melv683fw6n2mvhl5h6dhqd8mqfv3wmxnz4qph83ua4dk4006ezsrt5c24))

### Agenda

Welcome to the SocialWeb Community Group!

1. [ ] Code of Ethics & Professional Conduct Reminder:  https://www.w3.org/Consortium/cepc/
2. [ ] W3C Community Group Process and Governance: https://www.w3.org/community/about/process/
3. [ ] IP Protection Note:
   a. **Anyone can participate in these calls.** However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
   b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA):
   https://www.w3.org/community/about/agreements/cla/
4. [ ] Goals and focus for the SocialWeb Community Group
  * Deliverables! (Community Group Report documents, test suites, tutorials, code, discussion)
  * Potential incubation of documents / input items for future SocialWeb Working Group charters
  * Coordination with other related standards groups
5. [ ] Relationship with the other centers of community and discussion, such as SocialHub https://socialhub.activitypub.rocks/, Fediverse Enhancement Proposals (FEP) https://codeberg.org/fediverse/fep, the Fedidevs Matrix chat rooms `#fediverse-developer-network:matrix.org`.
6. Governance process for adopting Work Items.
  * Example of an existing effective Work Item Process, see the Credential Community Group's process doc: https://w3c-ccg.github.io/workitem-process/
  * We have a rich backlog of potential work items (see FEPs, but also old SocialCG Use Cases), plus anything new that members are interested in.
7. [ ] CG communication channels
  * Voice calls/meetings: Monthly or bi-weekly?
  * Discussion: SWICG Mailing list https://lists.w3.org/Archives/Public/public-swicg/ and SocialHub https://socialhub.activitypub.rocks/
  * Code: https://github.com/swicg/general
  * Chat: ircs://irc.w3.org/#social Matrix?
8. [ ] Chair election! Current CG chairs: Nightpool, Aaron Parecki, Dmitri Zagidulin (temporary, assisting).
  * Proposal: 3 new co-chairs to be elected, ranked choice voting. -> on the mailing list?
  * Discussion and nomination period over a number of weeks, via the mailing list
9. [ ] Future call times
  * Monthly or bi-weekly?
  * If bi-weekly, alternate between weekday and weekend time slots?
  * Proposals for time slots other than this one? (Fri 9am EST)
  * To be determined on the mailing list.

## Notes

### 1. CEPC

This is following meetings are governed by the CEPC.

### 2. Process

Calls will be recorded.

### 3. "Intellectual Property"

Anyone can contribute but substantial contributions require CLA (to protect against patent trolls)

### 4. Goals and focus for the SocialWeb Community Group

- Discuss towards specs
- Test suite

Evan: we have a lot of opportunity to be building on top of existing specsw from the SocialWG. I think there are lots of things that people are interested in building, like e2e Encryption, Group structures, helping to incorporate the work coming out of the FEP community. One thing I'd like to ask: this group's charter is something along the lines of "Building on specs and related technologies", which I assume is any sort of distributed / federated social networking. However, a lot of our conversation over the last months have been arguing about alternative social networking protocols. I wonder if it's worthwhile to constrain our group to the currently active social specs out of this group/WG. Bluesky, Nostr and others have their own groups working on their specs, so it's not exactly our goal to argue/discuss etc.

Tantek: echo Evan's concerns, accurate observations. It raises interesting tensions in general at W3C, *should we scope work to a problem area, or to specific technologies?* I don't kknow what the right answer is, I've been following discussions on mailing list and across the fediverse. It depends on what goals we have - is it to maintain specs, maybe more focused is better. If goal is broader interop and new specs, then maybe broader scope is preferred.

Johannes: We have unique opportunity - an existing networkk with millions of people interacting on a daily basis using particular standards (defined in this group and predecessors). I suggest we simply grow that network. Meaning, we look at - what does it take to make those users that we have already be happier, able to do more things in daily life, bring friends. That should be the objective; not by tech & specs, but by those users, making them happier, whatever that means. Certainly not to "Osbourne ourselves" (killed the business of an early laptop company, announcement was "the next version is better", so it killed the product). *What use cases do users want to solve that cannot be solved by specs today? --- and solve those one at a time. That should be guiding principle.*

nightpool: Having be involved in the deep history of this group - one of the things that was really a struggle was implementor involvement. I 100% agree with Evan's concerns that group's energy may not be super productive when discussing other specs, one of the reasons it's not productive is because we don't have implementors from those groups, so there's no desire with standardization (like with Bluesky at the moment). I'd like to focus on places where we have current implementor interest, what'll be practically achievable.

Evan: Dropped a [link on the specs](https://www.w3.org/wiki/Socialwg#Specifications) out of the WG, 11 of them covering different stacks, that's quite a bit, all very extensible. Lots of things that this group here can discuss, lots we can be interested in, but noone else on the web who can do the work on these specs, evolve them, build on top, document, extend. That's our role; we'd be doing a disservice to the internet community if we don't take on that responsibility. Having deep conversations about bitwise differences about Nostr & Bluesky - it's fun, but not work we're here to do.

Bob Wyman: My concern is that, because there are other protocols that obv have motivations, some silly some good, there is much to learn from understanding those protocols, and much that can be taken from them and incorporated, to strengthen our protocols. So I'm concerned that a ban on talking about those other protocols would mean not being able to access those tremendous resources and knowledge. Could you expand a bit more on this? For example, I'd like e2e encryption, message integrity, etc, hinted at or implemented at other protocols. I'd like to be able to bring those in.

Evan: My sense is - absolutely, you have a really good point. If we don't learn from other work that's happening around the net, we'd be stagnating, we need to integrate & adapt. That makes a lot of sense. What I would rather not have is a debating society, where we'll crown one protocol king, on the grounds of pure logic and flame warrior activity. So if we can keep the discussions about the work we're responsible for doing (which might include additional work in the future), the dozens of specs we've already taken on. But yes, having other protocols inform our work is great.

a/trwnh: since this is w3c/SocialWeb, we should be focusing on the social web. when it comes to specs, focus should be very strongly on what it would actually take to build a social web, have it be part for www. Looking to other specs for inspiration is fine, but purv...

Dmitri: we should focus on the work at end. Could use WGs.

Tantek: nightpool made a very good point - level of implementer interest as a guiding principle. I can speak to the success of other WGs - taking things from incubation to specs. One of the strongest predictions for that success is - level of implementer interest. The WGs that have limited their scope to "do we have strong implementer interest" before we add it to scope, have been most successful. Especially in more mature/evolving areas. When we started SocialWeb WG, it was a bit more greenfield, but a different situation now. Many established specs and products (many of them out of the WG), so that's a strong thing to consider. Flip side: at w3c, we want to include a lot of different voices proactively. I agree debating & flamewar against teams is not helpful or productive. That said, it's a good thing for folks involved in w3c to do outreach to implementers of those other specs. And if they're not interested, that's fine, but if they are, collaborative. Not invitation "come to w3c and we'll rubberstamp your spec" - no, but if you want to discuss commonalities, porting features from one spec to another. Outreach should be proactive rather than sit back and wait "why don't those guys join us" - let's be the grown-ups in the room.

janwildeboer: Evangelist at RedHat. Short version - wrt focus groups and implementer outreach - exactly that. What we are seeing with AP is divergence and workarounds of established spec - we should not discourage that, but learn about weak spots in the specs and improve it.

Bob Wyman: I'd like to agree strongly w/ Tantek about implementer interest, vs academically beautiful/provably excellent things that don't end up being built. On the other hand, I've also been in efforts at w3c particularly where implementer interest was read as - like "neither FB or Google would implement that, so we should not discuss it". We should recognize that implementers that exist now, and then also there are potential future implementers, if we only give them a standard approach. So it's important that when one talks about implementers, we should recognize that there's those new and growing ones too, who would build if particular problems would be addressed. Or ones we don't know about. So, we don't want to emphasize encumbents only.

nightpool: yeah, this is somewhat a contentious topic in socialweb spaces in general -- it's important to ground our discussion of implementers in terms of the audiences they represent. Internet today is successful because of the users who choose their software and why they choose to use it. Nobody in the socialweb space is a monopoly on the grounds of vendor lock in, we have interoperable specs, self hosting, etc. Most important to think of when guiding implementation - priority of constituencies and users. Implementers important as well, but we should be cognizant of users.

a: in order for those potential implementers to become real implementers - the reason anyone might be holding off on any of these specs is just the confusion around some of them. Lot of things that need to be clarified/addressed. Obv they're not perfect, they're good, but room for improvement. E.g. why hasn't C2S spec not taken off, things like that. Needs guidance and clarification. People read the spec, don't understand part of it, don't get vision or motivation, they just look at dominant implementations, and follow suite. At the end of the day interop is what we're after, here. Work will be best served by improving the specs, making sure they're clear, actionable.


Johannes: I want to bring up DX (developer experience), which is not the best right now, speakking from my own experience. As a dev entering the AP context, it's too complicated to figure out what I need to implement. Specifically, which parts I need to do for interop, various arcane details. HTTPSig etc. We have competition from other protocols that specifically focus on DX. Specifically, Nostr - the brand is "you can build something in a few hours that's super easy". *So I want to make sure we produce not just standard but a DX that goes from zero to interop in shortest amount of time.* May need to adopt larger perspective. Specs, community, examples, full stack.

Tantek: Johannes makes good point, a lot of the existing specs - success or not can be traced to DX. Aaron Parecki (co-chair) who's not here, has done several sessions "you can develop a Micropub client in 10 mins", similarly, Webmention sender and receiver. This kind of thing is key to develop new specs, and to improve and clarify existing ones. [Priority of constituencies](https://www.w3.org/TR/design-principles/#priority-of-constituencies) There's been lots of discussion on what we should discuss vs not - we can divide that question up. Keeping the discussion more broad or open in the CG (wild wild west) is still ok, but if we want to actually evolve the specs in a Working Group, we probably do want to pick a narrower scope of what to evolve, based on adoption, end users, extensions. Lastly, re C2S part of the spec -- there are dozens of implementations of Micropub C2S spec, that's been great. Not the same as AP C2S - we standardized both because we weren't sure which combo would be more appealing to developers. It's ok that if there's multiple specs and one takes off and another doesnt, there's opportunity for complementary work. Bob brought up new vs old implementers - I think that's a really important point to consider. We all know ActivityPub took off essentially because of Mastodon, we used it as part of finishing the spec. We know and acknowledge it - that said, there's many more future implementers than existing. Good to see the long tail vs not just too dominant ones. I too remember the anti pattern re "if big players don't implement this it's not worth pursuing" -- I don't think that's true for the social web -- I hope we don't get into that situation. We can do both. How do we add new features, get new devs on board as well.

a: I'd like to briefly point out - there are a lot of specs under umbrella of SocialWeb CG, but also some other missing pieces in other groups, like HTTPSig spec, especially authn and authz, especially cross domain. Those were left wide open first time around, and even now, those pieces are in development by other WGs and CGs. Not sure how to proceed there, as an implementor. I don't have guidance, except - look at all that other stuff, maybe some of it useful some not. We should not lock ourselves into using that same outdated draft of HTTPSig forever. But also some nonzero thought on which parts should be needed for implementations.

Manton: C2S API and Micropub -- I've implemented Micropub, but not C2S, just because I'm not aware of clients out in the world who are using it. I'd love to know more about clients in the wild, what the friction is, what Mastodon API offers (not a standard), etc. Would be good focus for the group how it should evolve.

Evan: It's a common term, but specification is not documentation. Specs that we have are somewhat readable, but not designed as tutorials for jump-starting a developer into the process of developing. We should recognize there may be additional documents that can ease that. One thing that comes up in GH issues is things like "why did you choose this?" / "why does it work like that?" - not how specs usually work. But we have opportunities to document this, for the curious. Also, tutorials are a great use for this group. ActivityStreams C2S is close to my heart, I think it's a good API, main reason it's not used is - Mastodon chose not to use it, and everyone clones that. And the reason they chose not to use it is - the implementers already had an API when they joined group.

nightpool: More context for HTTPSig spec - it's critical to the actual nuts & bolts interop in the Social Web, but not under the purview of CG, it's in the HTTP WG at IETF. (Lots of drafts, major changes.) But at least it's adopted by a WG now. It's one of the biggest issues right now - earliest tutorials use older versions of HTTPSig spec, Mastodon & Pleroma & others have moved on and don't support those versions, etc. Good progress in making errors easier to understand.

Tantek: as action item to consider - do we want to propose scope for an actual WG to iterate on particular specs?

nightpool: I think CG working mode has served us well; a lot of space to iterate on specs in terms of extensions / CG Notes.

### 5. Relationships with other community places

- [W3C Solid Community Group](https://www.w3.org/community/solid/)
- [W3C Nostr Community Group](https://www.w3.org/community/nostr/)

### 6. Governance process to adopt Work Items

### 7. Communication channels

- Mailing List + SocialHub
- IRC #Social
- Matrix #fedidevs

Evan: we do not have an inband comms channel. Group? Hashtag? #SocialCG may be just what we need.

### 8. Upcoming Chair elections

-> Discuss on the mailing list

We can use polls on the forum, Dmitri proposed ranked voting, not sure that is available with Discourse Polls.

### 9. Future call times

Kainoa: Twice a month would work great, weekly might be too much, monthly not enough. Good middle ground.

Evan: I would lean into once a month / very sustainable. Biweekly as high as I'd want to go.

jwildeboer: If we're close to saying "there's a lot to do", makes sense to have focus calls. For example "outreach, specific work items".

hellekin: I second the idea of alternative different dates and times. Also, I'd like to say I really like using Hedgedoc during meetings - it allows copy & paste to forum, also allows to make agendas in advance so we can share points, distribute discussions etc.

nightpool: I'd like to echo once a month may be paradoxically better - allows us to keep more focus on issue tracker and forums. Some of us do this part time - spending a lot of our energy in meetings, the less time we have for implementation & specs.

Dmitri: For once a month proponents - how do we pick a time slot that works for everyone?

Johannes: I've noticed we have subgroups / interest groups that want to focus on a particular subject.

Evan: Re how we choose a time -- Dmitri was suggesting twice a month, but we could also alternate different times between months. So, first month at Friday, next month on the weekend.

Tantek: I'm interested in hearing how frequently and what topics implementers in particular want to reserve call times for. That's the audience for sync meetings. If people want general purpose brainstorm meetings, that's fine, but I'm interested in implementers.

a: Could we move this time slot forward two hours?
(tantek: +1 moving forward two hours to 08:00PT would work better for those of us on Pacific Time)

Johannes: re what Tantek has - do we know who here are implementers? Might be really useful.

Dmitri: Good point, what's a good mechanism for that?

Johannes: Gabe set up a Fedidevs website, specifically People page. Maybe we could use that?

hellekin: On SocialHub, we have Groups for implementations/software categories. We can use that (team members identified with their logo). We can make it mandatory.

Dmitri: Huge thanks to hellekin for hosting SocialHub all these years. What can CG do to help you?

hellekin: I've been trying to involve more people in sysadmin and moderation. If SocialWeb CG is making SocialHub an official place, more people will be interesting in participating in the tasks. In terms of finance, my org has been taking some of it on - Amy Guy as well (backup and other servers). At some point, we should set up some kind of nonprofit to take charge of this. No hurry right now.

## Action Points

- [ ] @tantek in 4.
- [ ] @evan In-band (Fediverse) comms channel: proposal to use #SocialCG
- [ ] Choose days and times for upcoming meetings
