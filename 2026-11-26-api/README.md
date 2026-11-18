# ActivityPub API Task Force 18 Nov 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- bumblefudge

## Agenda

1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
7. MediaUpload unofficial draft
8. proxyUrl unofficial draft
4. SSE to CG-DRAFT?
6. Autocomplete to CG-DRAFT?

Video: https://meet.jit.si/activitypub-api
Time: 16:00 UTC | 11:00 EST | 8:00 PST

To recommend additions or changes to the agenda, please comment below.

## Notes

### Implementation progress reports

- seekItem: implemented on tags.pub, activitypub.bot, groups.pub

### Basic profile to CG-DRAFT

- Basic profile necessary to get "normal" social clients working
- ActivityPub, OAuth, HTTP
- Two underspecified ActivityPub features
- media upload
- proxyURL
- Concern: can we take this to CG-DRAFT with these underspecified features?
- Deeper definitions in the basic profile
- WG provides definition?
- Keep synched
- Building up conformance tests:
- https://swicg.github.io/activitypub-api/examples/oauth/index.html

### SSE

- Meets #9 requirement
- Problems with EventSource
- No Authorization header
- solution: include the access_token in the URL
- Big problem: access_tokens in the URL get logged in server logs, client logs, gateway logs
- Especially for long-lived access tokens, this is a big deal
- 4 options
- Recommend not using EventSource for authenticated request; use a polyfill
- Define a one-time ticket endpoint; automatic retries in EventSource
- Don't use SSE, use Websockets or something else
- Don't use OAuth 2.0, make up some other Authorization system
- https://swicg.github.io/activitypub-api/examples/oauth/index.html
- https://github.com/swicg/activitypub-api/issues/87
- Remove access_token
- Make a note about the issue
- Use a polyfill in the examples for authenticated requests
- I think we can implement this on the server and client side

### Autocomplete

- Add a conformance test client
- Test with some servers
- Going to CG-DRAFT after it is testable



