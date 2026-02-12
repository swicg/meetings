# February SocialCG Meeting 2026-02-06

SocialCG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Z.
* [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
* [Johannes Ernst](https://j12t.org/)
* [Michal](https://id.mrkvon.org)
* [Andy Piper](https://macaw.social/@andypiper)
* [Darius Kazemi](https://friend.camp/@darius)
* [Matthias Pfefferle](https://notiz.blog/)
* [Ryan Barrett](https://snarfed.org/)
* [Evan Prodromou](web+acct:evanprodromou@socialwebfoundation.org) (kind of)
* [Paul Fuxjaeger](https://chaos.social/@cypherhippie)
* a <trwnh.com>

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
4. Task Force Updates
5. WG updates if relevant
  * Darius with updates
6. Main Agenda
    - Proposal for an Events task force
    - Reminder about CG Chair Elections
    - FOSDEM and Protocols for Publishers London reports

## Minutes

### Announcements

Johannes: FediForum is doing an experimental UnWorkshop, a cross between an UnConference and a Workshop, focused on "How do we grow the Fediverse?". Asking for position papers, etc. Organizing this with Mike Masnick. [More info and registration](https://fediforum.org/2026-03-growing-open-social-web/): https://fediforum.org/2026-03-growing-open-social-web/

Andy Piper: [FediMTL](https://fedimtl.ca) is coming up in Montreal https://fedimtl.ca on Feb 24, 2026.

Johannes: There are now so many community events that, to avoid collisions, we're trying to curate an [events list](https://fediforum.org/events) at fediforum.org/events, so please reach out and add!

### TF Updates

Johannes: quick update on website TF. We have a reasonable version of the [activitypub.rocks](https://activitypub.rocks) website at this point. No longer out of date and has the links people have said they want to have. Will be in maintenance mode without regular meetings for now. If there's a redesign, we'll get the meetings started again. We have a PR process with a period of comment. Please do a PR/issue if there are any suggestions you have or issues you want to raise.

Lisa: not a lot of change on Account Portability TF. There's still implementation work being done, though the implementers have not tested against one another yet. I'd be interested if there are any other people working on implementing live account LOLA or even backup/restore.

Dmitri: Juan and I did a proof of concept full account export using the FEP for Hollo/Fedify

### WG Updates

Darius: There will be a working group first meeting announcement and it will be announced to the CG.

### Main Agenda

#### Report out from FOSDEM

Andy: We had a Fediverse drinks meetup on the Friday before the event, and about 40 people showed up including Ben Pate, Hong Minhee, and others. We had a really nice range of talks on the Social Web track, probably too many and need more breathing space next time. Most of the videos are [online now](https://fosdem.org/2026/schedule/track/social-web/) I think. We had topics like ActivityPub C2S API, local reports from different EU countries, frameworks like Emissary, a Fedify talk, and Matthias was our kickoff keynote speaker. Appreciate all the work and support. Couple of BOF sessions on Sunday. One on events with projects wondering how they can collaborate better. There was a Hachyderm meetup. And a Fediverse and EU Digital Services panel.

Andy: There was an event in London, Protocols for Publishers, in the previous few days that was bringing together ActivityPub and ATProto devs with news publishers. Talks like: NewsMast and building community apps, ATProto and "bring your own algorithm", a talk about monetization by Jeremiah from Web Monetization group, some workshops which from my perspective was publishers talking about how terrible the world is but it was a good exercise though it was unclear the technical connection. I think they are trying to get a series of these knowledge sharing events.

Juan: A side event at FOSDEM was one from [ROOST tools](https://roost.tools/), that does open source trust and safety for platforms. They had a brunch with Christchurch Call people. I found out at the brunch that their big project for their first year was [Osprey](https://github.com/roostorg/osprey), originally built for and open sourced by Discord to be a dashboard for Discord moderators of large communities with optional ML hooks and optional external API hooks. Apparently Bluesky was using Osprey and now it's v1 stable open source. ROOST is eager to have people from different AP implementations write their own drivers for Osprey.

Dmitri: Is this a protocol or API?

Juan: It's an open source dashboard that can, in theory, plug into protocols and APIs.

#### New Events TF proposal

Dmitri: There's a proposal on the mailing list for an Events TF. Evan has nominated Andre to be a convener for that; we are waiting to hear back from Andre. If you have interest, please weigh in on the mailing list thread!

#### CG Chair elections

Dmitri: Just a bit ago I sent an email to the mailing list. We are going to have our first ever CG Chair election. There is a two week nomination period. If we get more than one nomination, we will have a vote. Please feel free to send your nominations to the mailing list. Any questions about elections?

Matthias: How do they work?

Dmitri: If we get more than one nomination, we will create a poll on a runoff voting site that other CGs have used. We'll cross reference votes against CG members.

#### Other business

Dmitri: I'm curious, Andy, you said you were hard pressed to offer solutions to the woes of the publising industry. What pain points have you heard from publishers that our family of protocols may or may not be able to help solve?

Andy: The workshops yesterday were really structured to let publishers express their concerns around things like plummeting search engine traffic due to AI. Another element was monetization, whether to paywall or not? How does advertising work, and how much do you need to know about people you are advertising to? I ended up in a conversation about identity, which was interesting in the Fediverse context, but was more focused on what publishers wanted to know and how they could track their audience. Members of identity-focused W3C WGs were in attendance. I think the gaps related to how content gets discovered, shared, and paid for.

Dmitri: Makes sense, those are the fundamental challenges of the Fediverse and any decentralized social media.

Johannes: Now that we have a WG again, the "attractiveness" of the public that might be attracted to it has changed. I was wondering whether anyone has thoughts on [...]. I'm always concerned that we don't have a lot of input from people we believe ought to adopt this but for some reason aren't. Perhaps there is too much of a gap between what publishers need and what a W3C can do.

Juan: My prejudice is that the WG and CG and W3C generally is developer-facing and we are trying to get websites that have users to become AP websites. Whereas specific apps and platforms shouldn't use our venue to get users, we are trying to get apps that will need to get users. A good place to look for publishers, NewsMast and Michael Foster's group is a good place to point publishers because they are iterating on different product shapes and clients. They are trying to build readerships for publishers and be a laboratory of products. I think _Protocols for Publishers_ is the kind of org where use case specific product and market research should happen. Fediforum, too.

Johannes: I didn't mean for application discussion here. But should we attempt to create a pipeline of people to join the CG/WG? What are we doing to support this?

Darius: One of my goals is to get publishers & similar groups — so, we need as many W3C Members as possible to join the group. I've been making a list of likely candidates that we want to specifically invite (started at TPAC and through now). For the Community Group, you don't need to be a W3C member to participate; that can be part of the pitch. (If somebody is not currently a member, then participate in the CG, and if you find it helpful, join W3C and the WG). But yes, the intent is to get the word out to every member org that is remotely relevant/adjacent to the Social Web. One thing that I found is that — there is quite a difference between a CG and WG — there are plenty of orgs who don't care about CGs, but do about WGs. 
The intent is to have joint CG-WG calls/sessions, for maximum cross-polination.

Johannes: Would it make sense to formulate a two sentence pitch (to participate in the WG) and add it to ActivityPubRocks.org?

Darius: Yes. Possibly tailored to segments (publishers, etc)

Dmitri: As always, we are going to get criticism, some valid, some not, about the the cost of participating in a WG, gatekeeping, the nature of standards organizations, and so on. On the one hand we can't solve all the woes or fix all standards bodies, but on the other hand we are one of the very few new CG/WG combinations that are putting forth a lot of effort to do maximum CG/WG cross-pollination and adopting the incubation process. The process is written into both charters. The idea is, you can start incubation anywhere on the web, FEP, wherever you like, and as there are champions and conveners and proposal gain momentum, there is a defined pathway to bring it into the CG and then the WG. Keep in mind we have the incubation process.

Ryan: As someone here who doesn't have budget, I don't have patience for people who get indignant about cost to participate. I don't buy that it's a big problem because the CG is free and there is the IE mechanism.

Dmitri: And joint CG/WG calls.
