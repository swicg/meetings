# January SocialCG Meeting 2026-01-09

SocialCG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Zagidulin
* Darius Kazemi
* Johannes Ernst
* Emelia Smith
* Ben Pate
* Ryan Barrett snarfed.org
* Matthias Pfefferle
* Evan Prodromou <acct:evanp@socialwebfoundation.org>
* [Michal](https://id.mrkvon.org)
* Theo [@thhck](https://github.com/thhck)
* [elf Pavlik](https://elf-pavlik.hackers4peace.net)
* a <trwnh.com>
* [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
* 

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
4. Task Force Updates
5. Charter updates if relevant
  * Darius with updates
6. Main Agenda 
  * FedCM discussion (Theo)
      * Emelia can add some context


## Minutes

* http://themetalayer.org/

### Announcements

* FOSDEM - SocialWeb Dev Room!
    * https://fosdem.org/2026/schedule/track/social-web/
* Protocols for Publishers conf - London, Feb 4&5
    * https://protocolsforpublishers.com/london-2026/

### TF Updates

Emelia: (Trust & Safety TF) Working on a FEP for content labeling.
- Next meeting: Feb 4

Johannes: (Website TF) Some PRs for ActivityPubRocks repo. Public page starting to shape up! Long backlog, volunteers & PRs needed.
- The 'quick explainer' graphic may be confusing, we should improve it
- Design may be somewhat date it, design refresh might be good. Maybe pitch in some $ to fund a design?

Evan: New explainer for the ActivityPub API TF: https://github.com/swicg/activitypub-api/blob/main/README.md

## Charter Updates

Darius: The working group has been approved as of ~16 hours ago.
- Darius is the presumed chair of the new working group
- Coordination happening on the announcement, expect next week
- Encouragement to read the W3C Process Documents - https://www.w3.org/policies/process/
- We need W3C members in the working group, for software implementers and publishers involved in the new working group.
- There are only a few hundred W3C Members (paying)
- Multiple paths to get people involved in the working group, including invited expert status
- Membership fees: https://www.w3.org/Consortium/fees

### Main Agenda

#### FedCM Discussion

Theo: FedCM is a type of SSO (Single Sign On) technology, mediated by the browser. 
One of the limitations is -- the RelyingParty (RP) web site needs to provide a list of valid Identity Providers.
There is some work on https://github.com/w3c-fedid/idp-registration
IdP Registration for "Bring Your Own IdP", which is relevant to the decentralized social media community.
Would be good to have more representation from decentralized communities in the FedCM meetings, since that WG is currently discussing whether to keep registration or not.

Emelia: FedCM would theoretically work for AP, AtProto, Solid, and others. The big problem we have right now is exactly that -- lack of IdP Registration. See issue https://github.com/w3c-fedid/idp-registration/issues/1
Aaron Parecki and Emelia did some complementary work on https://cimd.dev on the OAuth2 side.
This area (IdP Registration) needs more funding / attention.

Darius: Is this work done in a WG or CG? 

https://github.com/w3c-fedid/Administration/blob/main/proposals-CG-WG.md

Emelia: WG

Evan: (screenshare, gives example of Mastodon type SSO workflow currently out there)

eP: https://github.com/w3c-fedid/idp-registration/issues/15

Evan: What would be helpful for this community to do, to influence further work and adoption of IdP Registration?

Theo: Get the word out, join the discussions, do proof of concept implementations.

Johannes: I brought up this work to one of the Mastodon team last year, but no interest/uptake

TallTed: re WG vs CG. W3C work is meant to be done "in public", so that people not in the WG can keep tabs on what is being processed in the WG.
Chairs are empowered to invite anyone they like to a call, to speak on any topic. (And repeated invitations often lead to / lends weight to Invited Experts status)
Highly recommend people try for IE status in that group.
- https://www.w3.org/invited-experts/
- Example: https://www.w3.org/groups/wg/lws/instructions/
 
### Other

Elf: Ongoing effort from the Solid CG on interop with ActivityPub (things like ActivityPods etc). Might be good to coordinate / invite them for a presentation?



