# ActivityPub E2EE Task Force 28 Jul 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Ben Pate <acct:benpate@mastodon.social>
- Claire
- @mayel@bonfire.cafe
- @ivan@bonfire.cafe
- bumblefudge
- @elle@weathered-steel.social

## Agenda

- Introductions/administrative
    - [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    - [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
- Progress and implementation reports
- New version of the MLS spec
- New business
  - What next?
  - https://github.com/swicg/activitypub-e2ee/issues/83
  - #65 verifying additional devices actually belong to the actor (signing of actor's key packages) / Multiple Devices: Adding New Devices for an Actor
  - internal IDs: mls:// or ap-mls:// instead of uri:uuid: ?
  - ap-mls:// as a standard way to open a client at a particular group/thread/message

Jitsi: https://meet.jit.si/activitypub-e2ee
Time: 16:00 UTC | 11:00 EST | 8:00 PST

## Notes

Evan: W3C CLA announcement. Positive work environment, code of conduct.
Claire: Mastodon developer
Ivan: Bonfire developer
Ben: Emissary developer. Bonfire and Emissary are shooting an interop demo video. To share soon.

Evan: SWF has published an update to the MLS in ActivityPub spec that incorporates many discussions from this group: https://swicg.github.io/activitypub-e2ee/mls

Mayel: Bonfire's implementation includes a suite of end to end integration tests.

Evan: what happens next with this work?
- Milestone: Community Group Report (decision of the whole CG)
- "CG draft" -> "CG final"
- Either close or defer for next version *all* of our issues "vnext"
- incorporate learnings from implementations -- what is needed that's not in the report
- Extensions to ActivityPub E2EE
- Mutual support for implementer

Mayel: part of that is resolving some of the challenging problems and making decisions on some of the still open questions that have been discussed

elle: recommends BeeKEM: Decentralized, Secure and Efficient Group Key Agreement (https://eprint.iacr.org/2026/1434) as a model for us to consider.

evan: BeeKEM is an example of things that could be *extension* to the protocol. If extensions get lots of adoption, they can eventually be used as the primary mode for the protocol. Adding an issue to explore BeeKEM.
bf (in chat): the two different dMLS (distributed- and decentralized-) RFCs are both still unstable and iterating fast... too soon to build on...soatok's key-transparency-log thing is also a reasonable candidate for AP-specific KEM... see last week's [extension crosstesting presentation at MLS WG at IETF 126](https://datatracker.ietf.org/meeting/126/materials/slides-126-mls-thinking-about-mls-extension-compatibility-00) for example
elle: BeeKEM would need another cryptographer to review it. And, it may have been implemented by an LLM.

evan: so, can we shoot for halving the open (undeferred) issues by our next meeting?
ben: yes. I'll recommend lots of things to be closed, but we need a committer to actually close issues.
evan: goal: let's get to half the number of issues by the next meeting.
mayel: some just need an edit/addition drafted for the report before closing

elle: how viable would it be to use an alternative issue tracker (codeberg) instead of github? I want to interact with this group, but not github.
evan: all task force repositories are on github. However, we have used Fediverse enabled forums on other systems (e.g. Trust & Safety, Forums, and Groups)
elle: I would love to develop the Fediverse *on the Fediverse*
evan: adding an issue to use activitypub.space
mayel: what would this be, structurally? we should not have the same conversation in two places.
ben: can we just have conversations in one place? Such as: choosing which of the existing issues to migrate to a new platform
bumblefudge: replication exists, but doesn't fully trust this. there are many options, but if we're trying to cut an early version soon, we can move quicker if we stay on GitHub for the next few months.
evan: We could model how FEPs link Git (co