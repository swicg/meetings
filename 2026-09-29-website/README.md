# Website Task Force, 2026-09-29

## Present

* Johannes Ernst (http://j12t.org/)
* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
* [Ted Thibodeau Jr](https://www.linkedin.com/in/TallTed/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

Preliminaries:
* Administrative issues, CoC, IP reminder
* Intros if needed

## Topics:
    
* Port to Hugo: review and approve: #99 
* Stick with the logo currently on the site or not? #98 
* Is this graphic design direction acceptable? #48
* We need a one-sentence (or shorter) description of what ActivityPub is / what value it provides #97. A key question:
  * Is it a protocol to enable decentralized social media systems? or
  * is it a protocol that enables a user on one website to follow the activities of another user on another website? (which, among other things, allows the creation of decentralized social media systems)  
* Should we merge https://fedidevs.org/ content?
* Issue backlog

## Notes

### Moving from Haunt to Hugo

- Implemented Hugo
- Dropped some ancient pages, such as implementation matrix
- Amazing, zero changes!
- EP: we don't need the implementation matrix any more
- JE: any objections?
- EP: I think this is great
- EP: Are there tools for better UI for Hugo?
- JE: There's a tonne out there, issue #48 gives us some good ideas
- Action item: JE to follow up with the work

### ActivityPub logo

- JE: do we want to keep it and promote it
- JE: time to replace it?
- EP: I use this logo on stickers
- EP: I would be open to investigating other logos
- JE: what's the audience?
- EP: developers
- JE: comparison with RSS, Atom icon feeds
- JE: we should write it up somewhere
- EP: a great idea to use it as an indicator that software is ActivityPub-enabled

### Web design

- Issue #48
- EP: comparison: [AgenticCommerce.dev](https://www.agenticcommerce.dev)
- TT: also, we have the world of dark mode/light mode which people tend to like a lot
- TT: contrast values between text and background, for instance, matter for accessibility
- JE: let's do white background first, then add dark mode 
- JE: will come up with a design, for review

### Fedidevs.org

- JE: [Fedidevs.org](https://fedidevs.org/) came out of Fediforum, thanks to Gabe
- JE: [Fedidevs.org](https://fedidevs.org/) has some content worth bringing over
- JE: next steps
- identify fedidevs.org content to bring over to activitypub.rocks
- ask Andy Piper to redirect the domain

### What is the one sentence?

- JE: what is the one sentence for ActivityPub?
- EP: good candidate for the hero section
- JE: "a protocol that enables one form of decentralised media"
- JE: or maybe more fundamental structure: a user on one website can follow activities of another user on another web site
- JE: is it an enabler, or just social networking?
- EP: "federation", "coalition", "network of networks" (what is the larger organisation that you connect to)
- EP: connecting people, no matter (something?) where they have accounts
- TT: can't wait to wordsmith...  ActivityPub: 
  - provides a client-to-server API for creating, updating, and deleting content.
  - provides a federated server-to-server API for delivering notifications and subscribing to content.
  - is a decentralized social networking protocol based on the ActivityStreams 2.0 data format.
  - is an official W3C recommended standard published by the W3C Social Web Working Group. 
- JE: can we make this decision? Who would decide?
- JE: needs to comprehensible for people who are newcomers
- TT: that requires that it be one thing
- JE: mention of AS2 is too complicated
- JE: marketing question? Should we bring in experts
- TT: Who/what/when/where/why/how - first question is why?
- TT: What solves the why?
- TT: How is it solved?
- EP: not neutral
- TT: created to solve some problem; why was ActivityPub needed?
- JE: Because there are walled gardens
- EP: can we track metrics, like bounce rate?
- JE: does this idea get used externally, like in the press. Deliver the message
- EP: Best message is the one that resonates. We could test somewhat either with metrics or other mechanisms
- EP: Let's come up with candidate text, but hold onto it lightly, and maybe experiment with some option
- EP: We could test with a user testing service, usertesting.com
- JE: Is this a text we can use in speaking to people interpersonally?
- TT: Why was this thing needed?
- TT: Call to action -- click here to use this software | develop | see code | something else
- TT: are they looking for blogging software, how to contribute, etc.
- JE: who is this site for? Developers care about protocols, users do not
- JE: why creates vs. why is it needed today or tomorrow
- JE: why today?
- JE: what problem do we solve for the developer?
  - Connect to Mastodon?
  - Content sources
  - Audiences
- EP: a great opportunity to open up for more participation
- Plan is to come up with candidates and put them in the comments on the github issue
- Awesome chance to put this
