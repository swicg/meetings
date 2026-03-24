---
title: ActivityPub E2EE SocialCG Task Force 30 Dec 2025

---

# ActivityPub E2EE SocialCG Task Force 30 Dec 2025

## Present

* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
* @mayel@bonfire.cafe
* Ivan Minutillo <acct:ivan@bonfire.cafe>
* Ben Pate <acct:@benpate@mastodon.social>
* Aurélien <acct:@opsocket@mamot.fr>

## Agenda

* Changes to the MLS in ActivityPub spec
    * Added https://swicg.github.io/activitypub-e2ee/mls#messages
        * only need to include `mls:messages` on Actor when fetched by the authenticated actor 
    * use presence of `keyPackages` property on factor to determine if they can receive MLS messages?
        * https://github.com/swicg/activitypub-e2ee/issues/52
* Progress (and challenges) on implementations
    * Bonfire: https://github.com/bonfire-networks/bonfire-app/issues/1701 
    * 
* Fossdem?
* Issue review and triage
* 
## Issues

