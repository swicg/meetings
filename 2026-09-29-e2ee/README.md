# ActivityPub E2EE Task Force 29 Sep 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Ben Pate

## Agenda

- Introductions/administrative
    - [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    - [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
- Progress and implementation reports
- New business
  - Review changes in Draft document
  - Review remaining draft-blocker bugs
  - Move MLS Document to CG-DRAFT?
  - Threat model

Jitsi: https://meet.jit.si/activitypub-e2ee
Time: 16:00 UTC | 11:00 EST | 8:00 PST

Add comments below to modify or add to the agenda.

## Minutes

- Progress and implementation reports
- Implementation pause
- Security reviews due to LLM review
- New reference client at https://github.com/social-web-foundation/reference-e2ee-client

- Moving to CG-DRAFT
- "We think this will eventually go to a Final report, so we want implementations and review at this time"
- Proposal in August
- Concern that there are outstanding issues that might require significant re-architecture
- Started the draft-blocker label
- Are we still blocked with going to CG-DRAFT?
- EP: I think we have covered most of the ones marked CG-DRAFT, unclear if it's the "right" solution, but at least we have a mention or solution
- BP: Reread the draft, still two outstanding: choice of ciphersuite and very large files
- EP: How perfect do we have to be to go to CG-DRAFT?
- BP: For example when do you need to go to the ordered collection to check ordering?
- EP: When there is a cryptographic key problem, can you rollback and replay?
- BP: That's the problem -- doing it that way is harder! Describing an algorithm to apply at groupinfo receive time instead of exception time is much
- EP: We may want to introduce heuristics for who should send the epoch update -- such as the group creator?
- BP: We can't wait for any particular person to do the update, they may not be connected for a long time
- BP: An always-running daemon could work also
- EP: MB had strong objections to going to draft; I would feel uncomfortable making a decision today without him here
- BP: Make sure key signing is covered

- Threat model
- EP: Emelia Smith noted that we don't have a written threat model for the application area
- EP: Opened an issue, https://github.com/swicg/activitypub-e2ee/issues/99
- EP: I see a couple of options for this workstream
- EP: 1) Add a (very long) appendix to the MLS document with the threat model
- EP 2) Have a second, non-report document that we use to add security considerations and privacy considerations (and others...?)
