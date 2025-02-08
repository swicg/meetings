# January SocialCG Meeting 2025-01-03

SocialWG on Fedi: https://w3c.social/@socialcg

Archived: https://www.w3.org/wiki/SocialCG/2025-01-03

https://meet.jit.si/social-web-cg

## Present

* Dmitri Zagidulin
* nigini (https://nigini.me)
* [Ted Thibodeau](https://github.com/TallTed/) (he/him) https://mastodon.social/@TallTed
* Andy Piper https://macaw.social/@andypiper
* Evan Prodromou <acct:evan@cosocial.ca>
* Emelia Smith <acct:emelia@hachyderm.io>
* Damon Outlaw 
* Tantek Çelik [@tantek.com](https://tantek.com/)
* Angelo Gladding https://ragt.ag
* Bob Wyman

# Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
4. Task Force Updates
5. Main Agenda: 2025 Road Map and Wishlist items discussion
6. (If Time) Social Web CG Charter PR and issue processing
    - [existing PRs](https://github.com/swicg/potential-charters/pulls) and update status
    - [CG-related issues](https://github.com/swicg/potential-charters/issues?q=is%3Aopen+is%3Aissue+label%3A%22CG+Charter%22)

# Minutes

## Intros

- Lisa Dusseault: hi everyone, working on Account Portability, etc. (also we have a dev working on a testbed implementation)

    - Emelia: Regarding implementations, highly recommend Hollo (https://github.com/dahlia/hollo ) as a candidate for LOLA implementation (migrate from Mastodon)

    - Emelia: also, hi, I'm involved in IFTAS and other projects, lead of ActivityPub Trust & Safety TF (next meeting Jan 7th), working on initial report for it.


## Community announcements

* Darius: folks are encouraged to beta test the Fediverse Observatory https://asml.cyber.harvard.edu/fediverseobservatory/ ; send an email to fediverseobservatory@cyber.harvard.edu to request to join

* Emelia: also, Nivenly will be launching security fund later in the month.

* Evan: Fosdem in February will have a SocialWeb dev room. ~12 talks & implementations. So if you're in Europe and near Brussels, come join. 
    * Also separate after-hours event (4 more speakers) at Fosdem. 
* Evan: There will be a Fediverse-related space in SxSW (South by Southwest) conference in Austin.

* Andy: looking forward to Fosdem. Also, published a talk (script, since the video will have  a Japanese dub) of my SocialWeb talk in December. https://andypiper.co.uk/2024/12/24/building-a-better-social-web/
    * Also, couple of us will be going to RightsCon in Taipei in February

## TaskForce Updates

* Emelia: Discussion on Trust & Safety TF issue needs more eyeballs on it: https://github.com/swicg/activitypub-trust-and-safety/issues/46

* Evan: GeoSocial TF had its first meeting last month, Mike Waggoner and Jeremiah Lee stepped forward to co-lead the TF. 20 or so User Stories around Geosocial activities, covers a lot of ground, lots to review. Next meeting on the 9th next week.
    * https://github.com/swicg/geosocial

## 2025 Roadmap and Wishlist Item Discussion

* Dmitri: Finish and adopt the CG Charter https://github.com/swicg/potential-charters/
    * Can we commit to a date?
    * First, we need to give people sufficient warning, but Q1 and hopefully in the next two months
    * We need people to check the [issues](https://github.com/swicg/potential-charters/issues) the open PRs

* Emelia: [Pull request #50](https://github.com/swicg/potential-charters/pull/50) can be closed without merge considering the changed dates are passed and we did not reach the deadline

* Evan: wishlist item... standard way for authentication of ActivityPub requests (suggestion, giving some guidance to use OAuth)
    * Emelia: I'd leave the door open for alternatives. Using discovery to identify what authentication is being used. Example Solid uses multi-authentication. 
    * Evan: Agree. Giving guidance for OAuth should not block other authentication.
    * Emelia: Just making sure we don't want to bake OAuth into the protocol
    * Dmitri: How can we present that? 
    * Emelia: Use the way that Solid does it now!
    * Tantek: room for multiple approaches. Document existing approaches. And also express opinions on what some other/better options are, lay down some requirements. Provide an opinionated statement, perhaps advocating for OAuth as Evan suggests, due to its better privacy and security properties for users.
    * Emelia: perhaps adding an "authentication mechanisms" property to the Actor profile?
        * Evan: we have that (?)
        * Emelia: We only have two properties for oauth specifically

* Evan: Wishlist item — FPWD of ActivityPub 1.1, and ActivityStreams 2.1 by the end of the year. (Requires CG charter and a new WG charter set up).

* a: In parallel to signaling Authentication mechanisms for an Actor -- the idea for Profiles for semantics and behaviors. If you see an Actor & Inbox, you have no real ideas of what they produce and accept. Currently, these things are kind of ambiguous. (Like, when you send an Activity, and it's missing an implementation-specific field, it might get rejected etc.) A mechanism for declaring common profiles. For example, "publishing to a microblogging network" profile. A "chess app" profile. etc. Or "Actor supports E2EE messages". 
    * Emelia: at the moment, a lot of what we see in AP is people looking up Mastodon's implementation and implementing that (compat layer). Would be great to not only signal profiles supported by an actor, but also implementation guides for each.

* Evan: Wishlist item — we have a lot of TaskForces covering a lot of issues. It would be wonderful to see each TF going into 2025 to commit to at least one finalized report!

* Angelo: Was just looking over changes made to the CG charter, and I noticed that the Commit messages were a bit vague (with typos commingled with substantive changes), so it was hard to see diffs. So, wishlist item — clearer diffs/changelogs etc, better commit messages.
    * +1 Tantek (in chat)

* Dmitri: Wishlist item — chair elections! :)

* Emelia: Wishlist item — w3c's Activity Summary emails tool set up. (weekly automated email) https://github.com/ietf-github-services/activity-summary

* Angelo: related — Unifying with the greater Fediverse. Part of the delay with the charter might be — we don't want to catch the wider community off-guard. So if we had better commit messages, that might address that concern.
    * +1 Tantek (in chat): to linking in commit messages to when/where decisions were made, so folks could "follow their nose" to better understand reasoning

* Evan: In terms of finishing the charter, what would we need?

* Dmitri: My recommendation — close or label outstanding issues and PRs, announce to the wider community, comment period, then adopt.

* Tantek: My request to the group would be — for any new issues, consider whether it's a charter blocker. And if it's not a blocker, let's mention that in the issue and tag it as such. Or just wait to file the issue.
    * For the existing CG charter issues (the 10 or so), let's put out a call for PRs to address them.

## Social Web CG Charter PR and issue processing 

### https://github.com/swicg/potential-charters/pull/51

Evan: Discussion of terms used, Committer vs Contributor vs Editor. Champion from the staging doc.














