# 2023-08-04 W3C SWICG Special Topic Call: SocialWeb and CSAM: Liabilities and Tooling

CPEC Code of Conduct: https://www.w3.org/Consortium/cepc/

### Participants

* Kainoa Kanter
* James Gallagher
* Dmitri Zagidulin
* Bob Wyman
* Jaz-Michael King
* Angelo Gladding
* Elgin McLaren
* Evan Prodromou
* Jessica Jordan
* Gregory Scallan
* Mehdi Benadel
* Darius Kazemi
* bumblefudge
* Bengo
* Todd

### Reading and Resource List

#### General Information
* Recent Stanford report: https://cyber.fsi.stanford.edu/io/news/addressing-child-exploitation-federated-social-media ([Report PDF](https://stacks.stanford.edu/file/druid:vb515nd6874/20230724-fediverse-csam-report.pdf))
* [Moderating the Fediverse: Content Moderation on Distributed Social Media](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4213674), Alan Z. Rozenshtein, 3 Journal of Free Speech Law 217 (2023)
* [User Generated Content and the Fediverse: A Legal Primer](https://www.eff.org/deeplinks/2022/12/user-generated-content-and-fediverse-legal-primer)
* [Notes on operating fediverse services (Mastodon, Pleroma etc) from an English law point of view](https://decoded.legal/blog/2022/11/notes-on-operating-fediverse-services-mastodon-pleroma-etc-from-an-english-law-point-of-view)
* [Scaling a public Mastodon instance: Legal, compliance, privacy and more](https://bottomlinelawgroup.com/2023/01/23/mastodon-instance-legal-compliance-privacy/?doing_wp_cron=1691167165.0044350624084472656250)

#### European Union

* [Digital Service Act reporting requirements](https://digital-strategy.ec.europa.eu/en/policies/digital-services-act-package)
* Evidence-based recommendations on how to improve child safety (at least in the EU) are available from EDRi: https://edri.org/wp-content/uploads/2022/10/EDRi-Position-Paper-CSAR.pdf (posted by [@Federico on the SocialHub thread](https://socialhub.activitypub.rocks/t/about-child-safety-on-federated-social-media/3447/8))

#### USA

* Q from Bob Wyman: "Are operators of ActivityPub instances considered to be "providers of electronic communication services or remote computing services" who, if in the USA, have a legal obligation to make reports to the [NCMEC](https://www.missingkids.org/)?"
  * Answer from Darius Kazemi (with the biggest "I AM NOT A LAWYER" disclaimer ever): "Yes. Critically, the legal obligation comes once an operator is made aware of the presence of CSAM. An operator is not legally obligated to actively scan and search for CSAM material, and is not on the hook for material hosted that they do not know about, but rather they must report to [NCMEC](https://www.missingkids.org/) when they are made aware of the CSAM material. They must then retain a copy of material for 90 days (I believe to assist law enforcement if needed) and then must delete the material after 90 days."
* [federal statute](https://www.law.cornell.edu/uscode/text/18/2258A)
* [NCMEC](https://en.wikipedia.org/wiki/National_Center_for_Missing_%26_Exploited_Children)


#### Other Jurisdictions

* Australia: https://icmec.org.au/
* New Zealand: https://www.dia.govt.nz/Digital-Safety-Report-Online-Child-Exploitation-material
* Canada: https://protectchildren.ca/en/
* United Kingdom: https://report.iwf.org.uk/org/

#### Tools and APIs
* The community/moderation non-profit [IFTAS](https://about.iftas.org/) has been researching where and how some of offerings below may be incorporated into broader service offerings for instances/communities; their [matrix](https://matrix.to/#/#space:matrix.iftas.org) server is a good place to discuss, whether technically or not
* [PhotoDNA](https://www.microsoft.com/en-us/photodna)
* [Overview of Google's toolkit](https://protectingchildren.google/tools-for-partners/)
* [Safer by Thorn](https://get.safer.io/csam-detection-tool-for-child-safety)
* [Project Arachnid](https://projectarachnid.ca/en/#what-is-project-arachnid)
* [Cloudflare R2 bucket auto-filtering](https://blog.cloudflare.com/the-csam-scanning-tool/)
  * [Tutorial for firefish](https://socialweb.coop/blog/firefish-cloudflare-quickfix-r2-tutorial/)
* [Hive.AI tagging (CSAM model in beta)](https://docs.thehive.ai/docs/detailed-class-descriptions-text-moderation#child-safety-model-head-beta)
  * [hive-tagger NPM package on bluesky github](https://github.com/bluesky-social/atproto/blob/main/packages/bsky/src/labeler/hive.ts)
* Perceptual/Distance/Fuzzy hashing
  * [Alex shared this journal article introducing the problem space and families of solutions](https://tsjournal.org/index.php/jots/article/view/24/14)
  * [ISCC - OS codebase that includes both content hashing and perceptual hashing](https://iscc.codes/)
* [Draft API dictionary](https://transparency.dsa.ec.europa.eu/page/api-documentation) and [API prototype](https://github.com/digital-services-act/transparency-database) for incoming [Digital Service Act reporting requirements](https://digital-strategy.ec.europa.eu/en/policies/digital-services-act-package)
  - [A commentary on it by Daphne Keller](https://cyberlaw.stanford.edu/blog/2023/07/rushing-launch-eus-platform-database-experiment)
* Cloudflare's CSAM scanning tool: https://blog.cloudflare.com/the-csam-scanning-tool/
  * Tutorial on setting up the Cloudflare R2 tool with Firefish (formerly known as CalcKey): https://socialweb.coop/blog/firefish-cloudflare-quickfix-r2-tutorial/

### Agenda

1. Code of Ethics & Professional Conduct Reminder:  https://www.w3.org/Consortium/cepc/
2. W3C Community Group Process and Governance: https://www.w3.org/community/about/process/
3. IP Protection Note:
   a. **Anyone can participate in these calls.** However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
   b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA):
   https://www.w3.org/community/about/agreements/cla/
4. SocialWeb and CSAM discussions
5. We'll be joined by David Thiel and Alex Stamos, from the Stanford Internet Observatory

### Questions from Chat

* Bob: I am concerned that the report may be a bit misleading since it didn't provide jurisdiction-specific incidence rates. (i.e. In Japan, much of what others say is CSAM is actually legal and thus much more common than in EU and US.)

### Notes

Juan: A few days ago, there was a post on SocialHub with the Standford CSAM report. In parallel to that, there's been a lot of interest in the Fediverse in moderation mechanics. When I stumbled into it, started asking questions and chasing threads, I realized that IFTAS have been doing a lot of research on this at various levels (Fediverse and beyond). There's a lot of related topics regarding moderation toolings that might be out of scope for this particular call. But CSAM may be a more narrow topic to start.

EvanP: Stanford Internet Observatory is a research group that does security work at Stanford. They did a statistical analysis of output from the top 25 Mastodon servers (they were using public feeds from those servers), and they used industry standard APIs for doing checks for CSAM (PhotoDNA and Google Safe Search), doing scans for hashtags often used in child abuse circles for CSAM. They were able to identify 10s of thousands of CSAM items, which is what initiated the report, and resulted in a feature article about it. This kicked off a lot of discussion in the past several weeks.

There are some issues we're going to have regarding dealing with CSAM on the Fediverse, not least because it's extremely toxic content to handle, and testing and maintenance is very hard to do. And tooling for reporting CSAM content used by mainstream networks is very centralized. You have to submit full images, not just hashes, it has a system of reporting content directly to the feds (US gov't). So, as centralized as can be, but it's state of the art.

Jaz-Michael: [IFTAS](https://about.iftas.org/) is a non-profit that has recently incorporated; we've been working on something since Nov-Dec last year. It's intended to be a way to get foundation money into Fediverse, and out to moderation communities in Fediverse and decentralized social media. As far as CSAM specifically, we've been looking at it as something we want to work on. The story from a few weeks ago and the Stanford paper really kept motivating us. Right now, IFTAS is generally considering building on third-party moderation tooling. One of those things is likely going to be some form of CSAM scanning and reporting for fediverse service providers. We're talking with Fastly, PhotoDNA, Thorn, some of the Google tools, etc. We're hoping to hit the big hosting companies that can use things like Cloudflare's CSAM scanning tools. For larger providers, we hope to connect them with services like Thorn. [...]

Evan: Jaz, do you have like a roadmap expectations for CSAM scanning for Fediverse developers? If somebody wanted to start building this out for their implementations, any thoughts on time?

Jaz-Michael: Due to number of platforms and implementations (Mastodon, Pixelfed, Lenny, etc etc), we have danced around seeing if we can build some of these APIs into systems, and while we think it's noble to do, it's not in our purview or capabilities. Right now, we're exploring with engineering at Thorn re what thihs service might look like. We're also following in Bluesky's steps, since they're creating a moderating and scanning service. So we're probably ~2 weeks away from knowing how that turns out, so hopefully we can follow.

Evan: So, for folks on the call, for implementers, today, probably the best choices are going to be things likek PhotoDNA, which are live and working. You have to apply, but they work today.

Jaz-Michael: We're happy to help in any way with these conversations. Services like Thorn don't want to interact with like 25k providers, so we hope to be able to mediate / narrow the conversation a bit.

Evan: I want to point out that there's a reason that these providers don't want to have wide-open systems, and the reason is -- purveyors of CSAM will do adversarial hash checks, and alter their content so it no longer flags, to circumvent.

Jaz-Michael: Yeah, there's a number of techniques there, perceptual hashes, etc.

Kainoa: One of the things, as an implementer, I feel likek with the talk of APIs, there really should be better offline options, such as being able to match perceptual hashes against snapshot databases. What Misskey does right now - it has an offline available Tensorflow model to detect some of the material. It's not perfect, but openly distributed. So, if there was some sort of similar lightweight model admins could run locally, instead of relying on a third-party API, that would work better. That's even aside from considerations of pricing plans, etc.

James G: One thing wrt running vision models on the instance, is questions of liability, and maintaining such a model requires significant efforts, and adapting to managing model drift etc. It almost necessitates a central service for such models, which also **assumes liabilities for false positives**, etc.

Darius: As much as I like the idea of running local check services, there's a lot of security-by-obscurity at work here, whether we like it or not, to avoid sharing feedback with adversaries. That said, many who do not want to work with such systems, and a "second-tier" option downstream of that (inherited tagging, for example).

Evan: Maintaining a model requires handling a lot of toxic material, it's NOT something every instance operator or codebase wants to do in parallel. I do not want that for anyone, god bless specialists doing this so most of us will never have to.

Jaz: Any possession is equally illegal, so hard to train models. The hashes themselves are closely guarded. Following up on Bob's comment in chat, Japanese servers mentioned in the reports weren't hosting CSAM-adjacent content, it was CSAM. Enforcement in Japan is not always aggressive.

Bob: Breaking up the problem a bit-- this might create cruft and technical debt, and might not be in the scope or best interest of this group. I think annotation of content is essential to keep constitutive (software, at upload) from reactive/executive roles (proper to moderation/governance); this is what bluesky is doing, using ML to annotate and leaving policy and enforcement to instances (and/to end-users).

Mehdi: Jumping to technical solution rather than wondering the degree to which CSAM is actually a problem for [the entire] Fediverse per se. We might need to define and model a bit rather than assuming a simple/straightforward, unambiguous content.

Kainoa: Pawoo got banned by Misskey central command 6 hours ago! NSFW model comes from some fot

Alex Stamos: ... We do a lot of work on security, preserving privacy, encryption, but also focusing on safety work, including CSAM. David and I both come from working at Meta, specifically CSAM in the commercial media context. We've done lots of reports in the past year on child safety on major commercial instances (Instagram, Twitter, etc), and we've been doing a project on "How do you think about Trust & Safety in a Federated Context", and this was the first in a series of reports. We have a student working on legal issues under US law, then also will handle EU law, especially DSA, which Fediverse will have to deal with.

You all saw the report; the outcome is - there is a decent amount of CSAM in the Fediverse. Some of it is real images of real children, in the known hash databases. I want to dispel some illusions up front. A lot of the response was "This is a Japanese problem", but many of the largest US and EU instances have similar problems. And even when informed of that, their ability to respond has been limited. So it's not just Pawoo and other Japanese servers, though there is a complication wrt Japanese law, and some of the content that's legal there that's not legal elsewhere. But this is a global problem.

Second issue, I think there's a whole bunch of layers here, for why you want to prevent this content from being transfered. But there are legal obligations that attach to being what's called an "electronic service provider" in the USA, and unlike EU's DSA, there is no de-minimis standard, so, basically a large number of US servers are not in compliance, which is a federal felony in the US. So, we want to explore some solutions, that we can enable owner-operators to be legally compliant, and to police their servers for this, hopefully in a way that doesn't require massive manual labor outlay. This stuff has a huge impact on individuals; one of the things we're hoping to speed up - there's been a lot of work in commercial media space on moderator mental health. People clicking through reports is neither scalable or ethical, so hopefully we can come up with technical solutions. David?

David Thiel: Sure, so, there's a couple of components here. I've been talking to folks running Mastodon Social, what the issues are there. A lot of the content is getting by either cause people are not reporting it, or lack of moderation tools. Sometimes up for weeks. People ARE reacting quickly when we bring it to their attention. The other thing at play yhere - I looked at the data from 2022, the only visually familiar company names that I could find -- I could not find any reporting from Mastodon operators from NCMEC; the only reporting I saw was from the holding company from Truth Social. And I want operators to do better than Truth Social :)

Alex: Yeah, that'll be our low bar. (And we've written a lot about Gab, Truth Social, etc.)

David: Right, so, we don't need to re-hash recommendations from the report. The challenge from the WG that has been looking at these issues (IFTAS) - I've seen that there's kind of a faction in those groups that still kind of holds on to some antipathy towards using any closed-source or third-party service for scanning content. So, I see there might be some factionalization ahead regarding solutions. We obviously recommend industry standard solutions; they're not the only ones, but implementing other solutions will be very labor intensive.

[James: Gives his apologies as he has another engagement to which to attend. Will review call after meeting and notes.]

Alex: We talk about solutions, but also there's a taxonomy here, wrt Child Safety world. Let me share some slides here from our lectures here at Stanford. Re taxonomy, so we're all on the mpage, when we talk about online sexual exploitation, there are some situation that happens with the child's participation - either teenagers selling content, or adults reaching out to children and blackmailing them into producing content. And another situation where it's just adults in a criminal conspiracy. Forthcoming European and U.K. law is increasingly addressing these situations in particular.

And that's the main technical distinction - if the content is known, if it's been seen by a major social media provider (perceptual hashes - we have a good intro on the tech), there's a bunch of pretty technically easy (but architecturally challenging) solutions. We just have to figure out how that applies to the Fediverse. For new content, that's a huge challenge even for large multi-billion $ providers, much bigger challenge.

So to start, maybe it makes sense to start with that, with already known content from adults.

Evan: I find this topic terribly depressing, really hard to deal with. I admire professionals that spend their time on this. I wonder, with your experience with commercial social networks, does implementing some of these standard tools -- does it actually help? Does it reduce occurrences?

Alex: Great question. One of the reasons we do our work, started our journal, is there's not a lot of empirical evidence on the impact of some of this tech on safety. I would say - widespread trading of known CSAM is something that's become much more difficult to do among commercial providers. Doesn't mean it never happens, the whole NCNEC system, they're approaching around 40 million reports a year. What is a report? One report could have anywhere from 1 to a thousand images, etc. Anyways, if you look at those stats, people are still trading CSAM, but their ability is greatly reduced. So, if you're trying to prevent adults using your platform to trade CSAM, perceptual hashing is absolutely an effective solution. (Not to get too deep into it, there's medical research into this, there's an addiction / biological predilection, people who offend go through thousands of images, so perceptual hashes helps catch.) I supervised a whole child safety team that David supported as a technologist; we were running a conference on this stuff, and we had a wall of headshots of offendors - it's adults in positions of authority interacting with children.

David: what you mean by "success" may vary, though; arrest? rate of intervention when victim is alive is perhaps the generally a metric that proxies well to effectiveness by most people's priorities. pushing bad actors to other platforms is only success for the liability of the instance. detection and doxxing/real-world-identifying risk is something that coordinated strategies try to optimize, and perceptual hashing is generally more effective for this.

Mehdi: In making sure we're abiding by the law, and the goal of the Fediverse operator ensuring it's a safe space. I don't know if this distinction is important for us, or if picture sharing is more of a problem than general harassment in the Fediverse. Can we make sure we don't go overboard, but also abide by the law?

Evan: Firstly, I want to make sure, we're on a special topic call specifically on CSAM; if we want to discuss moderation in general, we'll have other calls on those.

The question I have for Alex and David is two part. 1) Top 3 recommendations for Fediverse devs for getting started with this work. 2) Would you be willing to re-run the stats in 6 months to a year, to measure how well we've done.

David: Answering the second one - we'd be willing to re-run the tests. The nature of how we can run them is going to change; the next version of Mastodon, it's going to switch to authenticated mode to the streaming API, which will change nature of our survey. So we can definitely do like the top 25 servers, but some of the other tests won't be able to be repeated. So, yes.
In terms of things individual operators can do right now - I think that the most effective.

Evan: Wait wait, specifically developers.

David: For devs, there are a couple of things that are relatively low-hanging fruit. One thing I would do is try and address the gap in reporting, since that's the most prominent legal liability. And really doing that is going to involve writing some glue that reports to entities like NCNEC.

Darius: Briefly, it's difficult to make reports to NCNEC when you don't know you're hosting this info in the first place. Did the server operators know they had this content and didn't report?

David: What people are doing is - they're taking reports from users, and taking down the content without reporting to the gov't. I don't know what EU law is like, but even among above-board instances, we're not seeing legal levels of US operators.

Darius: Yeah, to clarify, for US operators, just deleting is not abiding by the law, you actually have to report it to NCNEC. This is an education issue; operators don't know they have to do that.

Alex: Yeah, we're trying to write requirements and recommendations. So, there needs to be work on these platforms in general, to make pluggable trust tooling that fits into different streams of content as it moves through your server. None of the major platforms make it easy like, to run a script for each piece of content, or have rules for what should happen if there is a detection hit. So that's going to be key, both for CSAM, but also general violent and hateful content (like beheading videos etc). We need to have a service people can use, based on legal issues around accessing PhotoDNA. IFTAS is looking at some of this stuff, creating a centralized service that can do the scanning, that handles reporting and archiving. It's unrealistic to expect a thousand server-operators reporting this stuff individually and archiving the report. These services exist, but they're commercial and cost money, and require contractual relationships many operators won't want to participate in. So, creating a free central service would be key. (Keep in mind that this is just about public content so far, which is a slightly more tractable discussion.)

Jaz-Michael: Our concern is that these services don't get weaponized (used as means to take down services, maliciously), so that's what's driving some of our activity at IFTAS. Before we adjourn, I was wondering - I've heard a lot of feedback "oh these numbers are small." These numbers are NOT small, so I was wondering if you could comment on that.

David: I can compare two analyses we've done on other platforms. Of sites like Gettr (?) and Gab, and we've found tiny handfuls on the entire site. There's been analyses on Telegram, showing a significant number of lapses there. In terms of fediverse number, if anything, we've under-reported the numbers.
