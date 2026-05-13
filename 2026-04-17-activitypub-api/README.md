# ActivityPub API Task Force

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
- Steve Bate <acct:steve@social.technoetic.com>
- Matthias Pfefferle <acct:pfefferle@notiz.blog>
- bumblefudge.com
- a <trwnh.com>

## Agenda

1. Introductions / administrivia (5 min)
   * CLA
   * COC PWE
2. Implementation progress reports
   * bumblefudge profiling on implementer coordination
   * https://socialwebfoundation.org/2026/03/10/ap-the-activitypub-api-command-line-client/
  * WP API will go out with next release of AP Plugin (behind feature flag until enough implementation history)
     - Steve's testing tools and evan's client,
     - Evan: CxS matrix of spot-tested interop? Steve: not spitting out reports but current NLNet proposal includes upgrade to the testing tool (part of app for an SPA client)
* sill.social (NL) - may be interested some day
* Bonfire, Emissary - MLS over ActivityPub
3. [OAuth profile #1](https://github.com/swicg/activitypub-api/issues/1/)
* intro
* Preconditions - what does a client need to know to be able to OAuth with a Server?
- Steve: Actor ID needs to be in the exchange; WP plugin is using the indieweb `me` prop; Onepage.pub uses a JWK (?); could use a Token Introspec endpoint; could follow OIDC prior art
* Server Metadata for discovery: rfc 8414
- [example doc](https://datatracker.ietf.org/doc/html/rfc8414#section-3.2)
* Discovery questions: same-server assumption?
- BF: maybe for MVP profile, but I think very complicated setups will require breaking same-server assumption
- (in chat): `a`: i think practically speaking if you make the assumption that 8414 makes (same origin etc) then this MUST be mentioned in the security considerations of the profile document: "we expect people not to do this generally but it is possible that some people are going to do this so [implications]"
* CIMD (draft RFC 😬 ) versus dynamic client registration (client has to manage a secret? redundant registrations/deduping unknown clients registering en masse complexity)
4. [Baseline support profile #54](https://github.com/swicg/activitypub-api/issues/54/)
* a - I'd like to see it possible to dynamically discover multiple profiles, rather than having to sniff from domain apex; using `www-authenticate` header (e.g., sidewide) points any server or client to the AS and 8414 document anytime they request any resource, advertises OAuth and other authZ info everywhere
