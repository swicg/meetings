# April SocialCG Meeting 2025-04-04

* SocialCG on Fedi: https://w3c.social/@socialcg
* [SocialCG Calendar](https://www.w3.org/groups/cg/socialcg/calendar/)

Archived: __

## Present

* Dmitri Zagidulin
* [Ted Thibodeau](https://github.com/TallTed/) (he/him) https://mastodon.social/@TallTed (OpenLinkSw.com)
* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
* [Nigini Oliveira](https://nigini.me)
* [Lisa Dusseault](https://mastodon.geekeryorg/@lisarue)
* Darius Kazemi
* Bob Wyman
* a <trwnh.com>
* Tantek Çelik [@tantek.com](https://tantek.com/) (for first half of meeting)
* Emelia S
* Angelo Gladding, @ragt.ag
* Bumblefudge
* James Smith

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. ~~Introductions & Re-Introductions~~
3. Community Announcements (minimal)
4. Task Force Updates (may be moved to "if time")
5. **Main topic:** Working Group Charter
    * Evan's proposal to break the logjam: https://github.com/swicg/potential-charters/issues/83
6. Discussion: Including security considerations in the errata for ActivityPub and Activity Streams 2.0 Core and Vocabulary https://github.com/w3c/activitypub/issues/432

## Minutes

* Skipping introductions in the interest of time
* Announcements
    * IIW is next week, maybe we do a Fediverse session
    * Nivenly now has a fediverse security fund where we will pay for the responsible disclosure of security vulnerabilities in Fediverse software, specifically in high vulnerability cases. (CVE > 7.0) https://nivenly.org/blog/2025/04/01/nivenly-fediverse-security-fund/
    * Fediverse Schema Observatory is now generally available: https://observatory.cyber.harvard.edu/
    * Confirmed the dates and venue for IndieWebCamp Dusseldorf: https://events.indieweb.org/2025/05/indiewebcamp-d%C3%BCsseldorf-lbBv9MGOChq2
* Working Group Charter
    * Dmitri: So why are we here? We all sense that there is a fundamental, existential threat from unchecked traditional social media. All of us suspect that if there is even a chance that having standardized open source, open standards social web technology available then that chance is worth pursuing. In any community, there are lots of factions and disagreements but we have unified purpose. Task one is to come to consensus in this call, and then get through the two week "call for objections" period on the mailing list, forums, and so on. We need consensus on a working group charter. There is critical interest from big players, including Tumblr (which has a lot of new interest from Gen Z), in updated, standardized, social web specs. We need to put together a WG charter that we can all live with.
    * Dmitri: There are essentiallly two proposals in front of us. Do we charter an ActivityPub and ActivityStreams specific working group, with a provision that other documents migrate through the incubation steps framework? Option two is a broader social web working group with AP documents but also in scope errata and updates to other documents that the previous Social Web WG put out, which include the specs we broadly term "IndieWeb". Are there any other major roadblocks? Have people had insights and realizations since our last call related to the WG charter?
    * Evan: I do want to say, and I think PLH brought it up two meetings ago, the W3C expects SWICG to define this charter. We are going to define how these documents are normatively defined and improved over time. He also said that if we do not find our way to defining this charter, they will seek input from the rest of W3C membership and they may not design a structure that is as favorable to SWICG. It's not a threat so much as a wakeup call that if we don't step up and show leadership in this area, then someone else will.
    * Dmitri: let's take a look at [Evan's proposal](https://github.com/swicg/potential-charters/issues/83). 
    * Evan: At our last CG meeting, there were two strands of concern about the scope for the WG. One was that we didn't want to abandon or orphan any of the important recommendations that came out of the original WG, e.g., Micropub, Web Sub, etc. The other concern, which Christine Lemmer-Webber put so well, was that it was hard for her and others to maintain such a high number of documents. I think we put out 7 documents at the end of the WG, and Christine said that was too much for a WG to do and we shouldn't put that much work on a WG in the future. I think we can keep the scope open for all the documents that the Social Web WG did, having them in scope, but not having particular requirements of deadlines and work-pace for all of them. We could have a queue for maintenance, maintaining a relatively bearable workload for the people in the WG; at the same time, making sure we don't cut out important documents that get left on the floor, unmaintained.
    * Lisa: We're at the point of agreeing, compromising, consensus, but not necessarily unanimity. Coming to that kind of consensus, this is a key point in time. It indicates what you can live with as well as what you prefer. I continue to prefer narrower scope, but can live with the other proposal, and support consensus even if it's not my favorite outcome. 
    * Darius: +100 that, I share Lisa's preferences and her overriding preference for consensus.
    * Emelia: I agree as well, but I think that if we are to take on IndieWeb documents, we do need a Chair who has experience with IndieWeb documents.
    * Dmitri: Obviously, the more Chair volunteers we can vote on, the better. If we get Chairs familiar with IndieWeb docs, that's better. The critical part for any document is its editor(s). In the charter will be stated something like "these are the deliverables, provided we can get editors to work on them".
    * Emelia: You mentioned that the need for editors was probably greater than the need for Chairs. I don't recall in the documents that the editors need experience with the material covered by the documents. It's great if we have Errata that can't be thrown at just anyone, just because they have experience elsewhere. I am not saying that every editor needs experience; a subject matter expert plus a great technical writer would be a fine balance.
    * Evan: Juan has proposed and merged, and then unmerged and reopened, a change. I'd like to ask Juan to address that change. https://github.com/swicg/potential-charters/pull/87/files
    * Juan: It was merged and unmerged because I was nervous and messed up a merge conflict. In terms of the thoughts behind this, I didn't want to overspecify and constrain, because the underlying problem we are trying to solve is having the group be as productive as possible within constraints. I wrote language saying "It's okay for a Chair to say they are already managing too much work, let's get another Chair into the group." To avoid constraining this into a specific number of work items at any given time, I was trying to wordsmith Chairs sticking up for themselves and making sure there isn't too much work for any one Chair to be responsible for. 
    * Manton: I haven't been very involved, sorry about that. Wanted to jump in today. I am in favor of having as much IndieWeb work in scope as possible. I've implemented all of the IndieWeb specs and am happy to help anyone who doesn't have experience in these.
    * Dmitri: Are you volunteering as an Editor?
    * Manton: If I can be helpful, I'm happy to do whatever is needed. I like keeping everything in scope because there is some overlap between things. Even if we can't work on everything at once, if we are working on AP C2S, it's important to remember, "Oh, MicroPub does something like that," so we don't reinvent the wheel when we don't need to.
    * Tantek: Thanks Manton, and appreciate the work and thoughtfulness Evan and Juan put into thinking through how we can be productive and have a good experience. If we can't find volunteers for MicroPub, WebMention, or WebSub specs, I am happy to step in as an Editor. I'd prefer others, but consider me a backstop. I'd also like to step back from consideration as a co-Chair in this work. I'd prefer to work on the technical side as my focus. I have a lot of experience being Chair, I am happy to provide guidance to any Chairs if they need that. I also like the transparent communication that is reflected in Evan's proposal.
    * Dmitri: I would love to run a proposal for a Social Web WG charter, with the ActivityPub Errata as definite deliverables, with the IndieWeb specs added to the potential deliverables with the implicit "if Editors are found" (but it sounds like we have a backstop in Tantek).
    * Bob: It is Social Web stuff, it is defined in the W3C description of Social Web. I'm concerned that classifying these things with the name "IndieWeb", which is not a W3C term, which I understand is loved by many, does not do a service to the community as a whole. Re: a comment that IndieWeb is the name they chose, there are things like PubSubHubbub that were developed independent of IndieWeb but created the work that WebSub and so on were derived from.
    * Dmitri: There is no need to use IndieWeb in specific references. We can say something like "non-ActivityPub".
    * Emelia: If you look at https://spec.indieweb.org/ you can see that IndieWeb is the name they chose.
    * Evan: Can we table this discussion around naming? Let's just call them Social Web. Can we have a proposal for a WG?
    * PROPOSAL: SWICG makes a recommendation for a Social Web Working Group 1.1 charter, with the following characteristics:
        * AP 1.1 / AS 2.1 / AS Vocab 1.1 errata front and center in the deliverables section
        * List the non-AP/AS specs in the Potential Deliverables section. WebSub, Micropub, Linked Data Notifications, Webmention 
        * Mention the Incubation staging process, and that if other documents go through the requisite incubation stages, and if there's time in the WG charter, they would be considered by the WG as well.
    * RESOLVED: SWICG makes a recommendation for a Social Web Working Group 1.1 charter, with the following characteristics:
        * AP 1.1 / AS 2.1 / AS Vocab 1.1 errata front and center in the deliverables section
        * List the non-AP/AS specs in the Potential Deliverables section. Specifically: WebSub, Micropub, Linked Data Notifications, Webmention 
        * Mention the Incubation staging process, and that if other documents go through the requisite incubation stages, and if there's time in the WG charter, they would be considered by the WG as well. 
    * VOTES
        * Bob Wyman: +1
        * Dmitri Z: +1
        * Darius K: +1
        * Nigini: +1
        * Tantek (in absentia): +1
        * Evan P.: +1
        * TallTed: +1
        * Lisa D.: +1
        * Manton Reece: +1
        * Emelia: +1
        * Bumblefudge: +1
        * Angelo G: +1
        * a: +0.5
            * from chat: "previous outputs are considered inputs, but we don't commit to necessarily publishing new versions of everything" seems fine, and the "potential deliverables" section seems to allow for that, so +0/+0.5 -- i'm somewhat unsure about whether the language applies to recs only or does it include notes. i would think that it should include notes
        
        
    * Angelo: Is IndieAuth included?
    * Dmitri: It was not part of the original WG.
    * Emelia: I've worked with IndieAuth. My understanding is it was originally a Note and not part of recommendation status in the WG. My understanding further is that because there is a lot of Auth/Identity work the W3C is doing, they would be unlikely to make a recommendation out of IndieAuth at the current time. FedCM is an entire WG, it's a Note and not a Recommendation, I have the gut feeling W3C is not going to make it a recommendation and would want it rolled into other specifications like DIDs or FedCM.
    * Emelia: If IndieAuth is currently a dependency for WebSub or WebMention, you probably want to look at how to support alternatives like FedCM or DIDs.
    * Evan: Question for Dmitri, it looks like we have consensus. Do we need to have an additional discussion on a final document or can we finish the document and pass it on to W3C staff.
    * Dmitri (scribe: didn't get this, was pasting in RESOLVED stuff) We'll mark the resolution now, and it will enter the 2 week Call For Consensus period, then we pass on the recommended charter to W3C.
* Moving on to next topic, Errata
    * Evan: Since the Social Web WG was wound down, the CG has taken on responsibility around maintaining documents. My approach has been to focus on errors of omission or commission in the docs themselve. We have released errata on spelling errors, grammatical errors, and so on. One suggestion we got was to include a security consideration about uploading JSON files to an ActivityPub server. There are ways to upload a file to an AP server and spoof that it was created by a user. Most AP implementations have corrected that but it's not in the documentation. Is the fact that this is missing something in the scope of Errata? Lisa pointed out that W3C's policy on Errata does allow non-normative changes to a document especially for important security considerations. I'd like to put it in front of the community group that we consider adding non-normative changes as Errata?
    * Emelia: The security consideration definitely needs to be added. It probably ties in to work that needs to be done on media uploads. If you upload media via origin/domain model trust and safety, even if AP is Actor-centric, most software does use the domain centric model.
    * a: I support adding security considerations to Errata. It would probably depend on specific wording. How do we handle the problem of trust? Right now we don't have a clear path toward Actor based trust versus origin based trust. The more general concern around security is trust considerations, but maybe we just put that in scope and have discussions on a case by case basis.
    * Dmitri: yes I think these should keep in scope.
    * Darius: Does this require a proposal?
    * Dmitri: I think probably not but... Evan go ahead
    * PROPOSED: The SocialCG should consider errata that are class 3 (no new features) for published recommendations, especially if they offer security considerations for implementers."
    * Emelia: would deprecating be in scope? Not removing, just noting there are better ways?
    * Dmitri: if it's a security consideration, sounds like.
    * Evan: deprecation is different from Errata and I think something WG should concentrate on.
    * RESOLVED: The SocialCG should consider errata that are class 3 (no new features) for published recommendations, especially if they offer security considerations for implementers." 
        * Votes:
            * Dmitri +1
            * a +1
            * Darius +1
            * Emelia +1
            * Juan +1
            * Evan +1
            * TallTed +1
            * Bob +1 only for security related issues
            * nigini +1
            * Lisa +1
            * Manton +1

    * Thank you everyone. End call.

(Tantek aside: permission granted to copy any of my comments from Jitsi chat into the minutes if they are helpful. I didn't copy the chat before signing-off. If someone does, feel free to email to me. Thanks, -t)

