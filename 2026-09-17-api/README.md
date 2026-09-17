# ActivityPub API Task Force 17 Sep 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>

## Agenda

1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
4. Basic profile to CG-DRAFT?
5. SSE to CG-DRAFT?
6. Seekitem to CG-DRAFT?
7. Autocomplete to CG-DRAFT?
8. Unofficial draft of RAR
9. Unofficial draft of Level 1
     - We need a good name for this!
10. FedID

Video: https://meet.jit.si/activitypub-api
Time: 16:00 UTC | 11:00 EST | 8:00 PST


## Minutes

### Implementation progress reports

- MP: Plugin supports all current OAuth scopes
- Autocomplete!
- PR for SeekItem
- Mapping system for scopes

- EP: ActivityPub (Chrome) browser extension
- Ready for demo by Fediforum

### Basic profile to CG-DRAFT

- EP: Two questions:
    - should Basic Profile ever become a draft (and then final)
    - is it ready now?

- MP: what about Media Upload? Still kind of chaotic

- EP: I think these parts of the draft are underbaked or at least are the newest, most volatile parts:
    - Media Upload
         - proxyUrl
         - OAuth Scopes
         - Actor Identity in OAuth access token response
         - Client IDs (CIMD is still a draft, one FEP, dynamic registration is solid)
         
- EP: I don't feel comfortable moving this forward in a meeting with 2 people
         - Create a "draft-blocker" label for issues
         - Mark the above user stories as "draft-blocker"
         - Get them to cleared
         - That's our signal that we're ready
         
- EP: How do we address proxyUrl and Media Upload?
- vaguely defined in ActivityPub 1.0
- Likely to be more fully defined in 1.1
- Create reports (in the same way that we have reports for SeekItem and SSE) for these interfaces
- Could be superceded by ActivityPub 1.1 at some point
- Other options: wait until AP 1.1 is in draft format with these interfaces better defined

- EP: TODO MediaUpload and proxyUrl documents

### SeekItem, SSE, Autocomplete

- EP: relatively independent of basic profile
- could go to draft independently
- would be nice to have more people here for that
- see more POC implementations
- maybe in https://swicg.github.io/examples/ ? Easy to use for testing
- Document implementations (similar to RFC 9421 doc for HTTP Signature)

### RAR

- EP: This is good for fine-grained permissions
- Interesting for some features https://github.com/swicg/activitypub-api/issues/72

- EP: seems like we've been able to implement multiple apps without RARs

- EP: I propose that we make RARs their own document, and don't include them in the basic profile, maybe in the "advanced" profile

### Move the time for this meeting

Same time, 3rd Wednesday of the month

