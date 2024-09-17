# July SocialCG Meeting 2024-07-05

Archived to: https://www.w3.org/wiki/SocialCG/2024-07-05

https://meet.jit.si/social-web-cg

## Present

* Dmitri Zagidulin
* Lisa Dusseault
* [Johannes Ernst](https://j12t.org/) [@j12t@social.coop](https://social.coop/@J12t)
* Tantek Çelik (https://tantek.com/) @tantek.com@tantek.com
* [a](https://trwnh.com)

## Agenda

1. IP Protection Note Reminder:
  a. Anyone can participate in these calls. However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
  b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA): https://www.w3.org/community/about/agreements/cla/
2. Introductions & Re-Introductions
3. Community Announcements
4. Task Force Updates
   * Webfinger TF
   * HTTP Signatures TF
   * Portability TF
   * Forums and Threaded Discussions TF
   * AP Testing TF
5. Issue Processing

## Announcements

TPAC 2024 in Anaheim -- we should encourage implementers to attend! https://www.w3.org/events/tpac/2024/

## Minutes

Lisa: I probably won't be able to make it to TPAC this year

Tantek: I will be at TPAC in person. Highly encourage invited experts to apply for waiver. The call for breakout sessions at TPAC is open! So even if you're not present in person, you can propose a breakout session and attend remotely. https://github.com/w3c/tpac2024-breakouts

Also, there's the XOXO festival in Portland OR in August, for indie creatives etc, highly culturally aligned. Festival is already sold out, but some of us are organizing an Indie Web Camp the day after the festival.
https://events.indieweb.org/2024/08/indiewebcamp-portland-2024-8bucXDlLqR0k

### TF Updates

Dmitri: CG has published reports for HTTP Sig and Webfinger (https://github.com/w3c/cg-reports/pull/41)

Lisa: Portability TF updates; document is coming along, thank you to bumblefudge, Johannes, others.
Need guidance on how to register the `previously` field.
Will put out a call for implementers to take a look at the LOLA report.

Re next Portability TF call -- scheduling..

Johannes: FediTest -- produced another report of the WebFinger tests we've done so far, with 94 AP implementations. Results are consistent with the WF report, but somebody should go over this. We found a few instances of attributes that are not properly registered. Needs more eyes to make sure it's consistent with the TF report ([Link](https://feditest.org/contrib/results/2024-06-16/)).

Dmitri: Couple of FEPs related to Portability:

* https://codeberg.org/fediverse/fep/src/branch/main/fep/e3e9/fep-e3e9.md
* https://codeberg.org/fediverse/fep/pulls/334/files (in progress)

bumblefudge: Minor comment on the Testing TaskForce, we hit a minor milestone this past week, Bengo is working on documenting self-serve testing using the test runner.
https://activitypub-testing-website.socialweb.coop/fep/521a/

Johannes: Steve collected these 94 implementations (for WebFinger and others), and we've been debating on -- how do we communicate to the implementers that these tests exist? How do we retest an so on? Tests are only useful if they lead to actions. Not sure how to do this aside from very manual work of tracking down the implementers and filing issues.

Does anyone have ideas on how to inform people and create momentum, for fixes and related issues?

One of the things we were thinking of doing was creating a spreadsheet, listing implementations and for each, listing the bug tracker where an issue was opened, and invite participation.

Johannes: Also, what are some steps we can take to update the top level activitypub.rocks domain?

a: It's hosted off of https://gitlab.com/dustyweb/activitypub.rocks

## Main Agenda

Tantek:
If we're on to other business, I'd like to suggest at least a brief discussion about the recent Fediverse Mastodon introduced an OpenGraph extension called Fediverse:Creator, and blogged about it.
It seems to serve the same role as rel=author, and I wanted to bring it to this group's attention. We should document how to use `rel=author` for the same use case, and talk to Mastodon folks about supporting both methods.
https://indieweb.social/@caesar/112719249332136433

https://github.com/mastodon/mastodon/pull/30398#issuecomment-2204184781

Dmitri: Excellent suggestion, lets do that. Would it make sense to create a special topic call for this topic?

Tantek: Yes, or at least add it as an agenda item for a future CG call.
Do we need better documentation on `rel=author`? How do we prevent this failure condition from happening again?

a: i am guessing that there is an implicit webfinger requirement in fediverse:creator that `rel=author` doesn't have?
fediverse:creator currently requires username@domain

bumblefudge: https://github.com/franck-paul/socialMeta/commit/a40765513a2fb72482e8812a4000a25300157583

Tantek: a, rel=author can be used for @-@ addresses too and certainly those can be parsed to discover them (vs "other" rel=author links) so it should still be usable

Johannes: Agree with Tantek.

a: on the PR renchap mentions specifically that "fediverse:" was chosen as a prefix is basically for more palatable marketing

bumblefudge: i like this proposal a lot (from one of the FEP editors)
https://github.com/mastodon/mastodon/pull/30398#issuecomment-2205071362

Johannes: On separate subject, you all might be aware of the podcast called dot.social that Flipboard's Mike McCue does on the fediverse and related. His most recent one was an interview with the Ghost implementer (John Nolan), that featured some requirements and ideas for future ActivityPub roadmap items. This is great, because it looks to the future, beyond just documenting current state of the art. Worth listening to. ([link](https://flipboard.video/w/sQCNmXx332xi3Y3dVVjd37))

-- no other items for the moment, see everyone on next call!
