# February SocialCG Meeting 2025-02-07

Archived: https://www.w3.org/wiki/SocialCG/2025-02-07

https://meet.jit.si/social-web-cg

## Present

* [TallTed // Ted Thibodeau](https://github.com/TallTed/) (he/him) <https://mastodon.social/@TallTed>
* Dmitri Z.
* Bob Wyman
* Darius Kazemi
* Eric Fassbender
* [Melvin Carvalho](https://melvincarvalho.com/#me)
* Angelo Gladding
* Lisa Dusseault (@lisarue@mastodon.geekery.org)
* Aaron N Gray
* [Johannes Ernst](https://j12t.org/)
* a <trwnh.com>
* Ryan Barrett <snarfed.org>
* [elf Pavlik](https://elf-pavlik.hackers4peace.net) (Solid CG)
* Tantek Çelik (@tantek.com)
* Jeremiah Lee ([@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah)) (he|they)
* Emelia Smith (@thisismissem@hachyderm.io)
* Evan Prodromou <acct:evan@cosocial.ca>
* Alex Kulikov (@alexeyqu@mastodon.social)

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
5. Vote on the [proposed CG charter](https://swicg.github.io/potential-charters/CGCharter-1727386911.html)!
    * (This kicks off a 14 day Call for Consensus period for comments and objections on the resolution made during the call.)
6. Task Force Updates
7. Discussion and issue processing.
8. FOSDEM report out?
    * Recording of Jeremiah's demo in Social Web BOF: https://alpaca.gold/@Jeremiah/113956388721652990

## Minutes

### Announcements

Emelia: IFTAS is looking at drastically reducing operations by Mar 30th, unless they raise more money. If anyone knows how to connect them with funding, please help. [link](https://about.iftas.org/2025/02/06/funding-challenges-and-the-future-of-our-work/)

Evan: On March 9-10 at SxSW festival in Austin TX, Flipboard and the SocialWeb Foundation are hosting a Fediverse House!
Also Bluesky and ATProto work [link](https://about.flipboard.com/fediverse/fediverse-house-2025/)

Elf:  I've been working lately with the team from [ActivityPods](https://activitypods.org/), they've been implementing both ActivityPub and Solid. We start working on a report that might be useful to this group here: https://github.com/solid/activitypub-interop

Johannes Ernst: the 5th  FediForum is coming up, April 1-2nd! More info and registration: https://fediforum.org/ . Same format: unconference and demos. Meet your fellow social web enthusiasts and start new things together!

### Main Agenda

Dmitri: We've been setting up a Community Group charter since the CG has been operating without one. We've discussed this over the past few months, now we think the charter is in pretty good shape to vote on adoption of the [proposed charter](https://swicg.github.io/potential-charters/CGCharter-1727386911.html). Fairly boilerplate, based on a W3C CG charter template. Today we want to vote on a resolution to adopt it, which kicks off a 14-day call for consensus/comments period that is publicized to the mailing list, socialhub, fediverse, and other places where people might want to see it.

Emelia: I see the section "out of scope TBD", do we want to delete it?

Dmitri: there's a [pending PR](https://github.com/swicg/potential-charters/pull/63) around scope. The resolution is to adopt the charter as-is assuming the two issues are resolved. One is the pending PR just mentioned, another is clarification on language around "champion" and "convener".

Emelia: Can we just vote to merge #63 since it's a one line change?

Dmitri: I see plus ones and no objections, let's merge.

Emelia: Can we get a link to the Github repository in the charter itself?

Dmitri: Yes, can you open an issue please.

(PR 63 is merged)

Melvin: In the charter I don't see SocialHub mentioned. Is that intentional?

Dmitri: No it's not left out intentionally. We mention it in the incubation steps (aka staging doc) that we are part of a larger community.

Aaron: I see no mentions of AI. We need a task force, we are going to need to whitelist things re: moderation.

Dmitri: That sounds like a great proposal for a task force, which we have a procedure for. We can add it to the agenda and discuss at the end of the call.

Bob: No need to list everything out in a closed list of discussion topics. Nothing in the charter precludes an AI task force.

Tantek: For the out of scope section, I haven't seen any discussion in this group about blockchain or cryptocurrency based social solutions. Is that something we would simply not mention in the charter, or do we want to explicitly call it out as out of scope?

Bob: I strongly prefer that the particular technology of blockchain not be mentioned in the charter. No reason to elevate that particular set of issues into the charter right now but they can be dealt with as they may come up in the future.

Ryan: I agree with Bob. I'm not personally a big fan but I want us to be able to discuss DSNP or Farcaster if there's anything to be learned from them.

Emelia: We don't need something that says blockchain is specifically out of scope, but we may want to say something about protocols that are non-W3C. Like the intent of the group is for W3C protocol discussion -- if you come in talking about ATProto, sure you can discuss it but you can't expect it to be on topic.

Dmitri: Do the main paragraphs in the scope of work section address what you said?

Emelia: Yes-ish. We also want to say that things that aren't going to be W3C standards or reports or group output aren't going to be in scope.

Dmitri: We do have a very explicit staging process document. Theoretically if someone like ATProto was interested in standardizing they can go through the community process.

Melvin: Replying to Tantek - I am highly sympathetic to his point but I do think that within the blockchain space there are some good bits and the main thing we can benefit from is a global ordering system. They are an instrument to sell tokens and there are de facto royalties which is against W3C policy generally.

Evan: Understanding that Tantek has made a proposal, I wonder if he might consider a rewritten proposal.

Darius: There is a problem where if we add things to the out of scope list, the more we add the more someone might say "because my pet issues isn't in your out of scope list, I have a right to talk about it here".

Emelia: (scribe didn't catch this)

Tantek: I think I got my answer which is that it sounds like there's rough consensus to just not mention blockchain or cryptocurrency explicitly for various reasons. I'm fine to go along with that.

Angelo: I've raised this twice now and haven't gotten much response other than consensus was already reached. You introduced this as the primary substantive changes from the template are scope-related, but there's more in the Chair election process. It's hard to decipher from the commit log. I put together a page on it: https://ragt.ag/socialcg/cg-charter . Specifically what does it mean to be a "discursive" member? Also there are changes to the way Chairs govern this group compared to other groups. (Also mention of the "Solid process" being unclear)

Emelia: What if people who run for chair say what their primary focus is, and then we have find a way to make it so there is a chair from each major community. As far as the discursive language thing, Darius noted it's no longer there. In other contributing documents we do have language that states contributing guidelines for groups.

Dmitri: We do straight-up link to the contribution documents by reference so it's inherent in the charter.

Bumblefudge: In previous conversations this was done intentionally but not formally. There was an informal desire to have the specs under maintenance to be understood really well by one of the chairs. I don't know if it needs to be formalized into the charter to keep happening on a good faith basis, like if we were numerically voting and a bunch of people from one ecosystem came in and got all the top votes. We could simply ask one of them informally to make room for someone from a different ecosystem. But I don't think we need tribe representation among the chairs, it's more of an editor role than an author role. A chair's primary role is to be able to resolve conflicts and understand tradeoffs.

Evan: I want to ask 2 questions of Angelo. Do you feel like you or others cannot approve of this charter with the text as it stands? If that is the case, would a change log with some bullet points that say what the changes from the boilerplate were, would that suffice to overcome your objection?

Angelo: I still don't think I've heard what the "Solid precedent" is? If the changelog was better I would probably understand the "Solid precedent" is.

Dmitri: The "Solid precedent" just means we are taking inspiration from the Solid group for chair election.

Emelia: I was involved in the Solid side. What we were trying to do was to ensure that the ecosystem was well represented and that a single company or organization didn't control the entire specification for Solid.

Evan: If there are specific objections to the document as it stands, I'd like that to be noted. If the changelog is the problem and how we got here is the problem we can address that later by providing a better changelog perhaps.

Dmitri: Angelo, are your concerns about the specifics of the Chair selection process a blocking issue?

Angelo: I could propose a PR to remove things and put it back to the default. But there's a room full of people who seem to think the Solid precedent is the way to go. But there's not good enough documentation to formally justify this. 

Emelia: If you're concerned about this I suggest reaching out to the chairs of the Solid CG and ask them why those decisions were reached.

Melvin: I was first chair of the Solid CG. I personally was not terribly happy with the charter document we landed on. We ended up in a place where the there were three chairs were, or had previously been, employed by the same firm.

Elf: I will respond quickly to the solid CG -- the charter has been mostly edited by Sarven. We approved it a year ago, recently Virginia stepped down. (Sorry, scribe couldn't keep up with this bit of discussion and lacks context)

plh: I want to say that we have been waiting  for this CG to produce a WG charter since 2023. W3C may come up with a proposed WG charter if this doesn't move ahead at the CG level.

Dmitri: calling for a vote on the understanding that this isn't final and changes can happen.

Emelia: are we going for 100% consensus or majority consensus?

Dmitri: rough consensus minus formal objections that can be taken up with w3c staff.

Dmitri: **PROPOSAL:** Adopt the Proposed CG Charter (at 
https://swicg.github.io/potential-charters/CGCharter-1727386911.html
 ) as this group's charter, with the understanding that PRs and conversation on it can continue. 
 
 Dmitri: lot of +1s, -1 from Angelo, -0 from Melvin, 0 from Aaron.

Votes: 

- Johannes Ernst: +1 
- Evan Prodromou: +1 
- Bob Wyman: +1 
- bumblefudge: +1 
- Jeremiah Lee: +1 
- Ryan Barrett: +1 
- Aaron N Gray: 0 
- Dmitri Zagidulin: +1 
- Angelo Gladding: -1 
- Melvin Carvalho: -0 
- Emelia Smith: +1 
- Tantek Çelik: +1 
- Ted Thibodeau: +1
- Aurélien: +1 
- Darius Kazemi: +1
- Lisa Dusseault: +1
- a: +0
- elf Pavlik: +0 (as not active participant)
 
**Results:** thirteen +1's, two +0, one 0, one -0, one -1, two abstains. Rough consensus and one formal objection (Angelo).

Angelo: Yes, formal objection is to the change to the W3C template regarding chair selection for this charter.

Darius: disagreeing with you is not ignoring you

Evan: Reiterated concern that charter is needed by March

Emelia: given the immediate need for a WG charter, can we convene this meeting weekly or every other week for the time being to make sure it happens?

Dmitri: Good idea, I'll put it to the mailing list.

Dmitri: meeting is being extended by 5-10 minutes. Any last words of advice from plh with regards to this situation in terms of how to procede? Angelo are you raising a formal objection?

Angelo: Yes

plh: It's a CG, so I don't know what you mean when you say there's a formal objection. It is not part of W3C process.

Dmitri: Jitsi recording stops after 1 hour. The meeting is continuing due to importance of topic and minutes will record the conversation.

Dmitri: **PASSED: PROPOSAL:** Adopt the Proposed CG Charter (at 
https://swicg.github.io/potential-charters/CGCharter-1727386911.html
 ) as this group's charter, with the understanding that PRs and conversation on it can continue. PENDING async resolution of the objection from Angelo. 

Votes:

- bumblefudge: +1 
- Tantek Çelik: +1 
- Aaron N Gray: +1 
- Evan Prodromou:+1 
- Emelia Smith: +1 
- Angelo Gladding: +1 
- Darius Kazemi: +1 
- AaronNGray: +1 
- Bob Wyman: +1
- Jeremiah Lee: +1 
- TallTed: +1

**Results:** Full consensus