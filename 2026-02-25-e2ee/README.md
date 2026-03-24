---
title: ActivityPub E2EE Task Force Meeting 25 Feb 2026

---

# ActivityPub E2EE Task Force Meeting 25 Feb 2026

## Present

* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
* @mayel@bonfire.cafe
* Ben Pate
* @ivan@bonfire.cafe
* Claire @ mastodon
* 

## Agenda

1. Introductions/administrative
2. Progress and implementation reports
3. https://github.com/swicg/activitypub-e2ee/issues/50 
4. https://github.com/swicg/activitypub-e2ee/issues/56 
5. https://github.com/swicg/activitypub-e2ee/issues/46 
6. https://github.com/swicg/activitypub-e2ee/issues/60 
7. https://github.com/swicg/activitypub-e2ee/issues/43 
8. SSE for new messages, related to https://github.com/swicg/activitypub-api/issues/9
9. internal IDs: mls:// instead of uri:uuid: ?
10. ap-mls:// as a standard way to open a client at a particular group/thread/message?
12. Holos...?
13. https://github.com/swicg/activitypub-e2ee/issues/51

## Notes

### Introductions

- various mutual introductions
- 

### Progress and implementation reports

- Emissary (Ben Pate)
    - Posted a video of the process
    - Create group
    - Send messages
    - Key management
    - SSE
- Bonfire (Mayel)
    - Messaging
    - Key management (remove self, remove others)
    - Emojis
    - Verify keys
    - Remove another device

### Messages by group

- https://github.com/swicg/activitypub-e2ee/issues/50

General consensus that this is not necessary (or a MUST), but using `context` with an `OrderedCollection` a la Threadiverse can be helpful. EP to add a SHOULD requirement to spec.

### Race conditions on GroupInfo

EP to investigate `published`, best practices for groupinfo.

### Actor autocomplete

EP to write up actor autocomplete proposal.

Q: is `endpoints` right way to do this?

## Action Items

- Issue 50: EP to add a SHOULD.
- Issue 56: check published granularity.
- Issue 56: suggest using `context`
- Issue 56: suggestions for best practices for sending groupinfo
- Issue 46: EP to write up
