---
title: ActivityPub API Task Force 19 Mar 2026

---

# ActivityPub API Task Force 19 Mar 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Steve Bate <acct:steve@social.technoetic.com>
- nigini <@nigini@social.coop>
- Darius Kazemi
- Fred Hauschel @naturzukunft2026@mastodon.social 
- a <trwnh.com>
- Django <acct:django@social.coop>

## Agenda

1. Introductions / administrivia (5 min)
2. Progress reports
   - ap https://github.com/evanp/ap
   - OAuth profile sample code https://swicg.github.io/activitypub-api/examples/oauth/index.html
   - ActivityPub C2S Toolkit Repo https://github.com/steve-bate/activitypub-c2s-toolkit

3. Using activitypub.space or socialhub.activitypub.rocks as a discussion forum
4. Filtering collections
    - #13 https://github.com/swicg/activitypub-api/issues/13
    - #14 https://github.com/swicg/activitypub-api/issues/14
    - #15 https://github.com/swicg/activitypub-api/issues/15
5. Autocomplete search
    - #24 https://github.com/swicg/activitypub-api/issues/24
    - https://swicg.github.io/activitypub-api/autocomplete

## Minutes

2. Progress
- Evan: Changes to ap project: OAuth update to do recovery using server metadata.
- Link to project for testing https://swicg.github.io/activitypub-api/examples/oauth/index.html
- Steve Bate: updates to client implementation
    - bumblefudge: how does it compare to browser.pub
    - steve: have not use browser, but this one goes in depth on all the AP exchanges.
    - bumblefudge: indeed looks like you are working on something more broad.

- Django: working with Matthias on a Branch for the Workpress plugin. Learning: working with State is challenging. EG. having to look for likes in different collections is super inefficient. (still not openly available).

3.
- Evan: is using these space something we want to use in this group?
- Bumblefudge: what for? don't people like Github?
- Evan: spaces are new and if we don't have needs we can wait to see
- Darius: 
- Bumblefudge: considering the very technical work that usually needs to refer to code, I'd say Github feels more appropriate.
- Evan: One thing: it is not federated. We are not entirely dog fooding the conversations. We may want to get someone to implement a one-way federation. (Steve, on comments: Email federation)
    - Darius: there are issues-to-rss and rss-to-AP tools... seems byzantine but possible


4. Talk about filtering and see what to do about it:
- Evan created these stories:
    - User story: filtering by member type
    - User story: filtering by activity type
    - User story: filtering by object type
    - These are very specific stories and I want to talk about architecture. Good to talk about fine functionality that which allows for people to pick and choose to support.
    - Fred has proposed and implemented a FEP that does more than these
- Ben: Have lots of opinions about this! There are very specific languages we can implement this. I can think of at least three other functionalities. There is a bunch of places we'd need these, and my take is to look for a balance between super specific and super generalized.
- Bumblefudge: I compare the current FEPs, and I can see it would be very hard for servers to implement them: I'd say, start with the easiest lift of the four proposals, but I can't see an intersection between them; is the GET queryparam approach a kind of simplified version that bridges between two diff kinds? I can see clienst and servers that already use RDF or JSON-LD natively preferring NaturZukunft's RDF-y QL, but that would be hell for very JSON-only implementations...
  - a: is it really, though? "JSON-only implementations" don't often work directly with JSON, they transform and store entities in SQL databases (or SPARQL if you like RDF :p)
- Evan: I can see something like GraphQL+Clients that can facilitate implementations. Basically, having code that can do the chunk of the parsing, and implementers can focus on the higher level functionality. https://www.apollographql.com
- Steve: JSONPath has libraries in most langauges that will turn these queries into an AST; i've tested some out, seems p uniform across languages
    - Darius: SQLite and other SQL backends have JSONPath native translators, so client can send JSONPath and server can run "SELECT * WHERE (<JSONPath-expression>)"
    - Evan: modulo sanitation, right?
    - (post-hoc addition from Darius)Yes it's more like SELECT JsonPath(<query>) FROM tablename WHERE [insert your appropriate access limitations]
- Evan: Could we implement the specific use cases with the general query languages?
- Steve: My FEP has an example for each C2S filtering usecase
    - Bumblefudge: I've seen that and I appreciate the ergonomy of the work: It makes the client much simpler to write. Very good for the simpler queries.
- Evan: summary, good feelings about the JSONPath but there is work to do on more exploration and implementations. The risk: explorations may get to a deadend, so people need to be comfortable with that.
    
5. Autocomplete: (Evan) which could be seen as part of the same conversations if we have a general enough query language.
- Typical autocomplete: adding while you are writing a post. Another case is ... 
    - Proposal: https://swicg.github.io/activitypub-api/autocomplete - very simple (and not very powerful) from the client side.
    - Steve: has proposal https://codeberg.org/fediverse/fep/src/branch/main/fep/f011/fep-f011.md
    - Evan: this is not a standard language, right?
    - Steve: not that I know. It's based on ??Lucene?? (https://lucene.apache.org/core/2_9_4/queryparsersyntax.html, https://www.elastic.co/docs/explore-analyze/query-filter/languages/lucene-query-syntax)
- Evan: Discussion... are there other approaches? I know that other systems have specific endpoints for these searchers... they respond in under 100ms, technically hard.
    - Ben: I have implemented this beautiful language but the DBAs hated it because users could search for everything. Example to support we need to specify fields that users can search for... there is no way we can index everything.
    - Bumblefudge: Typeahead nowadays is often implemented clientside from a preloaded collection or map-table for usernames/handles, email addresses, and categories/issues/pullrequests/etc to be responsive enough to be useful.  full-text/search-field typeahead, yeah, you want an API for but it's expensive and not always justified for every client/server pair 
    - a: basically the tradeoff is: index size vs network latency. you could index like 100 contacts, or index 10,000 people your server is aware of, or you could have a huge index for the broader social network of millions of users? There is a slider here, and we could support both approaches: a graph or index that the client can load for lower-scale use cases, and a service endpoint for when the index is too large and the network connection is fast and stable enough.
    - Evan: You have your social graph... I think thousands of followers is a usual size, and I don't think querying this scales well. .... I feel that doing the sync and the query would put a lot of weight to the client.
    - Darius: one good design goal for this usecase would be that it could happen anywhere (clientside, serverside, microservice) (analogy to how Mastodon is using Elastic Search)
    - Bumblefudge: this is composable and optional, right. it would be desirable to have something that can be delegated to a microservice or run in a service worker but also important that it's not mandatory and doesn't _need_ to be in v1.0 of everyone's C2S launch date.
    - Evan: I feel like that more exploration and implementation is needed.

### Next Steps and Action Items
    
[Baseline profile](https://github.com/swicg/activitypub-api/issues/54) - For next month: discuss

