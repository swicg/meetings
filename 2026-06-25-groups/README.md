# ActivityPub Groups TF 2026 Jun 25

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- bumblefudge
- a <trwnh.com>
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- @mayel@bonfire.cafe

## Agenda


- Introductions and administrative
  - Code of conduct
  - CLA
- Updates to report
  - Integration of user stories from README.md and GitHub issues https://github.com/swicg/groups/commit/d2d5051fbbbcf6c534f23e820d93bd99c90f4db0
  - Stub out some sections https://github.com/swicg/groups/commit/ece0eaed068a43167bb55e5cd65147ac49d42d8c
- Previous meeting agenda items
  - Async discussion on #26 https://github.com/swicg/groups/issues/26

  ## Minutes

- Updates to report
- We had a number of docs -- the explainer, the report, the issues
- a added all the issues to the report draft
- a stubbed out some of the sections in the report draft
- added sections for roles, permissions, etc.
- EP: how to do an editorial flow? start with issues -> consensus -> PR -> approve?
  - a: rough consensus, still concentrating on the problem domain
 - EP: multiple competing PRs can be an issue, if they all satisfy an issue -- being in the midst of the discussion on an issue and starting a PR also creates a 2nd discussion in the PR comments that can replicate the issue discussion. another antipattern i've seen is PRs parked for weeks or months and they become the only place to find certain information. if we can keep discussions on the issue comments, and PRs short and non-contentious, then that seems good to me.
- News and updates since last time
  - Mayel: screenshare of Bonfire implementation, currently local only
    - "Browse groups" button leads to group directory
    - See which groups I've already joined
    - Group has topics/channels which are basically subgroups
    - You can follow and join separately
    - You can see permissions of the group, open or closed group
    - Create a group with the name and description, "common empowerment" (?) -- simple upfront but flexible options.
    - Select between "public local community", "announcement channel" (only mods can post, everyone can follow), "private club" (?), and "custom".
    - Join on request, or invite only, or anyone in a specific circle
    - Who can see the group
    - Who can post and interact (anyone, members, mods, circles)
    - default content visibility (public, local, members-only)
    - Add moderators
    - Add rules -- rule name and content.
    - Archive the group
- Outstanding old business:
    - Who can do what https://github.com/swicg/groups/issues/26
    - Different groups can have different permission models
    - Use interaction policies?
    - a: interaction policy might not be the right way to do it
    - a: GTS impl of interaction policy doesn't enforce, only gives UX hints (handled internally)
    - a: list of options and actions
    - a: Mayel notes
    - EP: the difference might not be as big between a "hint" and a "permission", but GTS has not submitted this under CG's IP rights and it is nontrivial work. Maybe approach GTS for whether they want to submit this.
    - EP: user stories are a good list of actions, where they deal with interactions with the group
    - Mayel: we would be mostly defining new permissions anyway, so i don't know if there's an issue here. on the topic of them being more of a "hint" that's true but we have also implemented interactionPolicy for existing boundaries. JSON derived from internal permission representation and having manual/automatic approval is helpful. optimistic UI with sending things like follow requests but you can rollback on later failure.
    - EP: i don't think it covers everything but it would be a good step
    - EP: cross-ref on issue 36, consensus based governance, GTS interaction policy model can't represent that (if we want to do that)
    - Mayel: policykit could help here, rules language auto implements decisions. Set up on the host instance for the group but doesn't need to be specified on the protocol. Bot can implement decisions directly on the collection.
    - Bumblefudge: posted prior art in the issue as well. so much of today's fedi is hierarchical, a "home server for every group" means implementations can do what they want locally. can a group move from one implementation to another, this could get in the way. ideally you aren't locked into bonfire if you start a group on bonfire. what's the MVP scope on functionality that should interop among all implementations?
    - EP: we do have a user story #34 on moving hosts. it's complicated but necessary, good to include it.
    - EP: Suggest we get to a "what" before we get to a "how". Seems pretty clear to me that a fixed set of rules about how groups work ("owner", "admins", "only admins can change the description", "only mods can do x or y"), set a line in the sand that we won't define hardcoded roles like that and we should define a way for groups to define their own roles.
    - a: i agree that the roles and permissions need to be standardized in composable ways and not hardcoded ways
    - EP: probably a good idea to have examples of mapping a "mods and admins" model to the roles and permissions. it's a useful mental model for some people even if we don't strictly hardcode it in the document.
    - Mayel: power can feel overwhelming but we do have roles and "circles" and UX to simplify and collapse possibilities.
      - Moderate
 - Invite members
 - Edit info
 - Configure the instance
 - Grant roles and permissions
  - Mayel: "Delete a post" and "see a report" aren't necessarily the same thing even if implied by "moderate".
- Next steps
  - EP: Write out and/or implement a list of permissions, integrate it into the report section
  - (in chat) Mayel: moderation user stories are particularly hard to tease out all the implicit permissions; BF: maybe issue #28 would be a good one to read carefully when listing permissions, for them to be adequately explicit and useful for cross-server moderation (and for cross-server migration down the road)
- Issue 47 https://github.com/swicg/groups/issues/47
  - EP: Use case for Member type as distinct from the actor? Make it clear that we need it or see if there are ways to avoid it. Are we going to make it a required indirection.
  - a: it's a very convenient and natural point to hang all "membership concerns" from the same record. subreddits have flairs, discord has custom display names and avatars, etc, can also index in both directions (member has roles, role has members)
  + (in chat) BF: either you model membership "member-side" canonically and "group actor-side" at specific times, or vice versa, non? off the top of my portability-maxi head, actor-side canonical with [maybe non-portable] optional/extensions member-side feels like MVP/simplest
  - Mayel: for performance you don't want to scan the whole collection vs just checking a single id.
  - EP: It is O(n) so there is a real performance issue but it shouldn't keep us from ...
  - EP: I see the point in having it as an option for these situations of adding extra metadata ("i want my reddit flair") but my concern is that i want a mode where there can be a simpler relationship. an option at least to do that.
  - M (in chat): what about having both? a `members` collection with actors and an optional `memberships` collection