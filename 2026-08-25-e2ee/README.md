# ActivityPub E2EE Task Force 25 Aug 2026

## Present

Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
Ben Pate <@benpate@mastodon.social>
@mayel@bonfire.cafe
Matthias Pfefferle <acct:pfefferle@mastodon.social>


## Agenda

https://github.com/swicg/activitypub-e2ee/issues/96

- Introductions/administrative
    - [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    - [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
- Progress and implementation reports
   - https://activitypub.space/category/30/e2ee-task-force
   - https://github.com/swicg/activitypub-e2ee/wiki/Implementing-a-server
- New business
  - Move MLS Document to CG-DRAFT?
  - #65 verifying additional devices actually belong to the actor (signing of actor's key packages) / Multiple Devices: Adding New Devices for an Actor 
  - internal IDs: mls:// or ap-mls:// instead of uri:uuid: ?
  - ap-mls:// as a standard way to open a client at a particular group/thread/message

Jitsi: https://meet.jit.si/activitypub-e2ee
Time: 16:00 UTC | 11:00 EST | 8:00 PST

Add comments below to modify or add to the agenda.

## Notes

### Going to draft

- EP: I think we're ready to go to draft
- MB: There are still open issues
- BF: Is this a draft draft or just a draft?
- BP: need to close some of these tickets
    
PROPOSED: take the MLS over ActivityPub spec to draft

PROPOSAL did not carry

- EP: Let's mark outstanding issues as "draft blocker" and get them closed

### Keysigning #65

- MB: issue for key substitution attacks, this gives us a way to sign the key
- EP: is this a replacement?
- MB: additional, not replacing

### Internal IDs #74

https://github.com/swicg/activitypub-e2ee/issues/74

- MB: motivation is for a web client to launch the native client with the encrypted (PublicMessage) object
- EP: not an URL, but has some additional support
- EP: Is this a secondary doc, or necessary for the MLS spec?
