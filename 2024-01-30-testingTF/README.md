# Test Case Design Workshop

- Attendance
    - bumblefudge @by_caballero@mastodon.social https://learningproof.xyz
    - Johannes Ernst @j12t@social.coop https://j12t.org
    - Evan Prodromou @evan@cosocial.ca
    - Matthias Pfefferle @pfefferle@mastodon.social
    - Fredy (naturzukunft) @naturzukunft@mastodon.social https://rdf-pub.org
- Agenda
    - mailing list [thread gathering agenda](https://lists.w3.org/Archives/Public/public-swicg/2024Jan/0031.html)
    - Announcements
        - Johannes - Fediverse Test Suite ("feditest") project now funded by NLNet (5m?)
        - Bengo - async update on STF Testing Project [on list](https://lists.w3.org/Archives/Public/public-swicg/2024Jan/0040.html)
    - Topics
        - Marcus: ongoing, everyone-friendly testing versus developer-only tools? (10m)
        - Marcus: How test the async/distributed behaviors? "Friendly feedback"? (10m)
        - Johannes: Which tests are worth running? How modularize? (10m)
        - Johannes: Conformance Testing versus [Real-world] Interop Testing (10m)
        - Evan: Deliverables for the TF? (5m)
- Johannes - https://feditest.org (5m?)
    - will be blogging actively with project updates, also @feditest@mastodon.social
    - planning periodic office hours for show-and-tell-and-feedback
    - evan: is scope doc on there? johannes: yes, all links from https://feditest.org/ including plan; no code linked yet, because it's still exploratory, will share in a future meetup
- Marcus: ongoing, everyone-friendly testing versus developer-only tools?
    - Main point: unprivileged (non-root on their own servers) end-users should have ssome access to testing as well, not just devs
        - user story: user A of server X can't succesfully follow or message user B on server Y; how can I run tests on server X & Y to know who is out of conformance, 
        - Johannes: do test suites have user stories? I have a [slide](https://feditest.org/blog/2024-01-30-testing-tf-slides/): FediTest is for these two personas, and those needs
        - evan: this is entirely possible because AP is tested at the network boundary; precedents: [ipv6](https://test-ipv6.com/), [mx records](https://mxtoolbox.com/SuperTool.aspx?action=smtp%3aprodromou.name&run=toolpage), mro: matrix federation has a test like this; bengo [our WIP](https://socialweb.coop/activitypub/actor/tester/) would theoretically do this
        - evan: hypothesis: should be possible to run specific tests without permissions if a test runner requires no privileges on server Y, i.e. "can this server accept a federated image" or "does it accept DMs from a server on X" (server X-specific inputs)
        - bengo: might need multiple kinds of test runner; local test runners (that run on the server under test) need privvies but remote test runners should be able to set up and destroy after a server X to test server Y
            - evan: caveat: may need to use an existing account on server X if you need to test "from" server X
            - johannes: testing TF report that included these user stories and progress against them could help educate users of what we release
    - for later: Centralization of deployments? 
        - bumble: package managers?
- Marcus: How test the async/distributed behaviors? "Friendly feedback"?
    - Mro: Outside of scope of AP standard I think: servers need time to respond to some thing, but hard to know when to timeout or what to do if a response never comes; 
        - even if i'm blocked or banned, "i will not respond" response might be good to send?
        - only ignore requests that we suspect of being malicious or DOS/spam
        - Responses not really covered explicitly in AP due to layering (security and DOS-protection out of scope?)
        - evan: I think the AP spec DOES cover a lot of behaviors, tho, it's not totally mute on response obligations! I think it's mostly phrased as "side effects" and kind of implicit logically in some of the language, i.e. spec was written assuming HTTP code familiarity
        - evan: Reject Activity is the suggested mapping to "I Will not respond", although proposing a thorough mapping would make a great FEP
        - evan: security trumps conformance, even if the spec was very explicit about responding to everything
        - johannes: testing mode versus production mode - fully secured deployments tend NOT to send helpful debugging feedback :D; controllability versus observability in classic system theoretical terms: for tests you want as much controllability and observability as possible, for production as little as possible (security): why we have the notion of an "AppDriver" in FediTest that only runs during test.  
        - bengo: I would also +1 the utility of having a debug interface or debug mode (even though it demands a big implementation lift of servers); i have been trying to see how far i can get WITHOUT that kind of help, remotely/externally/in prod mode
            - fredy/naturzukunft: usecases in Nodeinfo <> testing usecases? don't run tests for behaviors a server is telling you it doesn't support?
            - bengo: a FEP defining a debug interface would allow servers to announce its availability!
            - evan: even in prod, responses rooted in activity vocab could be helpful- for ex., if X sends Y an activity it doesn't support (e.g. Checkin), Y could respond "huh" and X could try again downgrading it to a Note (this kind of activity failover is already how Articles become Notes across federation today in many cases)
                - naturzukunft: object types work this way too already in some cases
            - johannes: FEP not necessarily required? good enough to run tests > w3c standardization
    - bengo: example of "internal behavior tested externally or distributed behavior 
        - [example](https://activitypub-testing-website.socialweb.coop/58b55b12-550f-415d-9ce4-a5160c08676f)
- Johannes: Which tests are worth running? How modularize?
    - bumble: phrase as a user story about selective running of a test suite or project?
    - johannes: this might be a standing/recurring item of discussion for this group, not addressable in 10min!
    - johannes: I have a [slide](https://feditest.org/blog/2024-01-30-testing-tf-slides/)
        - I made a custom web component that lets me put tests definitions right into the HTML of the spec
        - marcus: I think linking directly to the spec is interesting; there's a turtle/RDF precedent here; how did you link them in your test suite?
            - johannes: I did a custom html tag; mro: where is it persisted, tho? johannes: i inline it into a wrapped HTML page; 
    - johannes: I use a slug including the section/subsection number in the document being referenced
        - johannes: testability of requirements may be contingent on profiling the spec, where specs include untestable bits?
        - johannes: some behaviors assume many actors (actor A on application X and actor B on application Y), and these are only testable depending on which of those actors/applications a test runner can "be" at time of test
    - johannes: test ids are a big design question - they're needed for traceability between tests and specs
    - johannes: tentatively, we're thinking of making "source" folders for each spec or spec-like anchor document and "combination" folders that pull from them, e.g. "webfinger", "activitypub", "http signature", "fediverse" (the combo)
- Johannes: Conformance Testing versus [Real-world] Interop Testing
    - bumblefudge: good transition
    - johannes: standards documents assume a certain modularity; "test all" isn't really practical under many circumstances, e.g. for developers, can create a huge lift to even make 
        - maybe a user starts by defining their "test plan" before first run; johannes: many test projects i've worked on HAVE this notion internally without exposing it, but i think here we really should expose it since there isn't a pre-existing shared target of what's worth testing
        - bengo: w3 conformance precedent has a lot of cool terminology and tooling for this kind of stuff: the [ACT Rules](https://www.w3.org/TR/act-rules-format/) could be really helpful as a standard format for capturing applicability to user stories like "i have a actor URI and i want to run tests against it remotely"; see also [solid qa](https://solidproject.org/ED/qa), or [ACT-R in the wild](https://github.com/act-rules/act-rules.github.io) in accessibility
    - johannes: what's WORTH testing? do we need 100% coverage?
        - most complex test I encountered so far: how test Delete activity where the to-be-deleted item has been shared to many servers?
            - evan: user A on server X shares object L, then sends delete, server Y can be tested by a few fetches before and after? there is a tombstone object specifically to make this testable (assuming test runner has access/authN to see object L)
            - johannes: but what if server Z had already made a copy before Delete got to server Y?
                - evan: but server Z shouldn't make the object public/viewable if it wasn't a recipient of the original activity; that's more about cache/garbage collection
                - bengo (in chat): It seems to me that its a somewhat inalienable right to copy messages (in email, handwritten notes, fies, etc), and therefore it might be hard to write a test to prove that someone has deleted all their copies. 
- Evan: Deliverables for the TF? (5m)
    - bumble: what would help? i don't wanna do opinionated or original work,, i wanna stay neutral
    - evan: why not a Report synthesizing or overviewing what's built at a checkpoint?
    - evan: blessing one test suite as Our Test Suite is a thing we could do?
    - bengo: +1 to johannes, usecases for testing would a great short-term deliverable
        - bumble: yeah doing that first makes me less nervous about being opinionated
        - evan: process-oriented task force (meta/support role) is useful, doesn't NEED to release reports to be useful; just wondering if reports (or any other concrete deliverable goal) might be additive to that mission
        - johannes: agree on what tests are WORTH writing more useful than blessing tests; different interpretations of the specification could get in the way of defining interoperability targets, so tentatively or contingently agreeing to the latter get us to useful testing sooner
        - bengo: agreeing to what test cases are just moves the chaos to a different layer, it can still be chaos and power vacuum leading to centralization; i would rather allow people to make test cases rather than make unanimous agreement on test targets a blocker for that work; 
- Parking lot:
    - deployment centralization?
    - merging rules for behavior yamls?
        - [socialweb.coop behaviors use UUID `id`s](https://codeberg.org/socialweb.coop/activitypub-behaviors), but sounds like feditest using strings/slugs?
- References:
    - Johannes' slides are available in higher resolution [in this blog post](https://feditest.org/blog/2024-01-30-testing-tf-slides/)