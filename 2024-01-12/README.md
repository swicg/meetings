# SocialCG Meeting 2024-01-12

Archived on the W3C wiki: https://www.w3.org/wiki/SocialCG/2024-01-12/minutes

## Present

* bumblefudge
* Emelia Smith, she/her (@thisismissem@hachyderm.io)
* Tantek Çelik (@tantek.com) scribe for first ~35min then had to depart.
* ryan b (@snarfed.org)
* evan p (@evan@cosocial.ca)
* Lindsay W (lindsay.lintereur@gmail.com)
* Bob Wyman (@bobwyman@mastodon.social)
* Dmitri Zagidulin
* a
* Johannes Ernst (@j12t@social.coop)
* Angelo Gladding
* Philippe Le Hegaret (plehegar@w3c.social)
* Fredy (@naturzukunft@mastodon.social)
* Laurens Hof (@fediversereport@mastodon.social)
* Damon Outlaw (@damon@mozilla.social)

## Agenda

1. IP Protection Note Reminder:
  a. Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
  b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions (optional) and community announcements
3. Update on ActivityPub Editors Draft
4. (Proposed agenda item from Evan) Documentation Reports on: AP + WebFinger and AP+HTTP Signatures.
5. Continue the discussion of the proposed Extensions policy (https://w3c.github.io/activitystreams/draft-extensions-policy.html)

## Minutes

### Introductions & announcements

* ... from Starling Labs
* https://events.indieweb.org/ - see upcoming Homebrew Website Club meetups on Zoom
* Johannes, next [Fediforum](https://fediforum.org/) coming up March 19th & 20th! (Would appreciate pointers to interesting new Fediverse projects for the demo track)

### ActivityPub Spec updates

Evan:
We decided to take the existing errata that had been decided by the group, and publish a [new editor's draft](https://w3c.github.io/activitypub/).
I have done that work. We have an errata published as well as an updated editors draft.
One thing that I did was add a change log at the end. I reintroduced it to show what is difference between this and the Recommendation.
There have been some changes in ReSpec since we last used it.
It does not recognize this document any more.
I need to do a request to get us added back in so our editors draft keeps working.
Relatively painless process. If possible, we have a number of errata for AS2 Core & Vocab documents and I'd like to do a pass on updating those also.

Dmitri:
Thanks very much, that's incredibly exciting. A lot of developers have been clamoring for this over the years.

PLH:
Thanks Evan this is fantastic work.
For the ReSpec, we cannot re-add the Working Group because it closed. You should add the CG.

Evan:
Because it's a CG it changes to being a CG Report. I don't know if that's what we wanted to do as an editors draft. That was the main reason I had an issue using the CG rather than the WG.

PLH:
I still believe it should be the CG, as soon as you guys [want to] create a WG we can do that.

Evan:
I can set the CG as the responsible body, but still keep as Recommendation.

PLH:
It's not a Recommendation.

Evan:
Is this editors draft an updated Recommendation or do we mark it separately?

PLH:
There is a process to edit the existing REC if we want to which I would recommend you follow.

Dmitri:
What's the process?

PLH:
Making editorial changes to the spec is easy, making substantive changes is harder. I'm happy to navigate offline for editorial stuff.
https://www.w3.org/Guide/transitions/?profile=REC&rec=editorial

> "If there is no Working Group chartered to maintain a Recommendation, the Team may republish the Recommendation with such changes incorporated, including errata and Team corrections."

Evan:
Everything we've incorporated here is errata.

Johannes:
I would encourage us to avoid anything that downgrades anything from official standard to something less official. One of the things we have going here is that it is a standard and we should keep it going that way.
Secondly, I would be very much in favor in creating structures for us to make substantive changes.

Emelia:
To add to Evan's point. There is some housekeeping points to be done to the ActivityPub repo. Missing license file. Structure of the branches that may confuse or be different between AP and AS2.

(Emelia:
On licenses / license files:

* ActivityPub is actually on 2023 license, but misses license file is the repository.
* ActivityStreams is on 2015 license and now has a corresponding license file.)

Evan:
For PLH: these were published, AP and AS2 Core & Vocab were published before 2023, so they have links to the old license version, is there anything we need to do to upgrade to the new copyright statement and newer versions of the license?

PLH:
Yes, and I don't want to bother the group with the details.
Make a decision to yes we want to update the REC and then let Evan and I figure out how to make it happen.

Bob:
What does it mean to make a decision to update the document?

PLH:
People saying here to update it is good enough.
It is better to make the decision here to update it rather than just Evan and me.

Bob:
A WG would require more process and may exclude participation from some Community Group members...

PLH:
It is possible to have the WG reopened and not ignore the CG.

Evan:
Chairs, can we for our next meeting re-open the discussion on doing a WG?

Dmitri:
Let's add it to the agenda.
PLH, is it possible to do editorial updates to the spec without a WG?

PLH:
Yes it is.

Dmitri:
Goal is now when you look at the spec, you don't have to have multiple tabs open, you can just look at the editors draft.

Tantek:
To base the working group on the existing work happening async on the wiki on the scope of the WG (link)
https://www.w3.org/wiki/SocialCG/WG_Charter_Discussion

Dmitri:
Yes we should do that.
Next item, Evan on the amiling list, potential CG reports on usage of WebFinger and HTTPsig on/with ActivityPub.

Evan:
This conversation started based on [Marcos blog post](https://blog.mro.name/2023/12/implementing-federation-i/) on implementing AP and some of the difficulties he had.
One of the difficulties he had that almost every implementer will run into is understanding how to incorporate AP with the two other main standards we use HTTP-signature and Webfinger. there is folk wisdom, there are blog posts.

We don't have CG guidance on using these specifications with AP.
These are widely used, there are de facto ways these are used, so if we produced profiles, it would be extremely helpful for developers.

We have a mechanism for the CG to [produce reports](https://www.w3.org/community/reports/reqs/), officially produced by our CG, something we agree on, but does not rise to the level of Recommendation as a W3C level.

It seems that providing profiles for Webfinger and HTTP signature would be a huge help for the AP implementer community and would fit well for our CG area.

Dmitri:
Thank you Evan. that would be a fantastic idea. and you're absolutely right, anybody who tries to implement goes through a trial by fire.

Emelia:
There is also an open item for writing an FEP or something for giving very clear guidance for how to support not just the version of HTTP signature that Mastodon is using but also to support the latest drop from the IETF. Those are very different. At some point we will have to have people upgrade to the official published version.

Dmitri:
You're absolutely right. We should as a community talk about potential migration.

Johanness:
I'm working a test suite and the identification of what's a valid test and what is not is left up in the air because these documents are up in the air. How can we test WF and test AP because that doc doesn't exist anywhere. A spec needs to exist that defines this connection.
There are other de facto conventions that people do that are not documented that we should document as well.
I would prefer we have documentation of how we use HTTP signatures the Mastodon style as a baseline, and then a new document that describes an upgrade path for how we can do it in the future.

Dmitri:
Good point Johannes.

Evan:
It would be much better for the implementer community, rather than jumping to the this is the better way to do it but not work with the fediverse as it exists. I strongly advise we document using draft cavage 12, it's not a great idea to do it and use it as the basis for ....

Tantek:
I like this pattern of documenting existing patterns; appreciate that dynamic here. Other things in similar categories we'd want to consider:

* Mastodon popularized `rel="me"` for "verified links". Is there interest in this group to similarly document this mechanism, so that others in the community can use it?
There's a spec, but no precise step-by-step mechanism such as what Mastodon does. So my question is - would it be valuable to document / specify that.

Bob:
Would be great to have the documentation first rather than updating the spec itself ActivityPub.

Dmitri:
This would be in parallel rather than in AP. It's used by services that also implement AP but kept separate

Bob:
Yes keep it separate.

Emelia:
Another thing with various things that are implemented in federated software is authorized fetch or how HTTP signatures are used in that context and the trust & security that can bring.
HTTP signatures can be "forged" to circumvent domain blocks on servers and defederation of servers.

Johannes:
I would suggest that what we want to end up with is a stack of documents and we can hand it to peopel and say implement this and you will be done.
Rel-me should be part of that stack.
I don't know what else should be in that stack of documents.
We can also evolve this as we come up with new standards.

Tantek scribe note: have to run soon. Please pick a new scribe :)
Bumblescribe is done being interrupted

(Thank you all)

Evan: [gesticulates wildly] I think 1:1 profile<>CG report is a good mode to work in, rather than many-to-1. Also one editor per report would help, get everyone in there!

Dmitri: +1.

a: i think we need a target and a definition of done, or else this pile of profiles might not be enough.

evan: that wasn't my intention, this stack of profiles definitely wan't be done, the ecosystem will likely grow and evolve before we're even done. each test suite will need to pick a subset or superset of those.

bumblefudge: I was going to say the same thing - every Test Suite is a few core specs, and a stack of additional profiles. I also think that microblogging profile is just one - there's also a podcasting profile, stuff like pixelfed, lemmy, etc. If we do the microblogging one really well, otbher people will copy that and add their own profiles to the stack for their interop targets.

johannes: i didn't mean to imply a def of done, just a minimuum threshold!

Dimtri: Credentials Community Working group has a lot of specifications relevant and people in common, and is discussing AP on 13Feb, Tues, 9am PST/12 EST/ 6PM CEST at https://meet.w3c-ccg.org/weekly

Evan: Putting two proposals into chat:

1. PROPOSAL: CG will create a draft report for a profile of Webfinger for ActivityPub with (one or more  CG members) as editor.
2. PROPOSAL: CG will create a draft report for a profile of HTTP Signatures for ActivityPub with (one or more  CG members) as editor.

let's poll these now:

1. 10 votes of 16 people present.
2. 8 votes for, one vote -0, out of 16 people present.
    * "-0" vote was to express concerns about current common practice/legacy use and its insecurities, which the CG should be careful not to endorse or ossify
    * Part of the goal of the draft report is to document these issues (I think Evan or Dmitri said this)

Dmitri: Other thing on agenda is more discussion points on the Extensions Policy. https://swicg.github.io/extensions-policy/

Evan: We agreed at last meeting to publish it eventually as a draft report for the CG. I broke it out from the ActivityStreams repository, and is now part of the SWICG organisation as a repository. Links will redirect correctly. Identical to last thing we discussed, only change was to versioning and how we version. We have these special "versions" for the namespace (?) if you need an identical copy for the document.

Evan: If we did a recommendation for an extension proposal, we should mock the process and prototype an extended AS vocab before adding things to the main one.

The typical graph document is ... for extensions, we should think through how to include extensions in the namespace.

Bob: You mean like making a chess-moves context file and having a few implementations use it? I feel like maybe the AP space is a little stuck in a microblogging rut, it might help model the extensability model. security is "doing the same thing better", while a feature not everyone needs or wants is a more traditional extension topic.

Ryan: +1 to bob. i think the space is starting to move beyond microblogging with groups, longform, content curation, etc. interop is

bumblefudge: This conversation and the previous one could go together. We've been talking about profiles of specs, but not everyone needs every piece of new specs. Like groups for example - not all implementations need them. So that could be a standalone interop profile (+ a few FEPs).

[in chat] Damon Outlaw says:I believe it is more a cultural issue than a technical one in terms of encouraging innovation. Interop is for sure the needed focus

Dmitri: +1

Evan: Chair action needed to publish extension policy as CG note? Last time we just voted to start it

Dmitri: yeah we can push the button and call it a DRAFT report until the group ratifies it as done/acceptible

Emelia: I think the policy implies a FEP author stepping up to an issue/topic is a required step, do we need a tag for that in github? How/where does an issue champion declare themself?

Evan: `fep solicited` sounds like a legit github tag to me. there's also the [fediverse-ideas](https://codeberg.org/fediverse/fediverse-ideas/issues) repo, which is a place where people can start a conversation or mold a socialhub conversation into FEP shape

Emelia: where exactly so we yell into the crowd of people "SOMEONE PLEASE WRITE THIS FEP", tho? socialhub? SocialCG github? fediverse-ideas? fediverse itself?

Dmitri: delete ack/nack topic as test case/starting point? [github issue](https://github.com/w3c/activitypub/issues/406)

Johannes: I would advocate less documents than more documents in the lifecycle/workflow? are we formalizing a step and making makework here?

a: start from existing docs, even? e.g. [mastodon](https://docs.joinmastodon.org/spec/activitypub)

emelia: one thing that would help is knowing that we're doing this process in the right place and that this work will actually get used.  i asked [on the fediverse](https://hachyderm.io/@thisismissem/111744245834534737) if we have any buy-in or commitment to use the form of moderation-infra we're designing here and it would be a great motivation boost if what we're working on is actually going to get used.

dmitri: and we're over time! thanks all, take further thoughts to the list and the fediverse.
