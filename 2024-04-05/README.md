# SocialCG Meeting 2024-04-05 Call Notes

https://meet.jit.si/social-web-cg

## Present

* Dmitri Zagidulin
* Lisa Dusseault (@lisarue@mastodon.geekery.org)
* Emelia Smith (@thisismissem@hachyderm.io)*
* Angus McLeod
* Julian Lam (@julian@community.nodebb.org)
* bumblefudge
* Johannes Ernst (@j12t@social.coop, https://j12t.org/)
* a (https://trwnh.com)
* Angelo Gladding

## Agenda
1. IP Protection Note Reminder:
   a. Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
   b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
4. PROPOSAL: Advance ActivityPub-Webfinger profile to a draft report.
  - [list context](https://lists.w3.org/Archives/Public/public-swicg/2024Apr/0013.html) and [link](https://github.com/swicg/activitypub-webfinger)
  - initial draft state
5. PROPOSAL: Integrate the Security namespace into the Activity Streams 2.0 context document.
  - [list context](https://lists.w3.org/Archives/Public/public-swicg/2024Apr/0013.html) and [link](https://swicg.github.io/extensions-policy)
  - Web Security 1.0 is a widely-implemented context used for HTTP Signature properties in ActivityPub. It would make a good test case for the CG extensions process.
7. PROPOSAL: Consider an OAuth 2.0 profile for ActivityPub
  - [list context](https://lists.w3.org/Archives/Public/public-swicg/2024Apr/0013.html) and [link](https://codeberg.org/fediverse/fep/src/branch/main/fep/d8c2/fep-d8c2.md>)
  - One discussion that has come up during issue triage is aligning the different OAuth 2.0 profiles for AP. FEP-d8c2 lays one out; there are also suggestions to use OIDC's discovery mechanisms. Because we already have several profiles for using other standards with AP, and because OAuth 2.0 is the primary way for client applications to access API servers, I think it may be good for developers to have a report on current best practices for OAuth 2.0.
8. Announcement of the first draft of the ActivityPub and HTTP Signatures report
  - [list context](https://lists.w3.org/Archives/Public/public-swicg/2024Apr/0013.html) and [link](https://swicg.github.io/activitypub-http-signature/)
9. Forum and link-sharing task force
  - [list context](https://lists.w3.org/Archives/Public/public-swicg/2024Apr/0011.html)
11. Issues and PRs processing


## Minutes

### Introductions
* Angus McLeod - Involved in Discourse
* Julian Lam - Lead of NodeBB


### Main Agenda

Ryan: HTTP Sig initial report is ready for review!

Evan: A topic for this call is whether HTTP Dig Sig is ready to advance

#### PROPOSAL: Advance ActivityPub-Webfinger profile to a draft report.

Evan: now at an initial draft state, there's four open issues on github for the report. Addresses a lot of what we hoped it'd address with Webfinger.

Evan: My proposal / discussion is that we move this forwards to an official CG Draft, for wider public review.

A: We could finish the issues first - there are a few things to include but we could still add them later after it becomes a CG Draft

Aaron: Tried implementing, ABNF definition not very clear (more information, or regular expressions for username?). Introduction comes in with technical detail first, instead of a general overview which could be improved.

Aaron: A few references to local and external usernames, which don't seem to be defined.

Dmitri: Excellent feedback Aaron, good to open specific issues on the Github to allow the team to address.

Evan: Agreement on issues being opened, question for A, do we want to move to CG draft

A: No opinion, we could, or move to next month. (Agreement on moving to next month for a decision)

Aaron: I'd like to see another implementer for the draft, at least two implementations

Evan: I think the profile that's in the draft is best known by all the implementations in the fediverse. Maybe we need to include a list of the implementers in a non-normative section.

Aaron: (clarified by Dmitri): We need to go from the draft for implementation, instead of from existing implementations.

Ryan: Are CG Reports standards, or are they descriptive reports of standards in the wild?

Dmitri: This is a draft of a report, so even more informal. Evan, is moving to a draft inviting review?

Evan: Yes.

Dmitri: Aaron would you still object to moving to draft?

Aaron: No, that's fine. (no objection)

Dmitri: Calls vote for proposal to move to draft:

**Results:** No objections, Supporters:
- AaronNGray
- Dmitri Zagidulin
- Evan Prodromou
- Angus McLeod
- Bob Wyman
- ckolderup
- Ryan (snarfed)
- Lisa Dusseault
- Emelia Smith
- Johannes Ernst

#### PROPOSAL: Integrate the Security namespace into the Activity Streams 2.0 context document.

Evan: This is about bringing the Security namespace into the Activity Streams 2.0 context document. There's a few issues to be resolved.

Evan: Document is [here](https://swicg.github.io/extensions-policy/)

Evan: Proposal to the group, we go through this process for a popular extension namespace, other option is to wait for the extension policy to go to final before attempting to use the process.

Evan: So we go through the extension policy process for Security namespace.

A: Speaking of popular extensions everyone has to use, we have properties in the Activity Streams namespace, we have some that need to be moved into the context or extensions, and we could push some or all of the terms from the [Mastodon namespace](https://docs.joinmastodon.org/spec/activitypub/#contexts)

Dmitri: Make sure the terms from different cryptographic suites don't collide. It may make sense not to merge them into the main namespace so implementers can be explicit in which they're using, so different software can use different namespaces (v1 vs v2).

Evan: Responding to A, that would be fulfilling a need and testing the draft process. Hashtag and ?? have neither of those. Reason I suggested security is that it does have the documents needed for extensions process.

Evan: If it makes more sense to grab "unnamespaced items" to include in here, that's fine.

Evan: Hoping we can do one that shows good practices, instead of just adding "junk drawer items" (however useful) into the main namespace.

Dmitri: Should we pick a property or several, or do the security context as first extension?

Dmitri: Security v1 context is also kind of a long term running kitchen sink of properties, hence my relunctance about adding it to the main AP context.

[ break in scribe ] - [ I think I captured the essence above - lisa]

Evan: Adding a context document specifically for the "junk drawer" items would both show best practice and allow us to formally add those first

Bumblefudge: Is there a place for issues for migration conflicts, is there a central repo where people should open issues if context updates are confusing them, and gather migration issues? That works best if we can have one place to send people.

Dmitri: Context is tracking these so that repository ?? is right for it

Aaron: _in audible_ I think we need to be quite tentative with the ?? with the extensions, including mastodon, and look at which are best fit to start with.

Dmitri: If I understand Evan's intent it's that we set an example to the community of "this is how we do it". Not about adding everything that hasn't been added before.

Evan: Alternative proposal. Make report documenting the most commonly used undocumented / non-standard terms used in the Activity Streams namespace. Including a JSON-LD document, then we could include in AS2 context document, shifting it into the extensions policy process.

Evan: I'd be interested in taking this on.

Evan: (clarification): I'd be happy to co-edit it.

Evan: Withdraws security namespace proposal.

PROPOSAL: a report for documenting the most common terms used in the Activity Streams 2.0 namespace, including a JSON-LD context document.

**Results**: No objections
- Dmitri Zagidulin
- AaronNGray
- Angus McLeod
- Julian Lam
- Laurens Hof
- Bob Wyman
- Damon

#### PROPOSAL: Consider an OAuth 2.0 profile for ActivityPub

Evan: There is way via the C2S API to create data and read data, question is OAuth 2 is a popular way to implement client to server authentication, HTTP Sig is better for Server to Server. OAuth 2 is better for users on a server. OAuth 2 is a very big specification, lots of things that can be changed.

Evan: Providing a profile can help C2S developers going forwards.

Emelia: None of the software that does OAuth, AFAIK, implements according to C2S

Evan: I think there are such implementations?

Emelia: There are proprietary APIs that do use OAuth2, but they're specific to their products and not actually linked to the C2S API.  If we could get a list of C2S implementations, that could make the discussion easier.  The problem with the proprietary APIs, of course, is that other implementors need to play catchup when Mastodon (etc) changes their proprietary API.  We need to be clear what we're specifying there and not conflate the two things.

Evan: Our remit is not to document anybody's particular API.  I'll see if I can confirm Mastodon's use of OAuth for read-only access to activities -- are you sure they don't do that?

Emelia: The OAuth access is used to read the Profile object, which is not a standardized Actor object.

Evan: My question is still whether the OAuth authentication gates access to the things which are Activity Streams but I think we're getting into the weeds.

Dmitri: Even if there are proprietary APIs for client access that are gated by OAuth, I think Evan is proposing that we define OAuth for acess.

Aaron: I'd like to see something more abstract, for DIDs and anything else that comes into ActivityPub.  All these models like Hydra, we need a model that's compatible with these models, otherwise we're going to end up with a hodgepodge and security that's a nightmare.

Emelia: The reason I'm trying to make a distinction between the proprietary APIs and C2S -
we use these APIs at IFTest ? for building fedi ? and other things.  The old oauth approaches don't give you enough information, so rather than build on the old approaches, since OAuth 2 does provide more, we should buidl on OAuth 2, and perhaps write up what this means for the standard C2S and maybe also for the proprietary APIs.

Ryan: This is starting to make me feel a little uncomfortable, there is very little use of OAuth for the ABC (?)  C2S.  Writing up how to do this would be more normative than descriptive.

Evan: FEP already exists

Emelia: Yes that PEP exists but it is different from most implementations. It's maybe more similar to IndieWeb auth?  there are competing proposals in that sense.  There's discussion in the forums on that FEP specifically so it might not be ready to progress.  The discussions on scope are to the extent that the scopes may be too coarse and provide too much access.  For example some use cases only involve reading activities and don't require the full scope.

Emelia: Also OIDC, which is a very related specification - The Solid community has a specification on OIDC.  Maybe that's relevant.

Evan: I withraw the proposal

Emelia: One suggestion I have is to describe what authentication mechanisms an actor supports.  e.g. This actor supports OAuth2 with a standardized profile, vs this actor supports HTTP auth...

Dmitri: This sounds like a good place to start a mailing list discussion.

#### first draft of the ActivityPub and HTTP Signatures report


Ryan: I have the first version of the [ActivityPub and HTTP Signatures report](https://swicg.github.io/activitypub-http-signature/)

Dmitri; Let's all read through and then discuss on the mailing list, then put fourth a proposal to move to draft.

Evan: It's wonderful seeing this now ready it's one of the hardest things to implement. bravo.

#### Forum and link-sharing task force

Angus: I'm working on the Discourse activitypub integration, at FediForum we had a discussion about how we can better align the "threadiverse", which includes Discourse, Lemmy, Kbin, NodeBB, Flarum

Angus: Myself, Julian and others got together to discuss and swap notes for better data sharing via activitypub, and how we can better integrate with other AP software.

Angus: We decided we wanted to form a group for that goal, and that we want to propose creating a task force for that. Name for that task force would be "Threadiverse Task Force" (name is a little controversial), idea is to focus on "threads" in the forum sense, instead of the more timeline/chronological uses of activitypub.

Dmitri: Angus + everyone else, great idea, sounds like a good proposal

PROPOSAL: creation of a CG Forum and link-sharing task force (/ Threadiverse TF)

**Results**:
- Bob Wyman
- Damon says:+1
- Dmitri Zagidulin
- Laurens Hof
- Ryan (snarfed)
- Julian Lam
- Johannes Ernst
- bumblefudge
- AaronNGray
- Evan Prodromou

Discussion happened around group naming and threads vs threadiverse.

Julian: No objections to naming it the **Forum and Link-Sharing Task Force**

Angus: There will be a monthly cadence of meetings. Async parts of the task force will hopefully happen via the fediverse

Dmitri: let's start on mailing list, and calls, and define what you want to work on first.

Bumblefudge: is this testing focused, as to report upwards, is a valid deliverable. Deliverable ideas:
- Testing (johannes' work), are there subprofiles or extension profiles threads implementation vs microblogging implementation compatability

A: One point to bring up, not many difference on a grand scale between microblogging vs forum side, it's not good to have defacto standards, would be good to get a standard profile for Threads / forums / topics / contexts.

Dmitri: Calls end of meeting.

