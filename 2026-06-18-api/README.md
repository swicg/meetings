# ActivityPub API Task Force 18 Jun 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- bumblefudge.com
- Charles Iliya Krempwaux <acct:reiver@mastodon.social>
- Django Doucet <acct:django@mediaformat.org>


## Agenda


1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
    a. Tutorial workshop on ActivityPub API at [DWebCamp early July](https://dwebcamp.org/)
4. OAuth scopes  #69
5. Rich authorization requests #72

Video: https://meet.jit.si/activitypub-api
Time: 16:00 UTC | 11:00 EST | 8:00 PST

To recommend additions or changes to the agenda, please comment below.

## Notes

- Introductions: NONE
- Progress:
- Tutorial workshop on ActivityPub API at [DWebCamp early July](https://dwebcamp.org/)
- Hopefully reusable for future events
- Matthias: WP Reader client for reading a user's federated feed; progress somewhat stuck on working around Reactisms
- maybe test later to other C2S Servers? (Evan: check out pleroma!)
- OAuth scopes
- Basic profile https://swicg.github.io/activitypub-api/basicprofile
- Included a list of proposed OAuth scopes
- proposal 1: Activity-based scopes
- (Side convo in chat): Charles (@reiver) says:If someone created a custom Activity (such as, for example, "Punch") is there a way it supports that. BF: Great question. Activities are arbitrarily extensible, so just dropping any unknown Activity kinda breaks a fundamental affordance of AP (but also opens a weird security surface for unknown Activity types
- https://github.com/swicg/activitypub-api/issues/69 <- architecture overview
- proposal 2: Resource-based scopes (following, followers, liked, replies, ...)
- https://www.w3.org/wiki/SocialCG/ActivityPub/OAuth_2.0_Scopes#Scopes
- proposal 3: [Functionality-based scopes](https://www.w3.org/wiki/SocialCG/ActivityPub/OAuth_2.0_Scopes#Scopes), aka capabilities
- URL aesthetics: M: move to another domain? (activitypub.rocks?)
- "read inbox" versus "read XXX in inbox"
+ Evan: failure mode: User distrusts app, rejects "entire inbox" authZ
+ Evan: another failure: Bad Actor client, requests "read all" which user doesn't realize is happening when she gets
- Matthias: "all content" is vague, "all public content" versus "all content" is important; besides, a client has to be able to READ (parse) all content to request
+ django: current "read all inbox" includes Block activities, etc-- not ideal, may not be comfortable for users to be authorizing that
- EP: Let's do a round of meanings (AI), then additions or removals, then start implementing (version #?)
- Rich Authorization Requests (RAR)
- https://github.com/swicg/activitypub-api/issues/72
- JSON-based
- Tend to be per-request structures
- Tend to be for high-security situations
- "Pay 35 euros from Account X to to Account Y on so-and-so date..."
- "Post a text reply with an image attachment to Django's Note with this ID: ..."
- bumblefudge: stabler parsing with structure; instead of "pay:35:euros:to:X:from:Y", use JSON
   - avoid using a complex DSL
   - ATProto does some dynamic scopes (verb-noun pairs) with string-parsing of complex structures, not RARs
- Evan: Something i like about RARs: they're precise
- Example of Github API: if API has pagination, "read inbox" might actually mean "read first 100 objects in inbox"; once servers implement divergently, gets tricky for client developer to assume consistent server behavior; finer-grained (e.g. RARs) helps avoid this semantic ambiguity
- Evan: Something I don't like about RARs: Mapping the requirements to a DSL might get hard, and hard for end-user to resonably consent
- UX Considerations
- authZ flow PER ACTIOn seems overkill, unless it's mega destructive/severe?
- bf: but RAR doesn't require that-- it's just one use-case for RARs, you can use RAR objects AS scopes (long-lived)
