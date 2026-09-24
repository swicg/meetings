# ActivityPub Groups TF 2026-08-27

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- ivan minutillo <acct:ivan@bonfirenetworks.org>
- a <trwnh.com>

## Notes


- Introductions and administrative
  - [Code of conduct](https://www.w3.org/policies/code-of-conduct/)
  - [CLA](https://www.w3.org/community/about/process/cla/)
- Implementation progress and demos
  - Assembly - ActivityPub API client for groups
	  - https://github.com/social-web-foundation/assembly.pub
	  - https://assembly.pub/
  - Bonfire groups released local only, intiial feedback received and basic interop FEPs started -- public only groups coming soon, private groups pending work in this TF for private participation. RC out and aim to have something by next release. possibly 3 types of public groups -- guppe-style "anyone can mention and it gets announced"; channel-style "accept the follow but not a member"; submission queue for group to approve.
  - First implementation of basic FEP for interop (fedigroup, threadiverse) a la guppe in 1.0.8
- Next different types of permissions for invite-only, private, announcement types of groups
- Updates to report
  - 
- Old business
  - Who can perform actions? https://github.com/swicg/groups/issues/26  (and related roles: https://github.com/swicg/groups/issues/48)
    - Mayel: granular; reuse existing mechanisms? instead of hardcoding "admin"/"mod"/etc
    - a: i think reframing it might make more progress -- instead of "who can perform actions" we should ask "which actions can be performed" 
    - Evan: the acl approach makes sense, we need to include in the specs
    - Evan: interactionpolicy is interesting advisory property, you can send but it might not be accepted. still waiting on gts if/when they submit interactionpolicy to the socialcg.
    - Evan: how to handle changes in policies -- update the group?
    - Evan: can we accommodate https://github.com/swicg/groups/issues/36
	- MB: could interact with an actor that has the permissions, automated actor
	- a: this could be implemented in the group software; the Group itself is that "automated actor" to some extent
	- ivan: i agree with a
	- mayel: agree but it can be also handled in another TF?
	- Evan: that's us!
	- mayel: we could point to these possibilities at least
	- a: consensus is good to do in the group software itself
  - review ATproto groups schema progress https://github.com/swicg/groups/issues/55 
	- should we sync up on permissions structure
	- a: there are some discussions in BS world already
	- MB: it would be good to see what they're drafting
	- https://discourse.atmosphere.community/t/another-follow-up-topic-group-management-methods/941
	- https://discourse.atmosphere.community/t/atmospheric-group-moderation-requirements/910/
- New business
   - Adding wireframes/mockups to issues to discuss UX and workflows
   - EU opportunity
   
## Next step
- ask GTS to contribute interactionPolicy to SWICG
- mayel makes a PR to https://swicg.github.io/groups/#user-stories-for-permissions
	- interactionPolicy mechanism
	- draft list of actions for our user stories, eg: canJoin, canAcceptJoin
	- share with https://discourse.atmosphere.community/t/another-follow-up-topic-group-management-methods/941 or https://discourse.atmosphere.community/t/atmospheric-group-moderation-requirements/910/

