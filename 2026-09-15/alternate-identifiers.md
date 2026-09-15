# Special Topic Call: Alternate Identifier Strategies and Alternate URIs types in ActivityPub

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Ryan Barrett snarfed.org
- Matthias Pfefferle
- Darius Kazemi
- a <https://trwnh.com/#a>
- bumblefudge

## Minutes

previously:
    [Identifiers and ActivityPub: Some Thoughts](https://learningproof.xyz/identifiers-and-activitypub/)
    [FEP-cd47: Federation-friendly Addressing and Deduplication Use-Cases](https://fediverse.codeberg.page/fep/fep/cd47/)
    [FEP-73cd: Migration User Stories](https://fediverse.codeberg.page/fep/fep/73cd/)


 - bumblefudge gives presentation: https://learningproof.xyz/assets/static/New%20Identifiers%20for%20new%20Webs.pdf
   - Use cases for AP: content addressing for attachments, activities, and Actors are different problems even though they might look similar at first blush
   - the rubric I'm proposing we use to assess identifier schemes for use cases is how locatable the URN is; and the trust equivalent. if you are dereferencing an URI, e.g. an at:// uri, who do you have to trust to dereference it on one protocol or another. Which servers have to be live, who do you have to trust to know you have the right keys/data.
- Ryan: are we discussing use cases in this call?
- bumblefudge: yes
- Ryan: in general this makes sense. A lot of the framing we've seen so far has focused on 2 possibilities: authority-based or content-addressed. Those are two big options, but there are others. I don't want us to slide into the idea that it's either/or and exclusive to these.
- bumblefudge: these are the buckets of building blocks, but when you're doing an end-to-end thing when you're doing content addressing plus fetching a key you are already doing something hybrid.
- Ryan: I think it's mostly helpful to make the distinction but it's a bit of an oversimplification
- bumblefudge: another big design consideration is where you want to use ICANN, and where you can avoid ICANN blocks. in some cases people do not want ICANN as the main authority.
- bumblefudge [back to presentation]: I put together a table of ways to identify things by hash. `eris` is worth looking into - it has its own RDF canonicalization, used for delta chats, implementer is AP-aware. Most of these don't have normative refs/specs so it's worth considering adoption in case there's going to be a path to WG adoption. You also have to consider how much work needs to be done to decode an identifier - how much compute etc.
- Evan: how about random identifiers like uuidv4? How important is it for us that the identifier be derived from the content?
- bf: Deriving identifiers from content can be a good thing or a bad thing depending on the use case. If you have a byte stable referent and you're passing around hashes, then anyone can prove you published it after deleting it, so there's a repudiability issue. I don't blindly recommend them for user generated content - in my personal opinion, i think we need to architect repudiable publication into user generated content even if it is internally identified by content identifiers. AP is an interesting use case because we are talking about identifiers for links in  JSON-LD ActivityStreams objects. But also worth noting uuids are used a lot in these cases. For id properties, uuids make great id properties. I think they should be legalized - but for example the Mastodon profile of AP drops uuids. People are afraid to use uuids as ids because they get dropped in practice. It's a super breaking change but I would support in v2 AP having `url` be the url and `id` be a unique non-URL id. For many of our user stories a uuid would be better than a content identifier! But that's on the level of such a breaking change I'm not advocating we put it on our todo list, but ideally ids shouldn't have to be URLs. URNs would be better.
- Ryan: the one thing a URI gives us is scheme, which implies transport. If you don't know how to get the thing you can't really do ActivityPub.
- bf: you can't insist on non-dereferenceable ids unless you mandate a `url` field alongside it
- Ryan: re: the repudiation part, I think it could be a goal to say that we allow for repudiability. I don't know if we can all assume it's a baseline.
- [discussion of many configurations and use cases in the current web where there is and isn't repudiability]
- Ryan: I just want to point out that it's not a given and it does introduce more work since it's a constraint we would be imposing
- a: when you say ids should not be urls, I think the distinction doesn't matter so much. If you look at URLs vs URNs, a URL is resolvable by "default", while a URN can be by having an implied resolution method/path/transport. Even a URL isn't always resolveable if the service is down. I'm thinking maybe a network is defined as a set of peers that agree to use the same resolver or gateway

- use case discussion - who wants to talk about which issues?
- evan: I find that in caching, you can't say "SRI-like ways to reduce the hug of death", maybe just say shared cache or archive, it's too inside baseball and I had to look it up. Anyway, having shared cache/archive for objects is the most important. And then having backwards compat for portocol experimentation is also important to dsicuss.
- ryan: HTTP is somewhere between the main way and the only way for ActivityPub as far as transports/protocols. I think one of the simplest things we can do for v1.1 is to say that other transports exist, and they should be URIs, and you can possibly use them if you want to. AT-uris are an example of such an alternate transport. Re: the bridging use case, I think it's closer to an alsoKnownAs.
- ryan: an important bridging use case is to say "I am also this user on this other server". it might be the main and only one. We are not trying to say "hey I am trying to serve you an Actor over at AT-ur", we are just providing proxy links.
- ryan: another user story - say you have a fedi account and you bridge it to bluesky. We create the bluesky post and we link it back. Clients can look at the original link and do special things. We struggle with updating the original fediverse post and point to the bridged content. Evan and I have discussed publishing annotations that do this but it's complex.
- a: the main priority for me is, as cool as everything here is, nothing will work if servers choke and die on them. Alternative protocols need to prioritized so that at the very least implementations that don't understand them can not choke on them. Then once we have that case covered, we can talk about what to do once you understand things.
- bf: if we loosened the id requirement in a future AP, it would be most useful if people were already using alsoKnownAs or a `url` into maintstream uses
- [a bit earlier] a few people prioritized the use cases:
    a, Ryan: 4 5 3 2 1
    Evan: 1 2 5 4
- more use cases in https://learningproof.xyz/identifiers-and-activitypub/
- eg spam: hash content to find duplicates
- ryan/evan: yes! ...but then are they just hashes, not ids?
  ...can be either/both? can be generated by moderators etc, not just authors
  handling CSAM is an obvious example
- evan: next steps? eg for CG
  WG plans to keep HTTP as SHOULD, but wants to add more language for non-HTTP
- ryan: yes! and then think about how to add something for FEP-fffd proxy links in AS2?
  proxy links vs alsoKnownAs? aKA is great for actors but not other objects. would be nice to use the same mechanism (eg proxy links) for all types of objects
- dmitri: also language for how to use hashes. digests for HTTP?
- evan: HTTP header? Content-Digest
- bf: digestMultibase? property of Link
- matthias: agreed on adding lang for non-HTTP ids to AP 1.1, and also how to gracefully fail/fallback
  also, alsoKnownAs is used widely now, eg by Mastodon for account migration. is that a problem?
- ryan: they could coexist!
- bf: i think so!  i would also note that on a previous call, I said I thought alsoKnownAs was only for actors, with narrower semantics, but no, Dmitri pointed me to outside JSON-LD examples outside of DID-land where it can be broader. across documents, protocols, etc. anything that can have an identity shared across different versions/URLs, you can use alsoKnownAs.
- did:dns? for domain handles
- ryan: alsoKnownAs vs proxy links?
- a: alsoKnownAs is identity, proxy links are url
- evan: WG already decided that it's alsoKnownAs https://github.com/w3c/socialwg/blob/1f4d3f04965080d9467f3410698b3fee7947aaad/meetings/2026/2026-07-16-CG-WG-joint.md?plain=1#L154
- a, darius: technically we just resolved to document it
- bf: FEP-1042 did a very JSON-LD-native form of juggling multiple links, with content type link decorations, to support content-negotiation from static publication pipelines. I think that is a very solid foundation for interop.
  goal is interop!
- a: as:alsoKnownAs is also ambiguous between DID semantics (more of a rel=self, "the link target identifies the current context's subject") vs Mastodon semantics (more of a rel=me, "the link subject and target are controlled by the same entity")
  
Action items:
    - WG lang for non-HTTP ids
    - something about alsoKnownAs and/or proxy links
    - hash usage guidance
