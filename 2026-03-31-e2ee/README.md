---
title: ActivityPub E2EE Task Force

---

# ActivityPub E2EE Task Force

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Claire @ Mastodon
- Ben @ Emissary
- Mayel @ Bonfire
- T


## Agenda

1. Introductions/administrative
2. Progress and implementation reports
3. Holos interop...?
4. Reference 3rd-party client
5. SSE for new messages, related to https://github.com/swicg/activitypub-api/issues/9
6. Read forward in time from last read message https://github.com/swicg/activitypub-e2ee/issues/51
7. Emoji reactions https://fediverse.codeberg.page/fep/fep/c0e0/
8. Sending "message received" activity https://github.com/swicg/activitypub-e2ee/issues/60 
9. Verifiable keys https://github.com/swicg/activitypub-e2ee/issues/43 
10. internal IDs: mls:// or ap-mls:// instead of uri:uuid: ? 
11. ap-mls:// as a standard way to open a client at a particular group/thread/message?

Jitsi: https://meet.jit.si/activitypub-e2ee
Time: 16:00 UTC | 11:00 EST | 8:00 PST

## Introductions

## Progress and implementation reports

- Ben Pate: Demo of emissary with adding, removing, e2ee
- Mayel: demo of Bonfire
    - https://github.com/swicg/activitypub-e2ee/issues/71
    - ACTION: EP to fill out with conversation (stored files, chunked messages, ...?)

## Holos

- Implemented E2EE messaging with Signal protocol
- Action item: outreach

## Reference 3rd-party client

- Web client (primary goal)
- Android native client (secondary goal)

## SSE

- Action item: access_token in URL
- Action item: smaller notifications with just an URL


# Seek interface

- https://github.com/swicg/activitypub-e2ee/issues/51
- https://swicg.github.io/activitypub-api/seekitem
