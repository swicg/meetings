# May SocialCG Meeting 2025-05-02

SocialWG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Zagidulin
* a <trwnh.com>
* [nigini](https://nigini.me)
* [TallTed // Ted Thibodeau Jr](https://github.com/TallTed) (he/him) [mastodon:@TallTed](https://mastodon.social/@TallTed) (OpenLinkSw.com)
* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
* Theia
* PLH 
* Tantek Çelik [@tantek.com@tantek.com](https://tantek.com/)
* [Michal](https://id.mrkvon.org) (guest)

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
    * https://socialwebfoundation.org/2025/04/29/places-pub/
5. Task Force Updates
6. Recap of recent CG resolutions
   * CG charter adopted
   * CG Chair Elections coming soon
   * WG Charter recommendation passed on to W3C management
7. Issue and PR processing

## Announcements

IndieWebCamp Dusseldorf this coming weekend!! https://indieweb.org/2025/D%C3%BCsseldorf - with remote participation


## Introductions and Reintroductions

(none)

## Task Force Updates

* Forum and Threaded Discussions TF: No updates (call postponed this past month)
* Geosocial TF:
    * Public vocabulary is now available for devs to experiment with https://socialwebfoundation.org/2025/04/29/places-pub/
    * geosocial activities (check ins, check outs, images, txt, etc)
* a: We had a cross-pollinate meeting with the JSON-LD CG (who are also looking to charter a WG), about the SocialWeb's experience implementing JSON-LD
    * `a` and Daenney from GoToSocial attended, gave feedback
    * notes: https://www.w3.org/2025/04/23-json-ld-minutes.html

## Recap of recent CG resolutions

* We have accomplished a great number of things that were been on the works for months:
* The CG charter 
    * We came to a consensus on the scope
* [Evan] Have we solved all the objections raised before?
* [Dmitri+Darius] Yes, we did!
* [Evan] Great! we HAVE a Charter!
* [Dmitri] We will now work with Phillip and others at the W3C for the next steps. We now need volunteers for chairs, Darius here is one, talked to others who don't have bandwith... Evan volunteered but we believe his editor skills are valuable (although need to be appointed by the group)
* [Philip] ... The next thing is I will review the charter which takes a month or month and a half. My understanding is the scope is ActivityPub stuff and the "IndieWeb" stuff. My understanding is that it would be great to have two chairs based on the scope. In summary, we will need around two months to get this fully approved if no oppositions.

Progress on charter to be tracked in issue: https://github.com/w3c/strategy/issues/435
Draft charter will now live at: https://w3c.github.io/charter-drafts/2025/social-wg.html (issue tracking and discussion to continue there)

[Evan] The issue that you shared is named "..." is this considered that this is the same group been re-started?
[P] Yes. In fact that is the reading I have from previous conversaitons.
[E] That is great. I fully agree and it makes sense.
[Tantek] ... Agree it is a good move!

[P] I shared the charter template, and part of the review is to check if the current document proposed is aligned...
[Tantek] I wanted to say thanks to Philippe for putting the template in the W3C charters repo. I would suggest that we should keep our section about Success Criteria (https://w3c.github.io/charter-drafts/2025/social-wg.html#success-criteria). W3C recently changed that section in default charter template to weaken that based on a browser maker proposal. I would like to see that language kept strenghtened as-is to make sure clients and server in our space can interoperate with each other.

[E] Should we ratify / come to consensus on the Staging Process document?
[Dmitri] Good idea, we can do that next in the CG

[Plh] I think we need to make the change (suggested by Tantek) but I will run it through the group before.

[Plh] Looking through it, sounds weaker than the current template. (missing the 'testing plan for each spec document')
[T] Browsers don't need to interoperate directly with each other, rather with the test, but for our social web specs we need to make sure our criteria don't get weakened because our implementations do need to interoperate with each other. The important part that we'd like to keep is the "two interoperable implementations" interopating with each other section.
[Plh]: Ah, no problem in keeping the 'interoperable implementations part'
[T] I can offline point you to the changes. Someone dropped that and I think we need to take this offline. Adding more is fine, I just think it should not be weakened.
[Plh] Agree.

[Plh] Question: do we want to add any other groups to the 'Coordinate With' section?
[Dim] From my perspective, I would love to coordinate with everyone, but as an engineer, I know that promissing less will help with accomplish more.
[Evan] I'd say the coordination with at least JSON-LD would be needed.


[Plh] It is something like, we needed to have checked with those folks before approving charters. (some other related charter was recently approved)
[Tantek] I am not too worried about it... (some liaiason in our space). Any IETF groups that we need to align with? No need to answer now, but we need to keep this in mind.

[Dmitri] Evan, we could do some issues processing. Also, we could talk about the roadmap for this group. What is this monthly meeting going to be? Right now, check-in on task forces. My question to the group, does that seem like a decent way?
[Tantek] I think it is good as there are more technical meetings happening. Praise to Evan's work on issues tracking for ActivityPub triage meetings. I plan to use that model if I get to edit other specs to resolve errata. I would suggest that if we need to we could capture that workmode in the WG charter, but also would be fine with that be a cultural custom and let the chairs help drive that.
[Evan] I'd suggest that, as a group, the CG have powers, like deciding to publish documents. So keep track of when reports are ready to be published. We are responsible for organizing Task forces. ... We have other resposibilies that I hope we can get to after this charting process. One question I have is around erratas and maintenance of ActivityPub documents... Sometimes their are very boring (grammar, etc.). I am wondering if making decisions about erratas is a good task for this meeting?
[Dmitri] Do we want to let Task Forces to handle that? But, question to the group: do we want to keep erratas as an async task?
[Evan] Actually, I am thinking about the fact that erratas are only published after the group discuss, so, maybe this meeting is a good place for it.
[Dmitri] My opinion, I am interested with experimenting with the async method proposed in the charter (call for consensus).
[Darius] Agree. Erratas may not be the best discussion for this sync meeting.
[Evan] That sounds good to exercise the call for consensus.

[Evan] I have another agenda item: The staging process, have we approved it? Is it ready to be approved? I would like to have a timeline to have it finished up!
[Tantek] Maybe I am misremembering, but have we discussed to try it out as is?
[Dmitri]
[Tantek] I'd liked to see us telegraph our intentions of using stages earlier by inclusion in the advance notice WG charter and have any concerns raised earlier.

[Dmitri] Proposal: Vote to ratify the Staging Process document on the June monthly call. (So, begin the review / call-for-consensus process now).
**RESOLVED**: +1 by Evan, Darius, Dmitri, a, Tantek, TallTed


[nigni] DANG! I am really bad at transcribing! ;)
hahaha nigini, no worries, thank you so much for scribing! Much appreciated.

[TallTed] Paraphrasing is to be expected with manual scribing. Scribes are not expected to capture every word.


