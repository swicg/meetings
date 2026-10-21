# ActivityPub API 21 Oct 2026

## Present

- bumblefudge.com 
- Django Doucet <django@mediaformat.org>
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>

## Agenda

Administrative
a. W3C Community Contributor License Agreement (CLA)
b. Positive Work Environment
Introductions
Implementation progress reports
Seekitem to CG-DRAFT?
SSE to CG-DRAFT?
Autocomplete to CG-DRAFT?
MediaUpload unofficial draft
proxyUrl unofficial draft

## Notes

### Introductions

### Implementation progress reports

- evan has two:
1. activitypub-bot now supports seekitem ([tags.pub](https://github.com/social-web-foundation/tags.pub), groups.pub, activitypub.bot, ...)
+ Live Demo in browser.pub! seekitem for pagination (endpoint declared in the collection object)
2. onepage.pub also supports seekitem
- nuage update: no new features since last meeting, but seekItem in the backlog and actually all the CG-drafts in today's agenda and the media-upload (starting a FEP draft about it maybe)

### Seekitem to CG-DRAFT

- Are we ready to move this to a CG-DRAFT? What does moving to a CG-DRAFT?
- Note on roadmap:
- "basic profile" (level 0)
- A number of extensions to meet use cases (SSE, seekitem, RARs, ...)
- "advanced profile" (level 1) some collection of these extensions
- PROPOSED: move seekitem report to CG-DRAFT 
- RESOLVED: move seekitem report to CG-DRAFT
- Evan: biggest implementer headache so far: mandatory 404 if caller isn't authZd for that collection OR the item that member refers to 
- Worth adding a ReSpec "open issue" note on this!
- BF: what collections shoudl the priv/sec considerations warn people NOT to use seekitem for? Following? T&S corner cases? Evan: That reminds me, there are some implementations that use 403 or 404 for Following collections
- Django: Privacy review from outside in w3c? get Tara or someone for that?  

### SSE to CG-DRAFT

- SSE Server-sent-events
- WHATWG (maybe?) standard for Web interfaces
- like websockets
- server to client only
- uses the same port and connection as HTTPS
      - Issue #9 https://github.com/swicg/activitypub-api/issues/9
      - Adding https://github.com/swicg/activitypub-api/issues/87
      - EP: I don't think we can go to CG-DRAFT without dealing with this issue
      - EP: I don't think we can go to CG-DRAFT if we have other proposals for streaming delivery to compare to
      



