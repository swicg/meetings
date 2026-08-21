# ActivityPub Groups TF 2026 Jul 23

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org> @evan.cosocial.ca.fed.brid.gy
- Ben Pate <acct:benpate@mastodon.social>
- @mayel@bonfire.cafe
- Brittany Ellich brittanyellich.com
- a <trwnh.com> -- 11:22 onward


## Agenda

- Introductions and administrative
  - [Code of conduct](https://www.w3.org/policies/code-of-conduct/)
  - [CLA](https://www.w3.org/community/about/process/cla/)
- Updates to report
  - 
- Old business
  - https://github.com/swicg/groups/issues/47
- New business
  - https://github.com/swicg/groups/issues/55

## Notes

- Updates:
- Bonfire release Monday 27 Jul 2026!
- WP: groups in wordpress
- Blogwide actor acts like a group
- Treat the group as a user
- Mastodon: received grant to do work on groups (!), preliminary stages
- ATProto: Atmospheric groups
- OpenSocial https://opensocial.community/ w/permissioned data

- Issue #47:
    - Member class for group membership and related state
         - OpenSocial.community - has a metadata relationship
         - BP: needed for music band relationships
         - EP: does this encompass roles?
         - a: maybe -- a Member can have one or more Role which has one or more Permission, or a Member can have one or more Permission directly. the Permission is checked for access control before doing a protected action. question is do we want any consumer to infer permissions from Member.hasRole.hasPermission or do we want to dynamically recalculate Member.hasPermission on every single role change? Update(Member) vs Update(Role)
         - Mayel: roles might be out of scope
         - EP: Can we use Relationship type
         - a: both as:Relationship and as:Profile may apply but we probably want a specific type that is composable with other types. implementers can decide which types make sense to compose together
         - a: re Evan and Scott concerns about group complexity -- compare LDP "basic containers" vs. "direct containers", we could have a sort of "basic group" vs "membership group" structure -- but it's questionable if we want to ask implementers to support both vs supporting only membership groups. question of "what is a group if not its members" -- if you have "6 people talking together" that could be a mailing list or relay and doesn't really need the groups TF work (already achievable with existing spec building blocks?)

- AT interop:
    - Brittany in chat: 
     - Initial spaces we outlined: 
Group membership (for rendering them)
joinGroup
leaveGroup
listGroupSpaces
createGroupSpace
Report (content) 
- https://tropopause.pckt.blog/on-atproto-and-atmospheric-groups-jqdept6 
   -  @evan.cosocial.ca.fed.brid.gy
   - @socialcg.w3.social

- Agenda for next month
  - Joining groups and becoming a member?
    - https://github.com/swicg/groups/issues/38 was integrated into the report as Appendix B.1 and B.2
    - https://github.com/swicg/groups/issues/52 was opened by Evan to continue the discussion
