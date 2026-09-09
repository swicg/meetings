# ActivityPub HTML Discovery

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
- bumblefudge

## Regrets
- a

## Agenda

Introductions/administrative

1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
4. Moving to a Draft Report (CG-DRAFT)
5. `rel=me`? #19 

Jitsi: https://meet.jit.si/activitypub-html-discovery
Time: 19:00 UTC | 14:00 EST | 11:00 PST

Add comments below to modify or add to the agenda.

## Notes

### Introduction

- Bumblefudge is a new participant!

### Implentation progress reports

- EP: https://github.com/social-web-foundation/activitypub-browser-extension
- Browser extension to identify ActivityPub object of the current page and provide UI to like, follow, share, ... the relevant objects

- EP: Matthias Pfefferle is working on an implementation in WP
- https://github.com/swicg/activitypub-html-discovery/issues/78
- Problems with Mastodon! see https://github.com/mastodon/mastodon/issues/22306

### Moving to CG-DRAFT

- EP: this document has been in slow-motion development for 2 years
- Would be great to move it on

- My criteria for CG-DRAFT
- on "CG Report" track
- ready for broader review
- ready for implementation (with the caveat that changes are still possible)
- non-goal: every issue closed

- BF: this might not be exhaustive
- We might need to add new items
- Could we specify that this is not exhaustive and there may be other ways of doing it that aren't listed?

- TT: A "CG Report" is never normative, always informative
- Can be input to a WG's recommendation

- EP: more of a profile of a few standards ecosystems (ActivityPub, HTML/browser, HTTP, ...)

- EP: a submitted an omnibus PR, with a lot of editorial changes, that we haven't worked through
- I haven't reviewed to the point of feeling comfortable that these are not draft-blocker changes
- I don't want to go to draft over his objections
- TODO: go through a's PR and make an issue for each (?) commit

- EP: add a draft-blocker label to issues

### `rel=me`

- EP: feature that Mastodon implemented
- assigning extra URL properties to an ActivityPub actor
- using `rel=me` link discovery in the pages at those URLs to define a relationship between the actor and the remote object
- Both pages need to have a subject
- TT: `owl:sameAs`
- BF: `alsoKnownAs`
- BF: might be an uncomfortable analogy to `alsoKnownAs`
- Based on https://indieweb.org/rel-me

- EP: Does `rel=me` need to be part of this report? Or should it be separate?
- PROPOSED: Drop `rel=me` as a user story for HTML Discovery TF 
- RESOLVED: Drop `rel=me` as a user story for HTML Discovery TF 


