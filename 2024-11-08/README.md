# November SocialCG Meeting 2024-11-08
Archived: 

https://meet.jit.si/social-web-cg

## Present

* [Dmitri Zagidulin](https://social.coop/@dmitri)
* [Ryan Barrett](https://snarfed.org/)
* [Tantek Çelik](https://tantek.com/) (@tantek.com)
* a <trwnh.com>
* Lisa Dusseault (@lisarue@mastodon.geekery.org)
* Bob Wyman <@bobwyman@mastodon.social>
* [Nigini Oliveira](https://social.coop/@nigini)
* Emelia Smith (@thisismissem.
* Evan Prodromou <acct:evanp@socialwebfoundation.org>
* [Eric Fassbender](https://wellrestedmango.com) (@fassbender@sciences.social)
* [Darius Kazemi](https://friend.camp/@darius)
* [Matthias Pfefferle](https://mastodon.social/@pfefferle)

# Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
    - IndieWeb Berlin! https://indieweb.org/2024/Berlin
    - ActivityPub Trust & Safety Taskforce's next meeting: 11:00am East Coast US / 5pm Central European time on Tuesday 12th November.
4. Location task force proposal (Mike, Jeremiah, Evan) from [Fediforum session](https://fediforum.org/2024-09/session/7-b/)
5. Social Web CG Charter discussion 
6. CG to WG Work Items Staging Process discussion 
7. Potential Working Group charters discussion.
9. (if time) Group TF
    - Rigorous definition of Group/Join/Leave/members/inbox/outbox etc.
10. (if time) brief recap from Forum TF meeting yesterday (Darius)
11. (if time) C2C protocol TF -- https://lists.w3.org/Archives/Public/public-swicg/2024Nov/0010.html | document protocols built on top of ActivityPub, including how to negotiate protocols client-to-client or actor-to-actor. signalling server behaviors, client behaviors, actor behaviors. generating one or more reports for possible profiles.
  - defer to next meeting, see mailing list for further discussion

# Minutes

## Intros
## Community announcements
## Location task force proposal

Evan P: Initally proposed during FediForum, geospatial related ActivityPub objects. Including location as part of social experience, part of AP. The idea is to synthesize location-based ideas into a Report.

Anyone that has experience using a geospatial-based application (Swarm, etc), it's a fun and exciting way to do social.

Evan P: Also, we're about to adopt a CG charter, and as part of it, it includes a staging process (for incubating specs). We can use the Locaiton TF as a great testing item for this process.
Let's stage it until then.

Bob Wyman: Yeah, there's exciting opportunities there, in geosocial. There's some fundamental under-specification in that area (no default units for Altitude, or a place to specify the coordinate system, etc). Also support for non-Earth planetary location systems. These are fairly low-hanging fruit.

Dmitri: Any objections re tabling this til charter is approved?

Bob: Any reason for that? We can do it in parallel.

Evan: I'm excited about the new staging process, and I'd want to see us test it out! This is a juicy bundle of functionality, great test case for it.

Emelia: May I suggest that instead of just taking one task force (Location), we can just apply the staging process to all Task Forces?

Dmitri: As always we need volunteers to lead this effort. Do we have volunteers?

Evan: We have some people, but I'd like to wait for the staging.

Dmitri: We can parallelize.

Emelia: What makes sense is that the task force will only be needed when we have issues to address.

Evan: We can vote on the proposal to wait.

Dmitri: My suggestion is to change the proposal to not start the task force.

Tantek: There are [recommendations](https://w3ctag.org/explainers/) to how to structure/start an effort and then bring it up to the meeting to push forward.

Dmitri: This is relevant to one of our next items (which is the staging process), since Stage 2 requires an Explainer.

bumblefudge: Explainer will be a really helpful template! I would like to volunteer to start that.

Emelia: In order for us to have a TF, we want a Staging Process. But TFs by themselves don't produce official documents (or don't have to). THe majority of the work is in meetings, issue triage, explainer, etc. So setting up a TF does make sense meanwhile? 

Evan: Change my mind, let's do a geosocial TF, and move on.

Tantek: Starting an explainer is very aligned to Stage 0, can be done async. Adopting explainers is useful beyond Geosocial etc. As long as you're not creating technical proposals, you're free of IP protection restrictions (IANAL etc.)

Evan: Let us finish it up via email.

RESOLVED: Proposal to form a Geosocial Task Force. (Next steps: Mailing list post about its formation etc). 

Dmitri: Let us talk about Charter. We have this [potential-charter](https://github.com/swicg/potential-charters). Everybody should take a look: we have 3 main tasks.
1. read through it (as you can see by the highlighs, we need to fill it up) please read through the PRs and vote.
2. as part of this: we have a proposal for the stage process. Reading through this, it doesn't quite address the Task Force, when it is actually formed. I encourage PRs on this.

bumblefudge: this Staging process was forked from a WG that doesn't really have Task Forces, but uses Champions & drafts instead. So one way to think about TFs is just -- it's a recurring special topic call that works on documents, and documents have Champions per the staging process. So that would be an informal way of treating TFs, not enshrining it in the charter or staging process.

Tantek: +1 to bumblefudge about -- the Staging proposal works as is, and Task Forces can just work within that. I trust this group to organize/come up with stuff as a whole.
But, what I queued for is -- the one high level concern I have about the CG charter, which I wanted to bring up on this call specifically, is the Decision Process. In general, it's good, I agree with the async provision (that people can follow up on mailing list etc.) My concern is -- I don't think that (at least in our case), that the email list is the best way to do follow-up discussion. I don't want to have a fight about the email list on the email list. :) 
So, my historical concern is -- when this was established earlier, we had a lot more participation and diversity on the emailing list. And now the mailing list is a smaller set. Not sure how to have a productive discussion for this.

If you were to ask me for a counter-proposal, how about Github issues? 

Evan: two notes -- one about the Staging Process and Task Forces. 
Currently, when we create a TF, it 1) creates a Github repo for the TF, to collect issues, have discussion. 2) Identify leaders (Champions in the staging doc parlance) to write a report, or make test suites, etc. 

Both of those things happen at Stage 1 in the staging process doc. So that maps pretty closely to TFs. The only thing that's not mentioned in the doc is meetings (like special topic calls).

Second thought re async comms: We do have other venues, like [Mastodon](https://w3c.social/@socialcg).

Dmitri: My proposal is gonna be, let us go with plurality and add that section in the charter on the decision process. So, multiple venues - mailing list, Github, Fediverse, SocialHub forum.

Tantek: minor add to your proposal, I'd include everything, but we should communicate a canonical thread of discussion, preferably a GitHub issue.

Emilia: Currently there is no mention to licensing. Sounds like important to add in stage 0 a mention to the default W3C process.

Dmitri: Every single group I participated struggles to accept the GitHub PR as the cannonical discussion thread. I hear that some people have difficulties with adding comments to issues and PRs. I personally would like that to be the case, but is that setting us up to exclude people.

Tantek: Some groups have decided to use email lists. I do concur with the value of inclusiveness.

Dmitri: Do you think that the space (GH or email) influences how people behave?

Tantek: I am still to see detrimental threads in GH.

Bob: It would be fabulous to have a cannonical place. There are a lot of places to discuss ActivityPub, and some people has ownership of them, and centralizing it would create social issues. Another thing is GH is seen as evel for a good number of members of our community. 

Dmitri: I am glad you brought the social issues of centralization... it is going to be a process. It would be nice to use some ActivityPub powered space.

Dmitri: In a similar vein, Group Charters, please read the current GH proposals, and add your contributions. Any questions before we move on?

Evan: In terms of ordering of this charters, one way, first we finish one of them and get approval from the W3C. Relationship between community and charter: it would be wonderful to get the community charter done first.

Dmitri: 

Evan: Do we have a preferred schedule do deal with the charter: weeks, months? 

Dmitri: Earlier is better. Because of the rush of the end of the year, should we move it to January?

Emelia: Should we do the ??? issues triage meeting?

Dmitri: How do people feel about January? (I am assuming tumbs up are for January)

Emelia: I'd propose December?

Dmitri: Any objections? NO. (ran a chat vote! All +1!)

RESOLVED: Aim to adopt the SocialCG Charter on the December call. 

Dmitri: Let us talk about Task Forces. Interest to Group Task Force, overlap with Forum? And there is the Client-to-client efforts. Darius, could you summarize the Forum conversation?

Darius: I don't have a great memory of the meeting, I am pulling up my notes.

Dmitri: Reminder, this is a landmark moment: Long posts presenting well in Mastodon.

Tantek: I want to volunteer to co-chair HTML Discovery TF.

Evan: Me too.

Tantek: Should I submit PRs?

Evan: I will add you to the GH admin.

RESOLVED: Evan and Tantek as HTML Discovery TF co-chairs

Dmitri: Back to Task forces.

a: last time we mentioned a Group Task Force. I am not sure who is interested but I am and i think evan said as well?

Dmitri: I think the Fediverse badly needs that, but is that different enough from Forum?

a: I believe so: what is the AP to join/leave a group? what are the specific behaviors?

Dmitri: Let us run a proposal.

a: We could definitely collaborate, but I don't think it should be the same TF.

Evan: I'll co-lead!

Darius: Agree with a's in not merging TF.

Dmitri: Formal proposal... all +1 on chat...

RESOLVED: Start Group TF with a and Evan as co-leads

Emelia: ?something around Kamala's campaign?

