# ActivityPub API TF meeting 2026-02-19

## Present

- Evan Prodromou <evan@cosocial.ca>
- Mayel @mayel@bonfire.cafe
- Darius Kazemi
- Emelia Smith
- ivan @ivan@bonfire.cafe
- Laurens Hof (@laurenshof@indieweb.social)
- bumblefudge.com
- [Ben Pate](https://mastodon.social/@benpate)
- [Django](https://social.coop/@django)
- [Matthias Pfefferle](https://notiz.blog/)
- [Steve Bate](@steve@social.technoetic.com)

## Agenda

1. Progress reports for implementations.
2. Relationship between this TF and the WG.
3. OAuth. What's our strategy?
4. Streaming API. Is the SSE doc the right approach? How do we test it?
    - https://swicg.github.io/activitypub-api/sse
5. Question about Query API

## Minutes

1. Progress reports for implementations.
    - open floor?
    - Mayel: we're doing very simple integration with no testing so far, but prototype client, starting with e2ee, happy to see streaming discussed here, as we've been thinking of a more widely-used way than SSE which we've been using in prototype
        - Evan: is this public? can we look over your shoulder or fork? Mayel: Yup, latest bonfire alpha has it all, and AP code is in this lib: https://github.com/bonfire-networks/activity_pub/
    - Django: i've been working on a client that logs into a few servers and testing: bonfire, WP-AP (PR), Fedbox, pleroma (!!), onepage.pub; got an NGIZero to support this work so it will be ongoing with support (w/Steve Bate)
        - Evan: scope? Django: next time; Evan: public repo? 
    - Ben Pate: //Mayel, working on the server side of the SSE socket, primitive outbox that the client can hit for now, and curious about query API; repo is public but not... ready
        - Evan (in chat): See https://swicg.github.io/activitypub-api/sse ?
    - Matthias: not feature-complete, but trying to triage feedback from Django and deal with the AuthZ part (the clients I've been experimenting all have slightly diff OAuth behaviors...)
        - Evan: Article, Notes, both? M: Originally Notes only, but now accepts whichever the client sends
        - [code here](https://github.com/Automattic/wordpress-activitypub/pull/2851)
    - Steve: Been working on a C2S "toolkit" with django and matthias to debug C2S SERVER behavior, primarily; helps you debug OAuth in detail, display tokens, etc; supports Mastodon-flavored OAuth and other profiles; Browse JSON-LD objects from yr server, with clickable URLs in case of mystery-activities; also helpful for debugging CORS issues
        - Evan: Will share repo hopefully by/at next meeting

3. Relationship between this TF and the WG.
    - Darius: At a high level: WG is more formal and not intended for contribution, new features, new specs; only path is to "bubble up" things, AFTER CG ratifies/versions notes; Notes can be rechartered into scope, although current scope is "maintenance only"; if scope expanded to include new features based on/maturing Notes, a champion who was closely involved at CG stage can represent it as invited expert if not already a W3C member 
    - Evan: C2S in particular has bugs already covered by maintenance mode the people on this call might encounter for the first time

5. OAuth. What's our strategy?
    - Evan: In my thinking so far on [A maximally ecumenical/generic OAuth profile for these usecases](https://github.com/swicg/activitypub-api/issues/1), I have identified at least four different implicit OAuth profiles: 
    - Ben Pate: big fan of CIMD (Evan: implemented both? BP: yup!)
        - Emelia: CIMD helps with the "dead client" problem in DCR (e.g. each instance of a SPA without a secret store registering a "new" client per session); but server-side apps need to track [e.g. AP API] ASs (which are often AS+RSs) for each client, and a unique registration object PER AS, which adds up at scale; side effect: confidential clients need asym cryptos (e.g. privatekey->JWT); 
        - Evan: I've been wondering about draft status/stability of CIMD; Inside scoop from the OAuth WG? 
        - Em: It's not an internet-draft, it's a relatively stable WG draft; since CIMD was designed to be (and remain) Solid-OIDC backwards compat, at least that part is unlikely to change (clients identified by URLs); this backcompat requirement ALSO explains why there are no HTTP headers, and everything has to work with what's in the JSON object per-client (including the `@Context` req, JSON content-type header, convention of ending with `client-metadata.json` to be able to drop that in e.g. user-facing modals, etc)
            - a: seems contradictory to require everything to be in the .json but also require content-type header? also if you use a .well-known uri then the semantics can be encoded into that instead of the content-type, but then you need your own dns fqdn
            - OIDF folks have a competing draft (that uses authN'd HTTPS URLs from a closed federation)
            - ASs generally don't host a CIMD doc-- you host it on the app domain (same domain that does the redirect); mobile app usually hosts it 
            - Em: ATP OAuth spec is a good point of comparison, and the RFCs it uses; the usecase is pretty similar, and it's based on (but takes liberties from) the Solid-OIDC prior art; not directly analogous but similar enough properties
    - Steve: Can the CIMD file be hosted statically? Evan: Yeah I've tested it with multiple clients
    - Evan: My main concern is draft drift, so having a champion in that IETF WG would be great in parallel 
    - Emelia: Mastodon registration is effectively Dynamic Client Registration: https://github.com/mastodon/mastodon/issues/30154
    - Steve Bate: My comment is relatively minor. CIMD requires a server which might be an issue for someone who wants to develop a simple client without hosting a server (maybe there will be CIMD hosting services?). 
    - Django: with the open-ended nature of the properties in the document, will there be a need or use case for a CIMD AP profile?
    - a: more generally re: oauth i think HTTP auth-schemes for WWW-Authenticate and Authorization headers are a good idea to signal which ways of auth are supported. profiling oauth is one step; advertising it as an auth-scheme is a good way to remove ambiguity

6. Streaming API. Is the SSE doc the right approach? How do we test it? https://swicg.github.io/activitypub-api/sse.html
    - Ben: What i'm seeing is that most SSE impls are a "fat ping" approach (open channel and listen to firehose); but I'm finding a "thin ping" is more appropriate, without having to trust delivery in order and on-time; 
    - Mayel: I agree, but we are using SSE just for new e2ee messages; i've also tested it for notifications (eg @ mentions); the fatping might make more sense for a client listening to its full inbox in realtime as an event stream, which we might want to tackle later; a server-filtered stream from the inbox would make mroe sense than streaming it all and filtering it clientside;
    - Ben: I love the collection-bind-ability, i.e. subscribe to this collection; I wonder if the report as written is recommending a different approach than what i'm doing currently; 
    - a: https://www.w3.org/TR/annotation-protocol/#container-representation-preferences
    - Mayel: +1 I think Ben is suggesting it would be good to have two modes, simple ping that's there's a new activity in the collection vs receiving the entire JSON activities via SSE 
        - I'm wondering if some kind of metadata or protocol could communicate expectations-- would it make sense to have both modes declarable/requestable? one request for "single event" or "simple event" and a different request for "gimme an ongoing stream"
    - Mayel: It seems thin ping may be more compatible with Emelia saying: *You need each event to carry `event:`, `id:` and `data:` lines, rather than using the simpler data-only messages to support automatic stream resumption.*
            - a: web annotations protocol has "preferences" for this https://www.w3.org/TR/annotation-protocol/#container-representation-preferences using HTTP "prefer" header. thin ping maps to "minimal" or "iri only", fat ping maps to "embed descriptions", but fat ping needs to be reasonably complete and also trusted.
            - Evan: Reuse AS here? There's also some LD options, URL versus complete object? Ben: That makes sense, just send URL (by ref); if there was a protocol for asking "did this update" and getting a boolean back, that'd be the easiest, but maybe there's something else that can be just as simple
            - a: there's ways around "thundering herd" -- since this is streaming and therefore can never be static, why not have it be a single endpoint that allows setting these preferences for representation and topic(s)? solid also reuses AS2 here.
            - Mattias: How is this diff from WS? Evan: SSE is unidirectional, WS is bidirectional; also SSE needs less help traversing (e.g. firewalls); M: Is it pure HTTP? Ev: I think so? just never EOFs, keeps sending; Matthias: PHP will hate that almost as much as it hates websockets; 
            - Ben: Yes.  SSE is a part of the HTTP protocol, and built into all browsers now. I'll add that SSE is a LOT easier to implement on the server. 
            - a (in chat): sse > ws(s) imo unless you really need bidi 
        - Evan: Next steps? We could iterate the draft in parallel, or just pause that and implement freely and return to specs after lessons learned/compared? Ben: I'm going pretty quickly, I already had SSE so I can share some opinions on next call;
           - Mattias: I can implement quickly but debug slowly, and it helps me have a detailed usecase (and a working client) to build against with more confidence it'll get used; Evan: I will say people have been asking for push-based updates (eugen ranked it high in his critiques); 
           - Django: For a "thinping" usecase, I would love to see a use-case written up; happy to try once it's 
           - Mayel: I can see one usecase for thin: Following feed open in client, thickping, but also [DM] notifications thinping open as well, passively listening and polling periodically.
           - Mayel: we're integrating to some 3rd party apps, incl Lauti (sp?) that doesn't federate but WILL do C2S after authNing our the bonfire server's user which then federates it; but how can the server push incoming remote events (eg. from Mobilizon) to Lauti updates ?  
7. Question about Query API

## Emelia's notes on Streaming (async)

For streaming, it really depends on the bidirectionality that may be required. The other thing that you *will* need is a form of stable cursors for "events" — for instance, if you're subscribing to say the inbox over Websockets or SSE, every activity that comes in will need a time-ordered ID which can act as your cursor. (In AT Protocol, they use auto incrementing bigints for this purposes, in FIRES I used UUIDv7). The stable cursor is important, because it allows for resumable subscription. For example, you have a stream of events A, B, C, D, E, F. You client gets disconnected due to network fault (e.g., mobile spottiness) after B and then reconnects at the time of E. If it reconnects purely to the live events, then the client will only have events A, B, E, F. With a stable cursor, and each event containing that cursor, when the client reconnects it can say "give me events newer than B", the server would then flush a buffer of events from B to E (the current live event), and then continue with emitting events as they happen.

SSE supports this type of reconnection out of the box, as long as you use event IDs, and the serve implements this cutover from recent events to live events. Websockets *can* support it, but you need to vary the connection URL on reconnection to include the latest cursor.

https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events#event_stream_format

On the SSE proposal, the JSON blob would just be on one data line, not multiple:

```
data: {
data:   "@context": "https://www.w3.org/ns/activitystreams",
data:   "type": "Add",
```

You need each event to carry `event:`, `id:` and `data:` lines, rather than using the simpler data-only messages to support automatic stream resumption. Using `id:` allows for this automatic resumption of where you were at, as the last known `id:` will be sent to the server automatically on reconnect via Last-Event-ID header: https://html.spec.whatwg.org/multipage/server-sent-events.html#last-event-id

Both server-sent events (SSE) and websockets **do not** allow setting the Authorization header, which is required by OAuth Bearer Tokens or OAuth DPoP Tokens. You'll probably want to look at the Solid Notifications Protocol, which solves this by have a POST request first, which then returns a signed URL for the event stream or websocket URL to connect to:

- https://solidproject.org/TR/notifications-protocol
- https://solid.github.io/notifications/eventsource-channel-2023
- https://solid.github.io/notifications/websocket-channel-2023

## a's notes re: Streaming Events

- per example 1: event stream on Note? event stream on *every* Note? this makes more sense on the collections maybe
- it feels like this should be a specific endpoint that takes a "topic" more like WebSub
- solid has a lot of work here that seems highly relevant, especially reading the user stories of the AP SSE draft here
	- https://solidproject.org/TR/notifications-protocol has multiple channels
		- javascript EventSource API (connect to event source URI) https://solid.github.io/notifications/eventsource-channel-2023
		- linked data notifications (POST to inbox) https://solid.github.io/notifications/ldn-channel-2023
		- websockets https://solid.github.io/notifications/websocket-channel-2023
		- http streaming https://solid.github.io/notifications/streaming-http-channel-2023
		- webhooks https://solid.github.io/notifications/webhook-channel-2023
- i see emelia has gotten to similar points re: robustness and reliability