# 2024-06-20 SWICG Portability TF Call

* https://www.w3.org/events/meetings/d83b5200-20aa-49c3-a1d0-851392df2f53/

## Participants

* Lisa Dusseault
* Dmitri Z
* Bumblefudge
* Bob Wyman
* [Ted Thibodeau](https://github.com/TallTed/) (he/him) ([OpenLink Software](https://www.openlinksw.com/))
* Tantek Çelik (he/him, https://tantek.com/)

## Agenda

Discussing https://swicg.github.io/activitypub-data-portability/lola.html

* Source servers redirecting object requests
* Externalities - servers DDOSed
* If we have time - OAuth model

## Redirects

Lisa: One goal is to make object redirects work OK for Web browsers. Folks might keep a link around for a year or so, and then try to `GET` it and find that it has moved.  The proposal in LOLA is to use a `301` and an approach that ought to work with existing browsers.

bumblefudge: Clarify that this happens in "phase 3" — some time after the content has been copied, a redirect may be set up.

Lisa: Yes and it's possible that it's never set up or that I suppose somebody could come up with a use case where a redirect is set up but a copy never happened.

Dmitri: I believe this requires the `alsoKnownAs` bidirectional link on the Actor to be set up in advance.

bumblefudge: Is `previously` new?  Yes, it is.

Bob: Can `previously` be used to hijack other peoples posts?

Dmitri: No, because it requires bidirectional links. (The Actor object on the previous instance needs to have an `alsoKnownAs` link set up pointing to the _new_ instance.)

Lisa: TODO here for me is to document that threat and that requirement.  It's fine for the browser to follow the link from the source to the destination and not check the bidirectional links, because they're following...

Bob: Can somebody else copy all the content over and get accepted as the new location?  If I copy Lisa's content and use the `preivously` value, does that get taken as a replacement?

Lisa: Yes, that is a threat if agents don't also check the `alsoKnownAs` value.

bumblefudge: We have a network connectivity problem.  If the Actor stays up, OK, but if that server goes down or isn't hosting that Actor any more, that bidirectionality breaks.

Dmitri: Yes.  We're scoping this to "Live online accounts", so yes, it does require network connectivity. The only way to do this without servers staying up is cryptograqphically.

Lisa: Not the only way; it could also be done with a registry of validated moves.

bumblefudge: Should the spec detail what the Actor looks like, if it's set up to be a redirect/tombstone?

Lisa: TODO for me: explain in more detail what an actor looks like after redirects are set up.  Also, I think we can do more to explain what 3rd parties should do IN CASE they can't verify the bidirectionality — it probably involves a mention of signing (without a dependency) and/or a mention of checking with the 3rd-party's initiating user before assuming the `previously` value is valid.

...

bumblefudge: It's worth laying this out algorithmically.  If, then, drop it, escrow it, don't let it corrupt your cache....

Lisa I'm trying to think whether this process needs to be followed if the 3rd party is just browsing content.  Or only needed if the 3rd party is trying to do something because of `previously` values.

Bob: Does this create a storm of requests?

* a very popular post exists on a server
* Another server creates a post that has a `previously` value that refers to that very popular post; it gets published
* now many other entities hit the first server to verify

bumblefudge: This strengthens the need for chunking
Bob: Or does it just prolong the storm...
Ted: batching 100 requests to validate posts

Lisa: But we're not validating posts one-by-one; we're validating that the Actor moved.

Dmitri: Posts are bound to the actor...

Lisa: So we may need to include the Actor URL in the `previously` value, an object ID like <https://my.example.social/all_posts/1234987698138> could have an actor name like <https://my.example.social/actors/alice> — you can't safely infer the actor ID from the post ID.

Dmitri: We should check whether the object ID allows you to get at the actor ID.

Bob & Lisa: It's an implementation detail, not a requirement, when implementations happen to build an object ID on top of the actor ID.

bumblefudge: It's an inherently hard problem when the old server is down.  A 3rd party shouldn't recognize a migration between server "B" and server "C" if the old server ("B") is down, no matter what server "C" says.

Lisa: There's something we're going to have to learn from implementers when they actually get around to implementing awareness of `previously` — knowing exactly why they need to trust it, what they are trying to solve.  TODO - call to implementers

bumblefudge: Whether they're updating their caches...

Bob: What about replying to the old post?  Does that get linked to the real moved post, or to the more widely distributed post that pretends to be previous?

Lisa: But the old post is gone — it's impossible to stumble upon and reply directly to the old post, no?

Bob: But the old post might be in the cache.

Tantek: For instance, I'm off camping all week with a complete static cache of people I follow and I can queue up replies and posts. When I connect up again, these are now replies to the old server's posts but some of those are gone because people moved.  From my perspective this should just work — my intent is to reply to the post I saw, not necessarily a post that's been migrated or edited etc.

bumblefudge in chat: tTe offline-enabled client would have to be attentive to the `302` from the old server.

Lisa: But does the replying post always actively re-double-check the post it's replying to? There are always race conditions where the thing you're replying to can disappear just as you're replying to it, so what happens today with that race condition?

Tantek: From my perspective, if I have a quote from the thing I'm replying to and the URL of it, I'm done.  It may turn out that the `in-reply-to` URL is to a server that's gone.

Lisa: If that's fine, then I think it's all fine.  Not all likes or `in-reply-to` links work.  The fediverse is a mess of links, not all of which work.

Bob: So that we're clear: a user can reply to a post and have nobody see their reply.

Tantek: Yes, and that's OK.  It can already happen.  Somebody can transfer their content to some place you don't like — your reply doesn't need to point to the new location on the place you don't like.  It's safer for the user if we maintain what they thought they replied to.

Lisa: So on the whole, is it best NOT to fix up like and reply URLs when the thing moves?

Tantek: It is better to preserve what the user saw.

Bob: Is this like the case where a poster can say something bad; I reply that they're an idiot; the author changes the original post; and now I look like an idiot?

Tantek: Yes.  This happens already with webmention.  When you do a careful job of replying, you include quotes of what you reply to, and if the original poster changes, other people can see that.

Ted: Also see, good NNTP and email reply patterns.

Bob: This works less-well in `activityPub` where the current consensus seems to be to not like quote-posts.

Tantek: To be clear, quote-posts are when somebody quotes an entire post, whereas I'm talking about quoting text explicitly in the contents of a post, like email reply patterns.

Bob: This is outside the scope of ActivityPub.

Tantek: People blockquote in the contents, e.g., markdown with `>` symbol... Also HTML `blockquote` tag has a cite attribute feature for semantically linking to the origin, possibly including a text fragment of the specific quoted .

## topic of DDOSsing as many people move

Lisa: DDOS on source: throttling is the answer, I need to say more in the spec specifically.  DDOS on destination: even easier, the destination could for example limit the amount of account-copy jobs it is currently willing to accept from users, and other jobs get rejected until it has more resources.

Bob: Should source servers round-robin? Should they complete one at a time?

Lisa: It's not our job to write the specification to say that; implementers need to figure out what works. The spec just needs to say what status code.

Bob: So do 3rd parties get confused by a slow migration in process?

Lisa: no, because 3rd parties are not notified until a redirect gets set up, and that redirect setup on the source server is instant; it can happen asynchronously with the content copying.

Bob: So is it wrong to set up the redirect before the copy is finished?

Lisa: Kind of, yes.  It's certainly not the ordinary intent. But it could happen — a user could have a narrow window granted by administrators to move their account, and might ned to set up the redirect before it finishes  Perhaps we should recommend that the destination move data in reverse chronological order, so the most interesting things can be copied first? or that the destination should lock the content until it's fully copied or otherwise marked "done" ?

TA.(aside: this is where something like Manton's "Blog Archive Format" can help)
Lisa: TODO add an out of scope section — export, signatures
