# September SocialCG Meeting 2025-09-05

SocialCG on Fedi: https://w3c.social/@socialcg

Archived: __

## Present

* Dmitri Z.
* Ted Thibodeau Jr (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
* Tantek Çelik (he/him) [@tantek.com](https://tantek.com/)
* Ryan Barrett snarfed.org
* Evan Prodromou <acct:evanp@socialwebfoundation.org>
* Nigini Oliveira (he/us) https://nigini.me
* Johannes Ernst ([j12t.org](https://j12t.org))
* Emelia Smith ([@thisismissem](https://support.thisismissem.social))

## Agenda

1. IP Protection Note Reminder:
    - Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    - To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements 
4. Task Force Updates
5. Charter updates if relevant.
6. Main Agenda
   1. (Evan) TPAC...? Are we ready?
   2. (Evan) OAuth2 + AP API discussion
       - is it a rebrand of C2S (Emelia advocates yes)
   3. (Tantek) Proposal to make keeping minutes in repo official.https://github.com/swicg/meetings
   4. (Emelia, Evan) Wider discussion on cross-community conversation, particularly about ActivityPub vs AT Proto arguments at the moment.
   
   
## Minutes


### Announcements

- Johannes: 3 events, FediForum related.
  * Robert Gehl [book tour event](https://events.humanitix.com/fediforum-special-event-robert-w-gehl-introduces-his-new-fediverse-book-move-slowly-and-build-bridges/tickets), next Thurs morning PT
  * FediForum coming up again in 5 weeks (online, 2 days) [registration](https://events.humanitix.com/fediforum-october-2025/tickets)
  * Fediverse track at free software conference FSFConf, organized by FediForum, in Northern Italy in November and events around it ([more info](https://fediforum.org/news/2025-07-09-fediforum-partners-with-sfscon-november-2025-bolzano/))

- Darius: Save the date for Oct 24-25th -- General DWeb gathering in Portland OR, USA, with Fediverse content

- Emelia: Trust and Safety Taskforce calls are now monthly, on the first wednesday of the month, information in: https://lists.w3.org/Archives/Public/public-swicg/2025Sep/0000.html (waiting for SWICG calendar to be updated).

- Tantek: Save the date - Nov 1st & 2nd, IndieWeb Camp Berlin is being planned. https://indieweb.org/2025/Berlin

- Dmitri: Internet Identity Workshop (IIW) is going to be on October 21st-23rd, Mt.View California - Computer History Museum.
https://www.eventbrite.com/e/internet-identity-workshop-iiwxli-41-2025b-tickets-1393125719529

- Evan: Belin Fediverse day, Oct 3rd-5th. https://berlinfedi.day/en/

- Johannes:
  * a bunch of stuff happening in the EU in the SSI / Eurostack
  * German-French "digital sovereignty summit" [LinkedIn post](https://www.linkedin.com/posts/bmds-bund_bmds-wirmachen-digitalministerium-activity-7367211501939486720-L6e7/), in November.
  * DMA discussion on potentially requiring Social Media interop in review next year
  * Utah - Digital Choice Act: Social Media interop legislation, required starting July 2026. [ref](https://le.utah.gov/~2025/bills/static/HB0418.html)
  * People are working on getting more states to join this legislation (like NY, VT, others).

- Emelia: I've seen a lot of discussion recently trying to pit AP against ATProto, and it's something that we as people involved in the standards community should probably address. This sort of thing is not helping anyone. Yeah, there are differences in the protocols, but they're also VERY similar (compare AP C2S with the AT PDS stuff, etc).
  * Some discussion happened off the record
  * Moved to an Agenda item!

- Evan: Julian from NodeBB set up a new forum at https://activitypub.space -- using NodeBB, federates with SocialHub and other Threadiverse servers

### TF Updates

1. Evan on geosocial: great discussions about the AS2 vocabulary and possible implementations of GeoSocial. (Demo: web app, uses AP API and GeoSocial activities, to allow for Foursquare-like check-ins. It scans through one's inboxes to present previous checkins -- which can have a speed problem.)
    Emelia: question about use of AP API vs C2S terminology
    
2. Evan on groups: quiet for the last months, doing async collab about User Stories and documenting an explainer with extended vocab. https://swicg.github.io/groups/

3. Johannes on [activitypub.rocks](https://activitypub.rocks/) hand over. Christine made a nice blog post saying she is handing over to the community in SWIGC. Have already writing access, thanks Evan for setting up the tool chain. Call for contributors... contact Johannes. Should we have a better place for discussing updates to the website instead of GitHub or use our regular mail-list.
    - Dmitri: just use the main swicg mailing list
    - Emelia: recommended using the Issues on Github
    - Johannes: ask about terminology about leaders of a task force... Dmitri clarified it is Task Force lead.
        - Emelia: does this need to be documented (or already is?)
        - Dmitri (via msg): (charter technically calls them "convener", but we can tweak it to lead)
        - TallTed (via msg): re TF lead (not chair), could log an issue at https://github.com/w3c/process/issues/
    - Johannes: the current procedure is to submit PRs that will be integrated after a period of dicussion or silence.
2. Emelia: Trust & Safety task force. Meeting schedule is changing. Working on a few FEPs/docs about our current items.
Also a conversation on ActivityPub.space about adult content / age verification laws etc. We knew this was coming.
3. Dmitri: Lisa not here but there are some Github activity. Please check it!
4. Emelia mentioned the [draft-meunier-http-message-signatures-directory](https://datatracker.ietf.org/doc/draft-meunier-http-message-signatures-directory/) on the ActivityPub and HTTP Signatures repo.

## Main Agenda

### TPAC

- Dmitri: TPAC is coming up.
- Evan: talking about having a presence for the WG and also for the CG... Are we ready for this? (flying there or jumping in a call?)
- Tantek: There is actually a timeslot assigned. https://www.w3.org/events/meetings/5ce4d187-2916-4efc-9c22-5650e1794105/ There are rules about how in advance a Group needs to be charttered before participating. Which reminds me to bring up the need to put the minutes up on Github in a timely fashion for people to monitor the activity.
- Emelia: is this mainly in person or hybrid?
- Tantek: I will not be this year and will experiment with the remote experience.
- Dmitri: although the hybrid experience is not perfect but they are making an effort to make it happen. Encourage those that can to go in person.
- Emelia: Where are we at with Working Group status? Is a working group within the W3C really actually happening for ActivityPub?
- Dmitri: There is some slow downs related to bureaucracy but there is no red flags.
- Emelia: raised concerns about we keeping up with the process, pointing out that AT-Proto is starting work to standardize.
- Evan: I am going to be in Japan and want to stablish a pattern of supporting those who are not there to be full participation on the conversations. (@EVAN, please double-check!!!)
- Tantek: what is the issue on Github to move on with the charter?
- Dmitri: institutional vs expert member. I have mostly be part through MIT (who is not a member.)

### Meeting Minutes

- Tantek: Proposal to keep the minutes in the Github repo https://github.com/swicg/meetings. It helps to further distribute the labor to keep minutes up-to-date and corrections (better than doing that on the Wiki.)
- Dmitri: **PROPOSAL:** The CG resolves to keep its minutes in the swicg/meetings github repo, preferably within a month of the call happening. 
  - Tantek: +1
  - Dmitri: +1
  - Ryan: +0
  - Darius: +1
  - Evan: +1 for both CG meetings and task force meetings
  - Emelia: +1
  - Nigini: +1
  - Emelia: It is possible to convert the MediaWiki entries to the repo in case we need to migrate old material, if necessary
  - Evan: ?let's keep TF minutes in the same repo
  - Emelia: oppose a little to keep the Task Forces in the same repo.
  - Dmitri: that would be a new proposal to move the ones that are already there.
  - Emelia: thought that Taskforces generally used their own repos for meetings minutes, this was corrected as it is not the case for all. Emelia's opinion: should standardize on where, and I believe the Taskforces should manage their own minutes, but with standard formatting and guidance from the CG.

- **RESOLVED**: The CG resolves to keep its minutes in the swicg/meetings github repo, preferably within a month of the call happening.

### ActivityPub API & OAuth

- Evan: Using OAuth with AP API.
- Dmitri: clarifying what painpoints need to be documented?
- Evan: there are different ways devs are using OAUth, I am leaning towards IETF OAuth.
- Emelia: The implementation of OAuth in AT Protocol is pretty similar to what we would likely end up with. We need to spend time to do that and suggestion is to create a taskforce for the ActivityPub AP and within that work on an OAuth profile targeting OAuth 2.1 standards.
- Evan: I agree with the TF and the use of 2.X.
- Emelia: **PROPOSAL:** SWICG to establish an ActivityPub API task force, with items including an OAuth 2.x profile for interacting with the API, more efficient fetching from outbox, media uploads, partial updates, and related.
  - Dmitri: clarification question???
  - Emelia: I'd like to see a document that is: here is what the ActivityPub API looks like and how to make it usable, that may mean applying some amendments pending for the ActivityPub specification
  - Evan: Maybe a TF that doesn't focus on AP that enable technology
  - Emelia and Evan volunteered as co-leads
- **RESOLVED:** SWICG to establish an ActivityPub API task force, with items including an OAuth 2.x profile for interacting with the API, more efficient fetching from outbox, media uploads, partial updates, and related.

### Discussion on ActivityPub vs AT Protocol discussions

- Emelia offered to draft a statement at the end of the meeting after a little discussion.
