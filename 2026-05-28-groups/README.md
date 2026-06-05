# SocialCG Groups TF meeting, 2026 May

Meeting held 2026-05-28
Scribe: bumblefudge, a
GH issue: https://github.com/swicg/groups/issues/40
URL of this pad: https://pad.w3.org/p/SocialCG_Groups_2026-05-28

## Present
- a <trwnh.com>
- @mayel@bonfire.cafe
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Ben Pate <acct:@benpate@mastodon.social>
- bumblefudge.com

## Agenda

Groups Task Force meeting

1. Introductions and administrative
   - Code of conduct
   - CLA
2. Progress/implemention reports
  - https://github.com/evanp/activitypub-bot - https://groups.pub/
3. Old business
   -  https://github.com/swicg/meetings/tree/main/2026-04-23-groups
   - Which user stories are in scope?
   - membership / state machines https://github.com/swicg/groups/issues/38
4. Report draft (?) https://swicg.github.io/groups/
5. New business
   - leave a group #2 
   - get group members #6 
   - post content privately #13 
6. Agenda building for next meeting

Video: https://meet.jit.si/activitypub-groups
Time: 17:00 UTC | 13:00 EDT | 10:00 PDT

To recommend additions or changes to the agenda, please comment below.

## Progress / implementation reports

- Evan: https://github.com/evanp/activitypub-bot/blob/main/lib/bots/group.js

## Previous meeting's minutes

- https://github.com/swicg/meetings/tree/main/2026-04-23-groups

## Report draft

### Relation to README

- Evan: What's the relation between this report and the README?
- a: Some information was integrated (user stories) but not all of it yet.

### Scope of work

- Evan: For me, scope of this TF is "Facebook-like groups on the fediverse", is the constraint only on membership management?
- a: No, group members can obviously "do stuff", it's just a question of what "to do"

### Proposal to adopt draft as first draft

- Evan: Propose that we adopt this as a first draft?

PROPOSED: adopt index.html as first working draft of TF report.

- Bumblefudge: Great start, one checklist to have before getting approval, let's make sure all the user stories are mentioned in the report, linked to issues. Other concern is worrywart interop -- backwards compatible Announce pattern vs using the outbox, the report should mention what the group publishes and the considerations. 

- May: how would outbox work without announce?
  - a: Not mutually exclusive! Group can use ActivityPub to publish Announce to its outbox, and also trigger outbox delivery. We don't constrain (yet?) which activities the Group can produce.
  - EP: maybe Group has posts on its own
  - a: could have its own activities, yes. Group as an actor can publish things on behalf of the group that are "posts" in their own right, not everything has to be an Announce unless the Group wants it to be that way.

- EP: issues in the repo are now issues against this report

- a: We want to have a solid foundation and build on it -- members and roles as a primitive. Groups can publish anything after that. Process of discussion -> integration -> implementation.

RESOLVED: adopt index.html as first working draft of TF report. 

## User stories

### members vs followers

- Evan: Is this structure too complicated? Are members and followers actually the same thing? Do we need a Member construct? Could it just be followers-only? 
- a: There are systems that already exist that make this distinction, so if we don't make this distinction, then those systems cannot implement.
Evan: Turns out on Facebook you can unfollow a group without leaving it, confirmed via screenshare
  - bumblefudge (in chat): Discord, Signal, XMPP, Matrix
  - a: Yes, having a Member representing your membership in a group, being able to change your name and icon, etc in that group and that group alone is imo not "too complicated" but rather "table stakes" for social expression.
- Ben: Follow and Join can be the same thing and filter or mute notifications at the receiving side?
  - a: Yes, but they can also be separate. Think of following as "I am interested in receiving activities in my inbox"; you might not actually be interested in receiving activities in your own personal inbox. Similar to how on a mailing list you can send messages to the list and separately you can subscribe to the list to receive messages. If I don't want to receive all activities, I should still be able to participate as a member.
  - Mayel: We can send both a Follow and a Join by default with the same button press, so joining a group by default can make you also follow its activities.
  - bumblefudge (in chat): i like mayel's suggestion of each-join-is-a-follow as sensible default! 

### who can perform actions?

- Mayel (in chat): speaking of role I'd love more discussion on this async: https://github.com/swicg/groups/issues/26

## ACTION POINTS:
- review user stories in github to ensure the report covers them
- Explainer README to point to report draft
- a: CFC to mailing list re: adopting https://swicg.github.io/groups/ as initial draft of groups draft
- Evan: Make issue for next meeting and agenda
