# 18 Oct 2023 - Helge, Bengo - Test Case Design & Documentation

## Resolutions

None taken

## Minutes

- Attendance (optional/honor-system)
  - @bumblefudge
- Links
  - [Agenda email](https://lists.w3.org/Archives/Public/public-swicg/2023Oct/0045.html)
  - Helge's [Fediverse Testing repo](https://helge.codeberg.page/funfedidev/)
    - example [test case](https://codeberg.org/helge/fediverse-features/src/branch/main/w3c/ap_follow.feature)
    - [slides](https://bovine.social/assets/presentation.pdf)
  - Bengo's test case and YAML-ized behavior [repo](https://git.coop/socialweb.coop/activitypub/behaviors/)
    - [Which ActivityPub Server Requirements are easy to test?](https://bengo.is/blogging/easy-to-test-activitypub-requirements/)
    - [Use Test Specifications to Improve Testability of ActivityPub Requirements](https://bengo.is/blogging/use-test-specifications-to-improve-testability-of-activitypub-requirements/)
    - [Introducing ActivityPub Requirements Cohort 1](https://bengo.is/blogging/introducing-activitypub-requirement-testing-cohort-1/)
- Fediverse Features- Presentation by @Helge
  - Context - different layers of testing (slide 1)
  - Gherkin as example of situational testing
    - Business case (UI-level) example, truly "BDD" (behavior-driven)
    - less-obvious usage: wrapping a Unit test in a gherkin feature (Use case data slide)
      - bob: are you auto-generating code or hand-writing it based on these test cases?
      - Helge: there are tools for that (behave for python, for ex.), but usually worth hand-editing even if you generate code automatically
      - Helge: ex unit test code corresponding to this unit-test feature is at codeberg.org/bovine/bovine/.../fedi_follow.py
      - bengo: would it help to have a stable identifier for addressing the test vector or test vector template in cases where it's generated at test runtime?
      - bengo: could gherkin @ decorators be used to separately-maintained vectorset?
        - helge: @ decorators are like `#`s or `//`s for remarks,
          - for example ![screengrab showing decorator usage for remarks](https://hedgedoc.socialweb.coop/uploads/90d92599-322d-4bf9-9dff-894cb1f270ad.png)
        - helge: I would say that gherkin tooling is pretty robust and well-maintained, so we should could look around for annotation tooling?
      - bengo: what's the best spec to use for gherkin syntax itself?
        - helge: the syntax is so simple, there's not much to specify
        - bengo: I found several, tho; should we just assume this is the canonical one? <https://cucumber.io/docs/gherkin/reference/>
        - helge: one feature I found is "data table"
    - Features wrapup:
      - Bengo: would <https://www.w3.org/copyright/test-suites-licenses/> work for the license?
      - Bengo: I'd like multiple drivers, partic a browser-driven one? is there a way to make multiple bindings verifiable?
        - maybe parameterize waits and sleeps?
        - Bengo: IMHO parameterizing would be a stitch in time for sharing across diff test environments
        - Peter Zingg (in chat): [Example of browser testing with Gherkin](https://www.lambdatest.com/blog/behaviour-driven-development-by-selenium-testing-with-gherkin/)
        - bengo (in chat): +1 I've done it with cucumber-js to mixed results
- Fun FediDev - Harness for dockerized servers - Presentation by @Helge
  - since so many servers are already dockerized, I made a harness for spawning some locally, creating accounts on them all, and having them communicate between containers on HTTP (HTTPSigs optional)
  - one glitch: doesn't currently support updates to an actor's signing key (PRs welcome)
    - scribe aside: is this a job for the data portability task force? at least use-cases would help here for cross-referencing/checking against
  - support table example
    - bengo: just by object type? helge: none yet, but many planned
    - (screenshares already-live display of test vectors, from "example" column of today's displaying support table)
- Biographical aside - actually started building htis harness to test hashtag normalization for a FEP
- Bengo's Presentation
  - [repo](https://git.coop/socialweb.coop/activitypub/behaviors/) autopublishes to a [web preview](https://socialweb.coop/activitypub/behaviors/) and NPM
    - returns mime type JSON so you can pipe to jq, etc
    - can curl from socialweb.coop/ and get the whole set
  - easy/medium/hard/nearly-impossible scheme
    - would rough consensus on "easy" set unblock cooperation?
      - [Which ActivityPub Server Requirements are easy to test?](https://bengo.is/blogging/easy-to-test-activitypub-requirements/)
    - sorting behaviors by sub-resource required: object (in general), actor, inbox, outbox, followers collection, liked collection, likes collection, and/or shares collection
    - Helge (in chat): Hell: Test cases that require THREE Servers, such [as this example](https://media.hachyderm.io/media_attachments/files/111/104/507/048/912/919/original/3982f5534dac30f0.png)
  - CTA - do people have more or less easies?
- Discussion/Q&A with @Helge and @Bengo
  - assumptions and supersets
  - Helga CTA: people are welcome to PR in more docker images to my harness! i need to focus on other work rest of the year
    - i'd love it if someone got friendica in there
  - bengo: we COULD start connecting my AP work to helge's and stevebate's drivers (by behavior)
  - Angelo: web-based "are we _ yet?" site worth making? is that a goal?
    - bengo (in chat)
    - juan: I would say it's worth doing for the easy tests but realistically couldn't be complete/exhaustive for conformance OR interop purposes
