# Private Groups in ActivityPub

Breakout at TPAC 2026

## Present

- Evan Prodromou <evanp@socialweb.foundation>
- Darius Kazemi (scribe)
- Bert Bos (W3C)
- Dmitri Zagidulin (https://interopalliance.org)
- Jean-Guilhem Rouel (W3C)
- Nick Doty (CDT)
- Sarven Capadisli <https://csarven.ca/#i> ( @csarven@w3c.social )

## Agenda

- Presentation by EP
- Open discussion
- Issue triage in groups repo

## Presentation (Evan)

- https://docs.google.com/presentation/d/1atNEHw46OxF1HACISW-jyQyJL0yKUrGBcw45DwjHVtg/edit?usp=sharing

Overview of how private groups are working now, where we are in the process, go to next steps.

By private groups, we mean -- a difficult part is deciding what a group is in a social network structure. A group is opt in. It has a concept of membership. There's a hub entity, a group, that people have a relationship with rather than a person-to-person mesh. Group ownership can be transferred, and there's some delegated authority to some number of members of the group in terms of moderation, making group settings, and so forth.

Facebook groups, Reddit subreddits, Discord or Slack channels, etc, are examples of the kind of thing we are aiming for.

We have something around 25-30 user stories around groups. Membership (joining, leaving). Lifecycle, Posting, Collections, Moderation.... there are a lot of functions that are "hidden" to a user but do exist in say a Facebook group.

Social Web Incubator Community Group is working on this, via the Groups Task Force. We have a Github at https://github.com/swicg/groups

### Where are we so far

ActivityPub is based on Activity Streams 2.0 which gives a social vocabulary of nouns and verbs, including "Group".  Actors (Person, Organization), Content Object (Note, Article, Image), Collections, Activities (Create, Update, Delete, Like, Follow...)

ActivityPub is a protocol that uses Activity Streams 2.0 (AS2) as its data structure. We tie resources to the Web where we say Objects are Web resources with AS2 representation and HTTPS IRI identifiers. Activities change the state of Objects. Actors have inbox/outbox endpoints where you can receive/send activities. Social graph is directed, not bidirectional. There's a client to server API, and a more popular federation protocol that's server to server. In AS2 vocab we describe 30 Activity types, but only about ~8 have no ActivityPub side effects.

There is not much group support in published ActivityPub. There are gestures toward it via AS2 which has a Group Actor type, and Activity types such as Join, Leave, Invite. There's no guidance for this at all in AP 1.0.

One way people have implemented groups is through addressable collections. A Collection is a sequence (ordered) or bag (unordered) of objects. "Andrew creates Collection "Model Train Fans", Andrew adds Blair, Charles, Donna to "Model Train Fans", Blair addresses the set of Actors in "Model Train Fans". This is easy to implement and already specified, but it's managed by one person, not opt-in, not clear which server unpacks the collection.

Addressable collections give us maybe 10% of our user story coverage.

A second option is FEP 1B12, Group Federation. It's a community spec that grew up organically among implementers of AP. You have an actor of type Group, and any time you mention that actor, the Group repeats via an Announce activity. So you just follow this Group entity that is effectively a relay for messages it is tagged in. Pros: easy to implement, actors look and behave like any other account on a service. Cons: moderation is tied to home server, doesn't use special activities like Join and Leave, following the account means you are a member of the group, it's possible to address followers-only to reduce public nature of posts but it's mostly implemented as a fully public sort of relay for boosting messages.

Another implementation is MLS in ActivityPub. MLS is an end to end encryption standard from the IETF. Social CG has been working on implementing MLS for e2ee. MLS treats group membership as a central part of the mechanism and has join, leave, invite verbs in its vocabulary. Pros: everything encrypted and private. Cons: everything is clientside, no durable record of the group, not browsable or searchable, can handle about 100 users how we've implemented it, and it's hard to implement though there are libraries.

We've come up with a few other options.

Variant 1: "Join and Leave". An Actor has a groups collection, and belongs to a members collection that is related to the Group and has a posts collection. This uses the AS2 Group schema, state is handled mostly in collection membership, managed mostly through ActivityPub and federation. Con: it has a rigid structure which may be a fatal flaw. Open questions: who are the Create activities addressed to? Do we send them to the Group or Group members Collection? Is it 1B12 compatible? If so are Follow and Join the same? How do we manage an application queue for members?

Variant 2: Membership object. This reifies membership into an object in its own right. An actor has a Membership and that goes into a members collection instead of the Actor directly belonging to the members collection. This means you can update membership in a group and handle the state there. Pros: Membership state is reified, Membership can hold extra information like a group-specific avatar and nickname. Cons: Extra level of indirection, not AS2 native, Object ownershpi is tricky, may require extra endpoints outside of AP to work correctly. Open questions: do we use Join/Leave? 1B12 compat?

In both variants, permissions are important. There is a permissions structure that was implemented by GoToSocial - it's an advisory permission structure. canJoin, canBlock, canCreate - more of a policy declaration than an authorization mechanism. 

Consensus in our task force: exercising democracy and bottom-up participation is important. Most group structures tend to have a techno-feudal structure where the platform is the monarch that grants admin powers to individual users.  We want to know if we can handle non-heirarchical decision structures in these groups. Can we do voting-based moderation decisions, etiher among a group of moderators or all users.  Ex: 2/3 of all members decide to kick out an unruly member. This is important to the TF and also could be advantageous as a draw for users from other platforms. Potentially disadvantageous because we'd be a standard requiring a certain social behavior rather than enabling behavior that's already out there. I htink we want to bulid the standard so it's able to support democratic governance but not require it.

"At risk" user stories include browsing and searching messages. Group collections as well have not seen much discussion within the task force.

## What next?

TF needs to choose a variant from the above. We may choose a variant before or after implementation. Seems likely we'll see an evolution from FEP 1B12. Implementations -- Bonfire and assembly.pub are working on this. Mastodon has said they may begin working on this 2027-8. I'd like us to have something that Mastodon can implement before it hits their roadmap.

Next step would be publishing a Draft CG Report in the Social CG. Then publish a Final CG Report. Not possible to get Groups stuff into AP 1.1 but maybe 2.0, though it's possible to just leave it as an extension.

Dmitri: is there hope for variant 2? And do groups have inboxes as well as outboxes?

Evan: Yes, in both variants, groups are AP actors with inbox/outbox.

Dmitri: Okay, is variant 2 a realistic option?

Evan: A likely path is implementers start with FEP 1B12, and then add features that implement user stories like moderation. I think it's hard to introduce the Membership structure into that. The first variant is more popular with implementers and the second variant is more popular with our architects and commenters. Sometimes running code wins. There's not no hope but there's some question as to whether we can get there.

Dmitri: is there a tracking issue?

Evan: I'll make sure there is one and will share.

Darius: Can you comment on Signal style groups vs the open world forum style groups?

Evan: I think the MLS work is more for the Signal style groups which is a very private structures. Forum-style would be something where you might look at someone's profile and see the groups they are in and then go check them out. There would be a discovery mechanism. 

Hometown-style Local-only posting (from Darius' Mastodon Hometown fork) -- but really looking for something more like groups, but there was an easy way to create a change to Mastodon that could be easily maintained and still provide some functionality

Evan: creates an implicit group of members of the server/instance, which might be localized.

Darius: by having that boundary of the instance, there was already common agreement about the same terms of service and conduct policies. there could be legal jurisdiction differences, etc.


Emelia: re: the trust and safety aspects, how are we communicating through the group who moderates thr group, what moderation teams are responsible for it, do servers moderate? And what about permissions of groups w/r/t privacy? Are member lists able to be private? Are you able to choose whether you want your memebrship to be shown in the membership list? Can you have groups that are invite only?

Evan: There might be specific rules for specific groups. There might be times you'd want to have other moderation requiement like domains that can't participate. THe face that these systems aren't e2ee means it's easier to enforce such rules. And then a third set of moderators could be recipients on the actor side. Person A in a group may be on a server with different policies from Person B's server and person B could post something that person A's moderators would take down. Pemission s management we would like to be able to say show/hide my group membership, showing or not showing your admin status, etc. Invite only groups ... having a mechanism for approval is one part. We have a sketch for how invitation could work, and we do have a user story for invite only groups.

Emelia: it would be good to have metadata on a group for its invite-only status and whether its membership is viewable. You mentioned moderating by domain, and in AP you don't have the concept of domains only actors with origins. Even though it's implemented in Mastodon, it's not something necessarily AP compliant since AP only has actors. As for moderation for the group actors, the AP T&S has the moderatedBy property that they're working on.

Nick: I wanted to continue that moderation question. There's an opportunity to be thinking of it as a basic requirement rather than a nice to have requirement. Consideration of harrassment and abuse is important. Early types of groups have benen especially susceptible to spam and harassment - don't start with something abusable and try to get it acceptable. Start with something NOT well suited to abuse. I see some of that in the user stories but I would like us to be more deliberate about some basic requirements. I get that it's impossible to foresee all scenarios but it would be good to say "we are going to start with not extremely susceptible to harrassment" as a baselement requirement.

Evan: Sounds like we are talking about moderating posts either pre- or -post distribution. Nick tried to post to a group and it's reviewed first and prevented, or Nick posted something and there were reports and then it was removed. We want to support both of those cases, plus reviews that happen on join, or an invite only group, etc. I'm concerned about saying any one implementation is the right one from a trust and safety standpoint. 

Nick: I agree, I don't think we have the knowledge to say this is the one right way. We can describe bad ways. Open join and open add anyone is bad and we shouldn't support it.  And I understand why we might have gotten into a situation but we should say these aren't safe.

Evan: maybe open join is okay, open post is okay, open join and post is not okay.
