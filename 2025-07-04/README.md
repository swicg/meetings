# July SocialCG Meeting 2025-07-04

SocialCG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Zagidulin
* Lisa Dusseault
* Evan P.
* Emelia S.
* bumblefudge
* Angelo Gladding
* Eugenus Optimus

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
5. Task Force Updates
6. Charter updates if relevant.


## Minutes


### TF Updates

Evan: New draft of the e2ee spec! https://swicg.github.io/activitypub-e2ee/
specifically: https://swicg.github.io/activitypub-e2ee/mls.html

Lisa D.: still working on account portability, added some more on oauth2 and http signatures.
Working on our own AP Testbed Server (to migrate accounts to and from). (In Python) https://github.com/dtinit/activity-pub-testbed

Emelia: question on acct portability -- how does the oauth2 mechanism make sense in the context of federated servers? (How would client registration work etc)

Lisa: We're using OAuth2 less to identify the user and more to authorize data transfer. For example, the destination server initiates the oauth dance to the old server, authorizes to pull all existing data.

Emelia: what about the client registration specifically -- will it be static, dynamic, etc?

Evan: would it make sense to discuss this more in depth on a taskforce-specific call?

Dmitri: good idea

Lisa: this is coming from a broader DTI pattern (starting from a template of how IMAP migrations work) so maybe the OAuth stuff maybe some work to be fine-tuned to this federated-OAuth way
https://github.com/dtinit/activity-pub-testbed/blob/main/testbed/core/utils/oauth_validators.py

Emelia: The underlying OAuth library that Mastodon uses doesn't support DPOP, and I think we need to use totally different OAuth flows and approaches... we should make sure to discuss this before investing time building out more

Lisa: 7am July 15 Portability TF will meet to discuss 
1. [LOLA Oauth stuff](https://github.com/dtinit/activity-pub-testbed/blob/main/testbed/core/utils/oauth_validators.py)
1. [Hollo identifiers for packing](https://github.com/fedify-dev/hollo/pull/68)

T&S update: Emelia will write a FEP soon for content-labeling from the ActivityPub Trust & Safety Taskforce, and a separate FEP for recommendations on more interoperable sensitive/CW/TW annotations - Mastodon was using `summary` and Evan prefers new-prop FEP approach (migration/upgrade path still TBD, renaud kicking ideas around); preserve legacy data; 

Evan: "Notes" special-handling can be fallback, since other aspects of the Mastodon, um, mapping to AP semantics are also special-cased already.

Dmitri: Ok, any other TF updates or other agenda items?

Dmitri: K, let's adjourn early today!
