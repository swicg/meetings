# Groups Taskforce 22 Oct 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- @mayel@bonfire.cafe
- @ivan@bonfire.cafe

## Agenda

- Introductions and administrative
  - [Code of conduct](https://www.w3.org/policies/code-of-conduct/)
  - [CLA](https://www.w3.org/community/about/process/cla/)
- Implementation progress and demos
- Updates to report
- Old business
    - Follow versus Join (https://github.com/swicg/groups/issues/39), together with the membership items already on the list (https://github.com/swicg/groups/issues/51 and https://github.com/swicg/groups/issues/58) and https://github.com/swicg/groups/issues/52, which is about the `Join` activity itself. It was discussed in previous meetings, and we mostly agreed on the defaults: joining a group also follows it, and the two can still be used separately. What is left to decide is the public case: whether one can follow a public group without being a member (I'd say so). That would settle who a group sends to, and who counts as inside it.
   - The names of interaction policies: https://github.com/swicg/groups/issues/26
   - how do we define which activities are within the group context and which ones aren't https://github.com/swicg/groups/issues/52#issuecomment-5063796717
   - how do we manage the provisioning of arbitrary streams (like what others might call "spaces"?) https://github.com/swicg/groups/issues/46
   - managing membership (https://github.com/swicg/groups/issues/51#issuecomment-5817076313 and https://github.com/swicg/groups/issues/58#issuecomment-5816940217)
   - (if we have time) invites https://github.com/swicg/groups/issues/4
- New business
- I started a draft support table for https://github.com/swicg/groups/issues/63: what each implementation does with groups, and how each differs from FEP-1b12. I tested Mastodon, Mitra, Lemmy and Mbin against our groups, and filled the rest from their documentation and perusing their code when necessary. Would be great if each implementer (or people in the know) can correct/improve their own row.
- The permissions section (https://github.com/swicg/groups/pull/59) is merged :)
- I added three user stories, each with a proposal: 
  - https://github.com/swicg/groups/issues/66
  - https://github.com/swicg/groups/issues/65 
  - https://github.com/swicg/groups/issues/67 

## Notes

### Implementation

- News on moderation from Bonfire, locking threads, banning people from a group
   - Moderating a group on a different instance
   
- https://assembly.pub/

- WordPress: implemented groups by accident!
- Needs to be different from users and other content
- Lots of special cases
- Big issue with events, need to be integrated with the plugin

### Draft support table

- MB: Track the support for implementation of the new specs
- For now, tracking support for FEPs
- Tracking specifics
- How complicated is it?
- Can we clarify in the specs, and have simpler implementations
- EP: should we move this to a Markdown file?
- MB: MD file is more useful when we have a more advanced spec
- EP: Let's move to a Markdown file when we have a need

### Follow versus Join

- Follow versus Join (https://github.com/swicg/groups/issues/39), together with the membership items already on the list (https://github.com/swicg/groups/issues/51 and https://github.com/swicg/groups/issues/58) and https://github.com/swicg/groups/issues/52, 

- EP: Argument for separate Follow and Join
- FEP 1b12 uses Follow, and it would be good to keep compatibility
- AV has a Join activity. It would be nice to use it.
- Some group software has join-but-don't-follow feature (I'm in the group, but don't get updates).
- Some groups are for announcements, follow-but-can't-join. see https://github.com/swicg/groups/issues/65 
- Having these be disjoint seems to reflect current usage.

- EP: Argument against
- They are close in functionality, so it might be confusing for users (this is up to implementations to solve)
- Multiple states (no contact, following only, join only, following and joining)
- Mismatched expectations ("I joined but didn't receive updates?")
- None -> Join -> followed and joined
   None -> Follow -> followed
   Followed and joined -> Undo Follow -> joining
      - Could we have implementations that join the two (say, by having the same collection for `followers` and `members`)
      
- MP: easier for subscribe, hard to do implicit follow-join

- MB: Interpret based on whether joint Follow/Join are received

- MB: Backwards compatibility until we have broader support

- MP: Multi-type? ["Follow", "Join"]

- MB: Way to link two activities? Point the two at each other?

- EP: would `result` be the right one? It's in Activity Streams

- MB: Less of a result than a parallel activity

PROPOSAL: We support the separate granular use of "Join" and "Follow" in our spec
RESOLVED: We support the separate granular use of "Join" and "Follow" in our spec

### Naming interactions

- List of interaction policies
- https://github.com/swicg/groups/issues/26#issuecomment-5470227200
- `canCreateGroup` - presupposes some kind of subgroup structure
- `canUpdateInteractionPolicy` - may need more granularity
- `canUpdateGroup`  - may need more granularity
- IP is not a guarantee that it will work, just a suggestion that it's worth trying
- Read permissions are better handled (?) with addressing, like `to: as:Public` or `cc: followers`
- ? Group collections covered?
- Reporting: anyone can report
- Who can read reports? Do we send `Flag` activities to the group? `canUndoAnnounce`? This is a read permission, so we don't see that as a problem. CC moderators collection gets it in their notifications.
- EP: The next step is defining a group context for these (and other) terms
- EP: Document the permissions in the group report

## 
