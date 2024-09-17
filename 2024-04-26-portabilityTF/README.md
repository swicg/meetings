# Data Portability Task Force

26 Apr 2024

## Present

- Evan Prodromou @evan@cosocial.ca
- Bob Wyman @bobwyman@mastodon.social
- Andy Piper @andypiper@macaw.social
- Johannes Ernst @j12t@social.coop
- Aaron N Gray @fosstodon.org
- Tantek Çelik @tantek.com

## Agenda

- Scope or light charter for portability TF
- Object identifiers persistence
- and:
a) Data synchronization for redundant storage across multiple servers.
b) data transfer, transportation, and backup, and security there of
c) backend cloud storage systems, and W3C SOLID POD's
d) seeing users data as theirs and as a whole
e) the ramifications and possible connections of these on LOLA

- Context setting
  - LD working on specific mechanism (LOLA) for moving an account from one live server to another
  - Pulling content from remote server
  - Web interactions make some specifications unnecessary
  - Proposal lets the destination server change object IDs
    - EP: Can we do better?
  - AG suggested additional scope
    - LD: backup and export are interesting
  - LOLA = Live, on-line account data portability
  - Tying FEPs together
  - Backup/restore better for copy semantics
  -

## Scope or light charter

From Lisa's email

- **Discovery**
  - how to know if a remote server supports account migration, and what OAuth URL to start with to get authorization.
- **Authorization**
  - Security considerations and threat models
  - OAuth proposed as how user authorizes origin server to accept full content access requests from destination server
- **Fetching data** needed for account migration
  - What to include along with all the public content
  - Blocklist endpoints
- **Post-move account state**
  - move notifications
  - replying to requests with redirects
- **Export format**
  - interoperable envelope for shared data model
  - https://indieweb.org/blog_archive_format (most implemented across various protocols/formats)
- **Shared data model**
  - including user’s blocklist (existing FEP)

And more importantly, who is willing to work on pieces of this as author or supervising/guiding discussion?

Lisa: The backup and account move work can use the same schemas/data models

Lisa: Note that the account state functionality is asynchronous and needs to be defined - but does not need to be interoperable. The user can go to a web page to set up account move notifications and redirects.  Both notifications and redirects are optional and can be done after a move or account setup.

Johannes: What if I set up an account and use it for a year, then try to transfer data into it? A merge can be different than a copy to empty

Aaron: agrees that the merge use case is interesting. people trying new servers might

Evan: One issue is copying followers.  When you copy those relationships, it's not entirely YOUR resource, it's kind of a shared resource.

Lisa: With these notes and issues, is it a good list of work? Who's willing to work on it?  

Evan: I am.  I want to confirm that the OAuth authorization approach can coexist with existing OAuth authentication endpoints?

Lisa: yes absolutely.

Johannes: are the right people in this call? Should there be more people participating who are implementors?

Evan: I think not. WE do have people from Mastodon and other projects. It's reasonable for us to get started here and worry about the other part and getting people engaged later.  As a standards Task Force, our job is to get the standards going

Lisa: Who else?  I don't want to both run a TF and take informal consensus calls AND write the docs!

Tantek: for this export item, Manton Reece has worked on the "Blog Archive Format" (BAF) for import/export for micro.blog content, blogs etc..  The micro.blog service supports many formats & protocols (ActivityPub+AS, Webmentions+microformats, Bluesky) so I feel that this is the common carrier export format, superior to RSS, it may be superior to raw activity streams as it is really interoperable between different protocols.  

Evan: This sounds really interesting.  I do feel that activity streams could be the main format used here.

Emelia: Could one of the reasons not to use activity Streams be that the object ID is going to change?  

Lisa: I am open to both/either (activity Streams or more generic format) , I don't think object IDs are a barrier to using either, this moves us on to the object ID discussion

Andy in chat volunteering

Aaron: Everything will need to be signed and possibly encrypted.

## Object ID persistence

Lisa: points to email april 16 with assumptions

Aaron: so we're talking about a mapping to a new object ID

Lisa: yes and that would be up to the destination server to decide how and what to do.

Evan: Copies of a thing can have a "copyOf" attribute

The new server might already have copies (because an item was shared or liked) and it might not need to actually create yet another copy while transfering an account.

Andy: An array of breadcrumbs

Aaron: If we have an array of *breadcrumbs*, each with the transfer date and Object ID. Although maybe people may note want to keep all of that history, that might be an option not to keep all the older server Object ID references.

Emelia: A lot of systems use Snowflake IDs, these are time-ordered IDs.  They need to generate IDs that are IN THE PAST to insert "older" posts.  Daniel Supernault (@dansup@mastodon.social) had to write a bunch of code to insert IDs into the past (for the Instagram import functionality). it would be worth talking to folks like that to get a sense of it.

Evan: And that is in order to keep posts sorted, rather than try to sort by date, the object IDs are faster to sort.  When you're requesting a page of records, and they all happen within a month, those are all stored in a page in the DB

Aaron: I think mapping IDs will be quite pragmatic. we may need to reach out to coders/authors and produce a default pragmatic implementation for mapping them.  with unit testing.

Evan in chat: IDs are per-implementation and should not be part of the spec.

Johannes: Why can't we simply delegate the mapping to the people implementing?

Aaron: it's a completeness problem

Emelia: Object IDs can definitely be treated as a pure IDs.  Separately, we have access to pbulication date and other information, and a server can generate an appropriate ID without parsing the old object ID.

Tantek: From a user perspective, if a user is going to export one place and import another place, they are going to need a single file. That's why Manton worked on this, it produces a single ZIP file with all the resources.  ActivityStreams is a stream but it relies on outside resources.  It is not, itself, an import/export format.   Right now blog archive format is specified well enough that it can be implemented. Whereas, there is no equivalent for activitystreams.  You could invent a new format to export activityStreams and it would include a Activity Stream data but also additional structure that is yet to be defined.  

Aaron: link plz (https://indieweb.org/blog_archive_format)

Evan: I agree with Tantek that we do not yet have a defined data export format for AS.  There are some de facto "standards" - mastodon's data export is activityPub based. you get your full archive in AS format. It's worthwhile looking at the blog archive backup format.  We should keep the AS-based ones in mind too.

Lisa: having different companies run the same server as a way to do portability doesn't work in the long term.

Aaron: I still think we need to have a holistic approach.  We should work more like the IETF and have a reference implementation.  

Lisa: Oddly, this is not the preferred or more commn approch in IETF -it's a backup approach when there aren't enough implementors participating

Aaron: I think we still need to do it.

Lisa: are you able to work on that?

Aaron: Regarding the data format and the wider view, facebook and twitter, they all allow you to download your data.  They were meant to be forming a standard for that long ago, and they did not, it's dead.  If you look at the FB export you lose all your privacy settings; if you use Twitter you get URLs that are twitter only - they are having wars.  Unless we have standards to nail this down, people are going to have different  features and diverge.  

Evan: I don't think there's anything in the work we're doing preventing other networks from implementing.  I want to highlight that the DTI (of which Lisa is the CTO) has been doing amazing work providing online transfer of data.

Tantek: DTP predates DTI (lisa agrees)

Tantek: platforms doing exports can be pretty bad.  But I could open up an export on my machine and it was *browsable* - this was a big usability plus.  I could confirm the data or see if it was missing data, like missing the name of your friend and only having a random ID.  It was user browsable as well as machine-readable.  I think any export format should be user-browsable in order for users to trust it.  If you don't do that, people don't trust that they have all their data.  

Emelia: Verification tool for export: does that tool need to be ebmedded in the archive that it's shipped in, or could there be a tool for browsing archives?  It could even be a Web app that doesn't upload data anywhere.  What architecture are we talking about? if we have a viewer embedded in the archive , that's larger.

Aaron: Having the HTML in the download, or separately, both, as options. As soon as you have data outside the OpenID system, it needs to be signed, possibly in chunks, if you want to import just separate bits. So everything needs a signed, by the source server. So we know somebody hasn't tampered with the data and then uploaded it. They could even scrape someone elses data and format it into the import/export format and import it back into another account so impersonating them.

Tantek: To respond to Emelia, the maintenance of a separate tool is greater than a one-time export of browsable HTML.  Every service that went down this path to answer this question came to the same conclusion.  The browsers will support it forever, it's cheap to maintain.  Smaller companies will find the same cost structure. I feel that debate has already occurred and we'd be fighting the economics.

Emelia: The comment is really actualy, I've downloaded my Twitter archive before, and it does have browsable HTML, but it really pulls it down by AJAX.   we should have shared code. Its not about shared code, it's more about

TanteK: It's not a separate tool, it's HTML.

Emelia: fully formed HTML.  fair enough.

Lisa: Wrapup !  i will be sending much text!

- these notes to mailing list
- Tantek to post to wiki ✅
