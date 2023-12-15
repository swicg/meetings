# SocialCG Meeting 2023-12-15 Minutes

## Present
* Dmitri Zagidulin
* PLH
* Evan P.
* Lisa Dusseault
* Bob Wyman
* Steve Bates
* Johannes
* Angelo Gladding
* Juan Caballero

Scribe: Lisa

## Agenda
1. IP Protection Note Reminder:
  a. Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
  b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. A few words on the Joint SolidCG/SocialWeb CG call this week (call minutes over at https://github.com/solid/specification/blob/main/meetings/2023-12-05.md )
3. Continue the discussion of the proposed Extensions policy (https://w3c.github.io/activitystreams/draft-extensions-policy.html)
4. Issue processing as time allows (spec issues marked as "need group input")

## Minutes

### Announcements

Evan: Threads is on the Fediverse! A small group of Threads users is available to follow on the Fediverse.
It's a small step, but very promising. I'm optimistic that they're moving in the right direction!

Johannes: I've been observing from the outside while you all created the standards, and it's been a lot of tough work. So this is an incredible accomplishment, that somebody like Threads comes along with 100 million users and starts to implement! This is worth celebrating.

Secondly, quick announcement, I have a developer survey on the Test Suite that we're starting to implement. Survey is on - what dev environments do people use, to help figure out what virtualization tech we can use. 24 responses so far. [Link to survey form](https://apps.dazzlelabs.net/nextcloud/apps/forms/s/ed2WBPzrrWFcWKjT5a9MwMGp).

PLH: W3C is now using [w3c.social](https://w3c.social/) [not just primarily but exclusively for micropublishing](https://mastodon.social/@w3c@w3c.social/111534700235620053)!

Evan: Would it make sense for SWICG to get an account on w3c.social?

PLH: Yes, let me check on the details. [Coralie](https://w3c.social/@koalie) / k @ w3 dot org is the person to contact about all things w3c.social

Johannes: Next FediForum (online unconference for the Fediverse will be on March 19 and 20. [More info and registration](https://fediforum.org/).
The entry of Threads (and corresponding press coverage) to the Fediverse will make people sit up and notice who haven't been part of the community, and a place like FediForum is a good place where to make connections and learn.

Dmitri: Summary of solid<>socialCG call 2 weeks ago - overlap of experience and complementary foci

Evan: I have a hard time with this. We've had different tech approaches to the same topical domain (making social software, etc). My concern is - is there a point of convergence, rather than crosspollination? Is there a way we can bring the two specs together in a forward path, instead of continuing along two track?

Dmitri: That's not entirely clear yet. At the very least there are some implementations being worked on actively that make solid work with AP as specified today [such as this project's lead dev who attended the call](https://github.com/assemblee-virtuelle/activitypods)

Dmitri: Editor's draft incorporating all of Evan's errata work to date? Easiest path forward to living spec and latest word

Johannes: Now there's a large amount of success with the spec (and number of endpoints supported will go up rapidly), the time is to focus, deep rather than broad. Lets focus on DX. From my perspective, we should come up with a roadmap - this is what we want to accomplish, and try and get main implementers to commit.
I'm also a strong proponent of re-chartering (having a WG), since this will increase the likelihood.

Evan: I can commit to prepping an Editors Draft by the next meeting, with the errata incorporated.

### Topic: Extensions Policy

https://w3c.github.io/activitystreams/draft-extensions-policy.html

Evan:  There's a new context doc for streams.  We put this off and it's been a loose thread for us for a time.
The draft threads document proposes how we would integrate those into the streams.  Activity streams
is an extensible vocabulary.  This does not say how extensions are written or how they should be used -
anyone can write, publish, implement.  This is about how we can take the most _popular_ extensions and
help implementors tackle them.  There's some work on how extensions can work, and advice on why it may
be advantageous to include those in the main document.

Dmitri: What's the next step? publish and ask for wider review?

Evan: I think the goal here is to publish in the CG as a CG Note.    That's not using the formal process
the W3C has.  This has been available 3-4 months. I've incorporated some of the comments that have come in
as GitHub Issues - but there hasn't been much objection. The framework is pretty straightforward.  It's up
to us, the SocialCG, to make a decision whether to include a vocabulary in the main streams document.
There are guidelines (min # implementors, documentation, own namespace, meets W3C IP requirements) to be a well-structured extension.  Next step might be an "intend to publish" statement to ask folks to get their
questions/issues in now.

Dmitri.  We'll publicize an intent to publish.  I agree the criteria are flexible but there's still a bar
to meet.   This ought to clear up some of the questions developers have when working on an extension.

Evan: I'd like to propose this language: "PROPOSAL: The SocialCG intends to publish the extension policy at
https://w3c.github.io/activitystreams/draft-extensions-policy.html
 and solicits final round of feedback from the Activity Streams 2.0 community. "

Dmitri: Consensus Call.  Resolved.

### Topic: Issue processing.

Evan: Last time we did ActivityPub issues, maybe we can do the outstanding issues for Activity Streams this time.
Looking for PRs specifically focused on errata.

(Ed. Lisa: Discussion that recapitulated what is in the following issues on github has not been added here, please view the issues.)

[PR 440](https://github.com/w3c/activitystreams/issues/440) - We have a Tombstone object.  One property of it is the item's former type.    Propose to accept this PR which adds an erratum about the former type property range.  Consensus called. Resolved - accepted.

[PR 441](https://github.com/w3c/activitystreams/issues/441)  We have an issue but not an erratum for this.  Seems pretty obvious to resolve as proposed (to add context to example).  Accepted.

[PR 545](https://github.com/w3c/activitystreams/issues/545)  Just a typo - let's fix.  added to errata and updated editor's draft.  Accepted.

[PR 482](https://github.com/w3c/activitystreams/issues/482)  Spec has a conflict between language about "singular" vs "one or more".  The PR rationalizes to, bto, cc and bcc to have a uniform structure.  Accepted.

### New topic: getting feedback from Threads implementors

Johannes: Is there anything special we can do to gather input from these folks who are probably

Evan: Standards communities are open, safe spaces.

Lisa:  100% agree on the ideal of safe spaces, but honestly standards spaces are not always safe.  I've seen before
when all the official input to standards did happen in open standards groups, but private groups also existed
(IETF and CalConnect, for example).  It's pretty normal for anyone to be able to talk to an editor or contributor who is
directly involved and try to convince them of some case, but the results of that are of course up to the real
contributor.

Evan: we do always have to be careful that side orgs don't cause side agreements.

Lisa: Yes and; not reaching out to implementers doesn't prevent such side agreements.  (ed: sorry for the double negative.)

Johannes: we could have a meeting just for implementers and give them each the mic for 5 min or so.

Bob Wyman: There have been comments about major implementers being more important than others.  I counsel against such things. Imagine you're a "minor" implementor working hard to make it work, and are told your input isn't important.  Every time we talk about "major" implementors we spit in the face of people working very hard.

Angelo Gladding:  I've been working on this; I can grab profiles from many sources but for some reason that doesn't work with Threads yet.  I am a small implementor, the smallest implementor!  There has not been communication from Threads, ...

Evan: Threads has a bug.  They're only returning profiles after signatures when they're needed before signatures. It's been reported to them, hopefully they can fix it soon, they're aware.  It works for people who are using HTML signatures.

Bob: and it's working only for 3 accounts so far.  It's a very slow rollout of the connection to AP.

Evan: They are erring on the side of transparency, telling us what's going on before they have all the answers and
documentation.

Angelo: They've been talking to individuals but not coming to the community.

Dmitri: Yes and there was history contributing to that.

Johannes: For folks who don't know, their roadmap (as repeated by Mosseri in a video this week):
* First is ability to follow a small number of Threads accounts of Meta employees from the Fediverse, without ability to interact with them (info does not flow back to Threads). This is what we are seeing this week.
* Then open this up to more accounts
* Then propagate likes, comments from the Fediverse back into Threads
* Lastly allow Theads to follow fediverse accounts.

What this means is that we're nowhere near "alpha" and it will take most of 2024 to get to the last point.

Bob: You said this was going to happen over 2024?  I think they have not committed to dates.

Johannes: yes, no commitment (it's software!)
