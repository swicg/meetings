# ActivityPub API Task Force 16 Jul 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Ben Pate <acct:benpate@mastodon.social>
- Steve Bate <acct:steve@social.technoetic.com>
- Matthias Pfefferle <acct:pfefferle@mastodon.social>

## Agenda


1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
    a. Workshop at DWeb Camp
4. https://github.com/swicg/activitypub-api/issues/11
5. https://github.com/swicg/activitypub-api/issues/24

## Notes

- Progress Report
  - https://github.com/social-web-foundation/workshop
  - https://docs.google.com/presentation/d/1akxQBW06rkD-aV_NMBODoYn56DWoCXTp_5xfBM6pw04/edit?usp=sharing
  - Ben Pate: E2EE - wrapping up some of the work from the project
    - MPf: rearchitecting work on AP plugin for better support

- Collection membership
  - Is A following B?
  - Is this object in the conversation context?
  - https://datatracker.ietf.org/doc/html/rfc6570 change from `item` to URI template
  - item -> id ?
  - tags.pub -> has this object been shared? EP to implement
  - Authentication: OAuth, HTTP Signature, none, ...? Show in examples

- Account autocomplete
- https://swicg.github.io/activitypub-api/autocomplete
- BP: implemented in Emissary
- 