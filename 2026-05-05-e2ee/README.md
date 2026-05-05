# ActivityPub E2EE TF 5 May 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
- Mayel @ Bonfire
- Claire
- Ben Pate
- Dmitri Z
- bumblefudge
- a <trwnh.com> (2nd half only, mobile)

## Agenda

- Introductions/administrative
 - https://www.w3.org/about/positive-work-environment/
 - https://www.w3.org/community/about/process/cla/
- Progress and implementation reports
  - Emissary https://spectra.video/w/oGzENb3eBqwZXQw2p5V4D6
  - Bonfire
- Sending "message received" activity #60
- Verifiable keys Verifiable keys #43
- Go with Emoji keys
- Document keyserver as backup/alternative
- Report a message to moderators #77
- ES: unencrypted
- ES: need context (messages before, messages after)
- EP: getting context (+/- 5 messages, for example)
- ES: mod of group is different than mod of site/host, you need both
- bumblefudge: don't want to add silent mods to private groups
- Verify a reported message #79
- Flag activity
- ES: if you decrypt on server so all mods can see it then better to keep it simple and use TLS to report the message. you need to know who the mods are if you want to e2ee with them, but you don't want that because people can target harassment toward them -- a "moderators group" actor acts as a proxy
- Mayel: There may be some times that E2EE makes sense here
- Flag activity: non-transient activities
- Flag activity: needs a group of messages
- potentially relevant paper about client-side governance and moderation for e2ee: https://james.grimmelmann.net/files/articles/private-hierarchical-governance.pdf
- Verify a reported message #79
- Franking: https://github.com/swicg/activitypub-e2ee/issues/79
- paper: https://arxiv.org/abs/2507.19391 and maybe https://www.usenix.org/system/files/sec22-issa.pdf
- ES: Need to send to multiple moderators, may do some trickery to not match the franking signature
- a: Wouldn't other clients also have a problem? both clients and mods would check an HMAC/signature
- Handling blocked users (Handling messages from blocked users #78)
- Large file uploads (Very large files #71)
- "Remove Self" from group + decomission device #80
- #65 verifying additional devices actually belong to the actor (signing of actor's key packages) / Multiple Devices: Adding New Devices for an Actor 
- internal IDs: mls:// or ap-mls:// instead of uri:uuid: ?
- ap-mls:// as a standard way to open a client at a particular group/thread/message

