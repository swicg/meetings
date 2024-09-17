# SocialCG Special Topic Call: AP Errata - Fri Nov 17, 2023

## Present

* Evan P
* Dmitri Z
* Nightpool
* A
* Bob Wyman

## Agenda

1. IP Protection Note Reminder:
   a. Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
   b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/

2. ActivityPub Errata issues

3. ActivityStreams2 Errata issues

## Notes

### AP [Issue #297](https://github.com/w3c/activitypub/issues/297)

Issue has a PR. "Federated servers MUST perform delivery on all Activities posted to the outbox..."

Q: Should Blocks override the MUST above (that things must be delivered)?

PROPOSAL:
> add Erratum for the ActivityPub spec saying, "
  Section 6.11 should read, Federated servers SHOULD perform delivery on all
  Activities posted to the outbox according to outbox delivery. Servers MAY filter
  activities for privacy, abuse mitigation, or other reasons."

Nightpool: There's another section (7.1.1) with similar language, we should
probably have it match.

PROPOSAL (Amended): add Erratum for the ActivityPub spec saying,
> "Section 6.11 should read, Federated servers SHOULD perform delivery on all Activities posted to the outbox according to outbox delivery. Servers MAY filter activities for privacy, abuse mitigation, or other reasons."
>
> Section 7.1.1 should read: "When objects are received in the outbox (for servers which support both Client to Server interactions and Server to Server Interactions), the server SHOULD target and deliver to:

> The to, bto, cc, bcc or audience fields if their values are individuals or Collections owned by the actor. Servers MAY filter activities for privacy, abuse mitigation, or other reasons."

Bob Wyman: Slightly hesitant, in the sense of, I have no problem giving users control, but slightly more hesitant wrt to Admins. Similarly, there may be gray areas in the operation of relays.

Nightpool: This is very similar logic to dealing with spam. Any sort of relay will likely classify and filter based on spam etc.

Bob W: Understood; I don't have an alternate proposal.

RESOLVED (4x +1s, no -1s)

### AP [Issue #376](https://github.com/w3c/activitypub/issues/376)

Relaxing the requirements for OrderedCollection to always be reverse-chronological.

PROPOSAL:
> Section 5 says, _in part An OrderedCollection MUST be presented consistently in reverse chronological order._ This requirement only applies to the collections defined in Section 5, namely: inbox, outbox, followers, following, liked, likes, shares. Collections defined in other vocabularies, including extensions, are not subject to this requirement and can be unordered or ordered by other criteria.

Nightpool: Should we discuss how we should update the living document spec / editors draft, to reflect these errata?
This is such a small change, to the spec.

Dmitri: Would it make sense to add the words "by default"? (unless otherwise overriden by user preference)

Nightpool: That opens the door to such a wider discussion, though - how to express user preference, etc. Let's keep it focused.

A: What if we phrase it as "the order presented" (chronology might not apply at all)

Evan: that's better

PROPOSAL:
> Add an erratum for the ActivityPub spec saying, "Section 5 should read, 'These OrderedCollections MUST be presented consistently in reverse chronological order.'"

Bob W: Do we have a general mechanism for specifying the order?

Evan: We have a FEP for it.

Bob W: We should collect the discussion/considerations there?

Evan: Definitely.

Nightpool: Yeah, it's a complicated topic, gets into what parts of the CtoS spec are implemented, how complete, etc.
In some senses, it might be clearer if we had a way to specify ordering, but I'm not certain it would be helpful. I can't think of a single mainstream social media app that allows me to sort these collections in a non-implementation-defined order.

Bob W: Twitter does give you a choice, it allows you to choose between reverse chrono, or the algorithmic sorting.

A: "Collections defined in other vocabularies, including extensions, are not subject to this requirement and can be unordered or ordered by other criteria"?

Bob W: Other consideration is, the reason the mainstream apps don't do it, is lock-in / profit etc.

Evan: incorporating the suggestion...

PROPOSAL:
> Add an erratum for the ActivityPub spec saying, "Section 5 should read, 'These OrderedCollection objects MUST be presented consistently in reverse chronological order. Collections defined in other vocabularies, including extensions, are not subject to this requirement and can be unordered or ordered by other criteria.'"

Nightpool: Can we leave off that sentence, and add an infobox node instead? "This requirement applies only to the 6 collections mentioned in this section".

Dmitri Z: I'm hesitant, due to the "presented" word, like - we MUST present it this way to the user.

Evan: Would "sorted" or "ordered" be better than presented?

Dmitri Z, others: yes

PROPOSAL:
> Add an erratum for the ActivityPub spec saying, "Section 5 should read, 'These OrderedCollection objects MUST be ordered consistently in reverse chronological order. Collections defined in other vocabularies, including extensions, are not subject to this requirement and can be unordered or ordered by other criteria.'"

RESOLVED (4x +1s, no -1s)

### AP [Issue #379](https://github.com/w3c/activitypub/issues/379)

Partially anonymize question and like responses.

Evan: Let's defer discussion on this.

### AP [Issue #395](https://github.com/w3c/activitypub/issues/395)

preferredUsername and natural language support - the 'preferredUsername' does not have a JSON-LD translation/multi-language support.

Evan: This is broadly consistent with all implementations, a username is a unique string, not for translations.
The current problem is, AP spec says to use preferredUsernameMap for internationalization.
We discussed this previously during Issue Triage, and agreed that it doesn't make sense to internationalize it, and have proposed erratum text.

PROPOSAL:
> Add an erratum to the ActivityPub spec saying, 'The note at the end of Section 4.1 should read, Properties containing natural language values, such as name or summary, make use of natural language support defined in ActivityStreams." There is no natural language value for preferredUsername defined in Activity Streams 2.0.'

Nightpool: I'd like to discuss the idea brought up here, that even if we decide to keep preferredUsername as a singualr value, might there be benefit to indicate the language it's in?

Dmitri Z: I don't think any other spec treats identifiers as in a particular language; they're opaque.

Nightpool: Maybe that's the issue, it's not referred to as an identifier.

Evan P: Can we say at least, at this point, we DON'T have a preferredUsernameMap.

A: the second sentence feels unnecessary imo -- it's not really natural language is it? i mean, there are other deeper issues with preferredUsername that we could get into (such as having no specified format/regex/grammar)

I would just call out name/summary/content and nameMap/summaryMap/contentMap

Evan: I agree with A, let's leave out the second sentence.

PROPOSAL:
> Add an erratum to the ActivityPub spec saying, 'The note at the end of Section 4.1 should read, Properties containing natural language values, such as name or summary, make use of natural language support defined in ActivityStreams."'

Nightpool: One thing I'd like to bring up - just looking at the Git Blame, the note was added based on feedback, in the WG. Maybe it helps to be able to display text direction for the preferredUsername.
I'd prefer it if we clarified in the spec that we have one identifier, and one name.

Evan P: Could we adopt this proposal, and open an issue on AS2 saying - this was proposed/discussed, maybe we need another name.

Bob W: Do we really want to keep the issue going though. Back in the 80s, when we were just starting to work with i18n, and we tried a number of i18n proposals for names specifically, and it was hell. We solved i18n issues for other things, but not for names.

Nightpool: Yeah, I want to be clear - I think the goal of the sentence was NOT that there'd be multiple usernames based on language. I think it was more "this is the language / direction" for the name, for text-to-speech etc.

Dmitri Z: Could it be that the document-level or client-level language/direction preference would be sufficient to handle the name?

Nightpool: Yeah, maybe document level preference would be sufficient.

Evan P: Wait, let's check if AS2 covers 'preferredUsername'

Nightpool: I would hate to impose an undue burden on JSON consumers, with regards to this name, to have to deal with language maps etc.

A: there's a sort of punting down the road of the other issues re: preferredUsername, the intention of the spec seems to diverge pretty heavily from the actual usage with webfinger/etc

Evan P: yeah, current typical usage combines it with domain, uses it for Webfinger. So, it's not just a display name, it's actual identifiers.

Nightpool: Yeah, regardless of path, preferredUsername should remain a functional property. We should fix the text on AP, and possibly open a discussion.

Evan P: Question is, does the note express intent for preferredUsername to have a language map, initially?

Nightpool: I think it does.

Bob W: yeah, I don't think usernames should be internationalized. Becomes a vector for fraud, etc.

Nightpool: Yes, I don't ever want us to have two preferredUsernames based on language. I'm only concerned with indicating the language direction.

RESOLVED (4x +1s, no -1s)

### Living Spec / Editors Draft

Evan:
The main doc is at https://w3.org/TR/activitypub

And it has two links. One is to the errata (which we're discussing). And the second link is to the **Latest editor's draft**, hosted on Github.

We have not made a latest Editors Draft in a while. I think it's necessary for us to keep updating the Errata, since that's traditional/formal.
But also maintain an Editors Draft, especially one that's mostly tracking Errata and editorial changes, is helpful for readers.

Nightpool: Yes, and will save us time down the road.

Evan: So we have some consensus in the group, which has been discussed previously multiple times, to apply the errata to the Editors Draft.

Dmitri Z: Could we add a sentence, to the main spec, saying something like "these errata have been incorporated to the latest Editors Draft".

Evan: That'd be great; we'd need to check with W3C and update the spec. (I don't want to over-promise, that errata will /always/ be in the latest draft, but that sentence would be useful.)

PROPOSAL:
> Incorporate the existing errata for the ActivityPub spec into an updated Editor's Draft.

Bob W: Should we change the list of Editors?

Evan: I don't think we need to yet.

RESOLVED (3x +1s, no -1s)

Nightpool: What's our procedure for working with the list?

Evan, Dmitri: Lets apply the errata, post to the list for review and objections. If there are any objections, we can reverse the errata.
