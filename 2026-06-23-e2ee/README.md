# ActivityPub E2EE Task Force 23 Jun 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
- Mallory Knodel <acct:mallory@socialwebfoundation.org> // Github:[@mallory]
- bumblefudge
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- Ben Paate <@benpate@mastodon.social>
- Claire
- Charles Iliya Krempeaux <acct:reiver@mastodon.social>
- @mayel@bonfire.cafe

## Agenda

Introductions/administrative
- https://www.w3.org/community/about/process/cla/
- https://www.w3.org/policies/code-of-conduct/
Progress and implementation reports
- [Issue #56: Maintaining ordering in the group conversation](https://github.com/swicg/activitypub-e2ee/issues/56)
- ["Remove Self" from group + decomission device #80](https://github.com/swicg/activitypub-e2ee/issues/80)
- #65 verifying additional devices actually belong to the actor (signing of actor's key packages) / Multiple Devices: Adding New Devices for an Actor
- internal IDs: mls:// or ap-mls:// instead of uri:uuid: ? + ap-mls:// as a standard way to open a client at a particular group/thread/message

Jitsi: https://meet.jit.si/activitypub-e2ee
Time: 16:00 UTC | 11:00 EST | 8:00 PST

Add comments below to modify or add to the agenda.

## Notes

Progress and implementation reports
Bonfire / Emissay interop: To wrap or not to wrap (MLS and AP). Implicit create (AP).

### [Issue 56 Maintaining ordering in the group conversation](https://github.com/swicg/activitypub-e2ee/issues/56)

- Mayel: Part of the issue is who canonicalizes/orders state-- group actor would help, or some other kind of service to coordinate?
- Have discussed group actor in the past, not
- How are we handling ordering the messages in the groups?
- Use a collection, as with threading in ActivityPub
- Use a group
- MK: use the MLS epoch/commit data to handle ordering strictly, don't fall back to a AP Ordered mechanism which could be outof sync from it
- BF: would it be possible for a "strong client" to send messages directly? (maybe this only works if the client is NOT the "group host" or running the "dataserver" thing)
+ Evan - we've adopted a S2S message envelope/routing thing, we haven't really been tracking that
+ Emelia - could the data server just canonicalize order? could other users call it for ordering?
* MK: Ooh, i'd have to look into the specific libraries, i'm not sure
* In chat: (Ben: Emissary is using mls-ts, Bonfire is using OpenMLS)
* Ben: I think the trick is how often do i check the ordering, whether it's an OrderedCollection or an MLS-specific thing? Wouldn't it be better for commits to be routed through a central broker/service? it could be a group actor or some other thing
- Evan: but in vanilla/cleartext AP, convo originator gets copy of every message; I don't think this helps _ordering_ but i think it might help with the user metadata leakage issue; maybe consider separately?
- Emelia: [Mark's dMLS i-d](https://datatracker.ietf.org/doc/draft-xue-distributed-mls/) does this with a delivery server; 
- Evan: I am not sure it's a good fit, germ/dMLS uses its own authN and delivery channels after authNing the atproto handles, and that's a valid possible architecture for bootstrapping to a distinct network, but i don't think we can do that without starting over
- MK (in chat): Buffering requirements should depend on epoch and commit status, or whatever you can get out of ts-mls. Everyone gets the same information as Evan is describing so every client should be able to recreate the same convo thread.
* MK: there might be good reasons to use Group on the AP layer, or not, but AS LONG AS the native MLS ordering is used, you leave open the maximum interop options
- Sidebar: MK: Metadata leakage - i think routing info is kind of an inherent thing of MLS? not sure we can do too much to minimize it - [Issue #83: Limiting group membership metadata exposure](https://github.com/swicg/activitypub-e2ee/issues/83)
- Emelia: but leaking user metadata is worse than just leaking server-to-server comms... 
- MK: sure
+ (close sidebar, back to issue 58)
- Evan: Consensus to use Context? <no objections>





[Issue #80: "Remove Self" from group](https://github.com/swicg/activitypub-e2ee/issues/80)
- Issue with MLS: Leaving a group requires everyone to agree.
- Ben: stampede/ordering lag if many people in a big group hit that "approve" button in the same 20 seconds?
+ emelia: don't they all get ordered when they hit the host's server (who controls the group) anyways?
+ emelia: IIRC the sequence is public/outside the envelope for this reason, for the delivery server to accept them in order
+ ben: wait, in my impl, i think i'm committing to the local dB before getting authoritative ACK from the delivery... i could maybe solve this by handling it as unconfirmed until ACK
* Em: think of this more like AP C2S than APS2S: until you hear back from the server, you don't have a canonical `id` for the activity/msg commit id/etc
- mayel: is this downstream of #56? 
- evan: i think so
+ evan: if everyone defers to the host's OrderedCollection, the host's acknowledgement of a leave message could be
- sidebar/factcheck: if i get 5 commits, and only 1 gets in, do i just ignore the other 4? 
- ben: I think so; 
- em: me too
- Evan: I'm marking this as a Sub-issue of 56, solution seems to shake out from that solution AFAICT
- Can ignore later commits

[Issue ?? - KeyPackage trust model and emoji verif system]()
- Mayel: "mark as verified" (//Signal?), or flag in client if KeyPackage replaced or updated by a server?
- Evan: A good example: Servers might try to insert keys to "keep a copy" or join a convo, or rotate a user's key; want to persist trust (keep accíng msgs from) "emoji-verified" users until/unless they rotate devices/keys;
- Evan: is the signature persisted with the keypackage or lost? `client signature key` is inside the package, and persists across the rotations of the group's sharedkey; 
- Ben: Yeah, can't new device sign over the keypackage and then it's visible to the group and verifiable, but also displayed as an event? 
- Mayel: Yeah I think as long as there's a non-approved-by-old-device recovery i'm good
- TallTed: lots of good info in chat? 
- BF: I've been getting most of it, i'll paste the raw chat into the bottom and double-check that i didn't miss anything too pertinent later, but i gotta run now!


me says:😀
17:01
EP
Evan Prodromou
Evan Prodromou says:https://pad.w3.org/p/ActivityPub_E2EE_Task_Force_23_Jun_2026
17:01
M
Mallory
Mallory says:I should also disclose that I'm a consultant with WhatsApp and Signal.
17:08
0
0xllx0
0xllx0 says:no sorry
17:11
EP
Evan Prodromou
Evan Prodromou says:https://github.com/swicg/activitypub-e2ee/issues/56
17:15
me says:matrix-style?
17:16
me says:(i'm still team #requireGroups 😄 )
❤️
17:17
Emelia Smith
Emelia Smith says:just seeing that you're using the w3c note taker, if you want I can give you an account on https://notes.socialcg.org/
17:19
Emelia Smith says:Is this meeting being recorded? I'm not seeing a whole lot in the notes?
17:21
me says:but then the client would have to re-check the Collection in realtime
17:23
me says:if there was a counter, it would know when it has to backfill/compare notes with the canonical collection
17:23
me says:👍
17:25
me says:i could do it
17:26
Mayel @ Bonfire
Mayel @ Bonfire says:see comment from a matrix dev in that issue above:  It's not just about needing an ordering to the messages, but you also need to ensure that everyone receives the messages in the same order. (This includes ensuring that senders know, at the time of sending, that their message comes after someone else's message.) Because the purpose of the ordering in MLS is that Commit messages that are sent "too late" are discarded. But if someone has already applied the Commit, before they find out that it should have been disregarded, they'll be unable to participate in the group any further.  For example, if Alice and Bob both try to send a commit message based on the same epoch (say, Epoch 1). Alice's message is ordered first, but Carol receives Bob's message first. When Carol receives Bob's message, she applies Bob's commit, giving her an Epoch 2. At this point, she throws out the Epoch 1 epoch_secret, because MLS requires this for forward secrecy. She then receives Alice's message, which she find out should have been applied instead of Bob's, but since she already threw out the Epoch 1 epoch_secret, she can't create Alice's Epoch 2.
17:26
me says:i didnt volunteer earlier cuz i thought i would be interrupted a lot
17:26
me says:but i think i'm good now
17:26
M
Mallory
Mallory says:Yes!
17:28
Mayel @ Bonfire
Mayel @ Bonfire says:yeah we're talking about the group starter's instance being the data server
17:31
Mayel @ Bonfire says:are you talking about not federating and having every client connect to the same server? (meaning clients who have to connect to up to N servers if they're in N groups started by different people)
17:32
BP
Ben Pate
Ben Pate says:Emissary is using ts-mls
👍
17:33
Ben Pate says:And Bonfire is using OpenMLS
17:33
Emelia Smith
Emelia Smith says:It's related just through how the  architecture of data servers usually is, so by not following that path we get a lot of issues like out of order messaging
17:35
Mayel @ Bonfire
Mayel @ Bonfire says:https://fediverse.codeberg.page/fep/fep/171b/ is only done by hubzilla IIRC but that's what I'm proposing
17:35
Mayel @ Bonfire says:so not quite well trodden by the rest of the fediverse
17:35
Mayel @ Bonfire says:(ah and mitra)
17:36
Mayel @ Bonfire says:hum not always
17:37
M
Mallory
Mallory says:Buffering requirements should depend on epoch and commit status, or whatever you can get out of ts-mls. Everyone gets the same information as Evan is describing so every client should be able to recreate the same convo thread.
17:37
me says:it's so confusing
17:39
me says:there are two dMLSs
17:39
me says:https://datatracker.ietf.org/doc/draft-xue-distributed-mls/  Distributed
17:39
Mayel @ Bonfire
Mayel @ Bonfire says:but thats centralised
17:39
Mayel @ Bonfire says:despite the name
17:40
me says:no, it's DISTRIBUTED
17:40
me says:😄
17:40
me says:dMLS (and the other dMLS) are two different profiles of MLS
17:44
me says:yeah i'm most interested in the interop question-- can a user of some other MLS client join a group without an AP account?  (this is maybe more fundamental than the Group wrapper)
17:45
Emelia Smith
Emelia Smith says:Yeah, it's this one which described a delivery service that is distributed: https://germ-mark.github.io/distributed-mls-id/draft-xue-distributed-mls.html
17:45
Mayel @ Bonfire
Mayel @ Bonfire says:@malory what do you say to the comment by uhoreg? (pasted above)
17:46
EP
Evan Prodromou
Evan Prodromou says:https://github.com/swicg/activitypub-e2ee/issues/83
17:46
BP
Ben Pate
Ben Pate says:@bumblefudge. Probably not. Even if the addressing worked, the message content would still contain ActivityPub inside the MLS envelope
17:46
M
Mallory
Mallory says:Then the group question becomes a choice rather than a spec-- the specification can prescribe what to do for both cases and the third case in which they interop.
👍
17:46
Mayel @ Bonfire
Mayel @ Bonfire says:doing a pending commit yeah
17:51
Mayel @ Bonfire says:yep, but that's why we need to be able to follow the group, because we don't want the client to be check N servers
17:52
me says:it's like c2s except it's someone else's S, not yours, hehe
17:52
me says:(unless you're the group host)
17:53
Mayel @ Bonfire
Mayel @ Bonfire says:but you might be in 100 threads
17:53
Mayel @ Bonfire says:you don't want to pull
17:53
me says:that's why mark's draft is called distributed MLS, because each thread has a different server 😄
17:53
me says:IN A HEAT WAVE
17:53
me says:(i am also melted, em probably too)
17:54
Emelia Smith
Emelia Smith says:I'm in the same city area as @bumblefudge and I'm fine because I bought an AC 😂
17:55
Emelia Smith says:I think the other four would fail to commit on the server?
17:55
me says:yeah this happens at the MLS layer, not the AP messaging layer, right? to mallory's earlier point about keeping MLS semantics canonical
17:56
Emelia Smith
Emelia Smith says:Also, for transparency I will be publishing this report I had generated almost two months ago as a review of activitypub-e2ee: https://writings.thisismissem.social/p/a6dacec6-90c7-45d8-9b70-fe896ce16ec4/?member_status=free
