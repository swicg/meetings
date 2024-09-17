# 2023-08-11 W3C SWICG Special Topic Call: AP Interop Test Suites

Call Notes: (will be archived over at https://github.com/swicg/meetings)

## Participants

- Dmitri Zagidulin
- James Gallagher (jamesg.blog)
- Helge
- Tim Chambers
- Ben Pate
- Matthias Pfefferle
- bengo.is
- Mayel (Bonfire)
- Laurens Hof
- Ryan Barrett
- Darius Kazemi
- Evan Prodromou
- Johannes Ernst
- Bob Wyman
- Angelo Gladding

## Agenda

Welcome to the SocialWeb Community Group!

1. Code of Ethics & Professional Conduct Reminder:  https://www.w3.org/Consortium/cepc/
2. W3C Community Group Process and Governance: https://www.w3.org/community/about/process/
3. IP Protection Note:
    a. **Anyone can participate in these calls.** However, all substantive contributors to any CG Work Items must be members of the CG with full IPR agreements signed. https://www.w3.org/community/socialcg/join
    b. To contribute to Work Items: ensure you have a W3 account: https://www.w3.org/accounts/request, and sign the W3C Community Contributor License Agreement (CLA):
https://www.w3.org/community/about/agreements/cla/
4. ActivityPub Test Suite Discussion
   - (5-10 min) Presentation by Johannes Ernst on Fediverse Test Suite Requirements and Architecture ([document and slides](https://github.com/fediverse-devnet/testsuite/tree/develop))
   - (5-10 min) Presentation by Bengo about in-progress test suite and behaviors data set
   - (5-10 min) Presentation by Helge on in-progress test suite and Testing the Fediverse resource
   - (5-10 min) Presentation/demo by Darius Kazemi on activitypub-tool
   - (remaining time) Discussion and next steps

## Notes

Evan: Question in terms of scope - when we talk of specs, we have AS2 spec, and AP (which is the protocol & client API). Is the scope primarily about protocol, not data model?

Dmitri: Both are in scope

Evan: I have a test suite for a ref implementation of AP, maybe we can talk about that at the end.

Johannes: [shares slide deck -- linked in the agenda above] Let's talk about reasons for test suites. 1. SWICG wants to know how / how well its standards are implemented. 2. Developers want to know whether they interop with other fediverse apps. 3. A developer is starting out with implementing Fediverse support, wants help with next steps.

When talking about test suites, we should indicate which one of these use cases we're talking about. For example, category 1 is a subset of category 2 (interop requires a lot more specs than the SWICG specs).

Johannes: State of the art today - bits and pieces of test suites, some incomplete testing. Ideally, we could have one automated test framework. Better test coverage across the Fediverse, better DX. A community around a common codebase.

Johannes: [proposed Architecture and DX slide] Go somewhere, clone some repo, have a sample of commands one should be able to run -- single app or interop between two different apps.
So, a set of interop unit tests, powered by app drivers, but also provide a "manual app driver". Over time, we can implement app drivers on docker, other methods.

If you want to help, writeup is at https://github.com/fediverse-devnet/testsuite/
We want your ideas, help evangelize, help find more funding.

Darius: this is all looking good to me -- one thing that I would propose *on top of this* is a view layer on the web along the lines of the Web Platform Tests dashboard: https://wpt.fyi/interop-2023

Evan: Thanks Johannes - question, for somebody who is a new developer, would they create a driver for their own app, and submit it to the suite?

Johannes: a really new developer would just use the manual test driver, that would be simplest.

Dmitri: Thanks! Bengo, you're up next!

Bengo: [Social Behaviors on the Web slides] A test suite can contain many things, one of them being of course a list of behaviors to test, and that's what I want to talk about.
Problem statement - verifying an implementation of a spec/protocol is expensive.
Implementing verifiably conformant social web services is hard. And maintaining is hard.
Assessing candidate solutions -- if I handed you a zip file today and claimed it was a completely finished AP test suite, how would you check my work?
What would you expect it to contain? Which implementations would you expect to pass, which not?

By what mandate should a test suite test things? (especially if there's one common suite)
Should it be textual rules, preference for test suite author, etc..?

What is a test suite? - a collection of test cases, tests a set of behaviors, etc. (Wikipedia entry). So, many components of this: set of behaviors, set of test cases, detailed instructions for how to configure a system to run the suite, pre-reqs and testing strategy.

Proposal: Socially construct test suite components. (kind of the opposite of the last presentation).
We can publish the test suite components on the web itself. Publish early and often, have people follow your work (via an as2:Follow message). Use the social web itself to get feedback. Discuss in an async fashion using social web protocols. Just work on whatever part you want to work on.

Demo: ActivityPub Behaviors https://socialweb.coop/activitypub/behaviors/
(a list of MUST statements from the AP spec). 50 behaviors so far, for the MUST level. Over time, with people's help, we can add the rest of the behaviors (MAY / SHOULD / etc), and add behaviors from FEPs.

If you click on a single behavior - it's addressible via a UUID, it links to where it is on the spec (uses the WebAnnotation data model to select the place in the text). Has a JSON object describing the behavior to test. It's up on codeberg, https://codeberg.org/socialweb.coop/activitypub-behaviors/

What next? Add more behaviors, for each one, think through how to test it as a group. Publish human-readable test cases and strategies. Automated unit tests.
File issues, send me an email if you want to get involved!

Dmitri: Thank you Bengo! Helge up next!

Helge: First thing I want to discuss - this repo I started, https://codeberg.org/helge/fediverse-features which has Gherkin features for the Fediverse.
(Gherkin is an english-like testing DSL). https://cucumber.io/docs/gherkin/ / https://en.wikipedia.org/wiki/Cucumber_(software)#Gherkin_language
Specification by example, describes what one expects from a test. Can be machine-runnable.

For example, here's a test for HTTP Signatures - you specify a public key, then a private key, then you specify what will happen. And now somebody actually implemented this test (aside form me) - here's this Elixir implementation! (they're not on this call tho)

So, Gherkin provides an infrastructure / way to test this. Contributions are welcome! I'm slowly building this up.

Dmitri: Do you have unit tests running those Gherkin objects?

Helge: I have python harness for running those! (off of the Bovine repo)

Evan: this is really cool, I wasn't familiar with Gherkin! Question was -- Bengo had about 50 different statements to cover. (50 MUSTs in the spec). I see four files here, how does it map?

Helge: Basically, in progress, I add tests as I go or think of it.

[demo of NLNet-funded interop test in Python] You pass a various tech elements into a message, send it to Mastodon, see what the result is on the public timeline. (Interesting edge cases for when Mastodon alters/removes unicode, etc. This is what these tests are for!)

Dmitri: Darius, you're up next!

Darius: Brief overview - small AP debugging server on Glitch.
https://tinysubversions.com/notes/activitypub-tool/

This is not a test suite, just a debugging tool, but useful for fediverse devs.
I built it specifically as usable / you don't have to use a command-line, just click buttons & paste text. Very beginner oriented.
It's on Glitch, you can hit the Remix button, fill out the user/password credentials to a given AP server, etc.
[Example of sending an ActivityPub message]
Now I can follow the user I created, see the replies and other messages. Link to a number of payloads (from various implementations), uses those to create mock messages. Creates wrapper objects. And you can see the post on the timeline here.
[being able to mock up generic AP events]

Johannes: I love what I'm seeing here - and there's almost no overlap, which is great! Can we bring these efforts together?

Ryan: Thanks, congrats for everyone who presented here, thank you to the organizers - timely conversations! Two ideas I've seen are very powerful from my development -- first is collecting the behaviors and data independent of code, like Helge and Bengo just talked about! That's hard enough, before even making specific drivers or language implementations. Collecting behaviors, variants, etc. Very helpful.

Darius: yeah! honestly this gist of random objects I copy/pasted in the wild has been as useful to me as anything else
https://gist.github.com/dariusk/e0aa9a0b4229c47dec2bc57cc6bb0994

Ryan: The other thing I've seen that's really powerful -- if we can lower the barrier to running a test suite (for example, against a live server on the internet)

Evan: Having a test suite for our social API was one of SocialWeb WG was one of the charter requirements. The test suite we have, developed by Christine, is very manual. Do we have a requirement / responsibility, as SWICG today in 2023, to have that suite available, or some other test suite available?

Dmitri: Definitely a great question, let's continue this discussion!

Ben Pate: One question to pose, to amplify Evan's question. As much as we can test in an automated fashion, that's best! If that's something I can run locally (without standing up a prod server), that dramatically speeds up the dev process. There's a lot of amazing ideas here, thank you for all these cool tools! If I haven't been here, I wouldn't have known about them, since everyone is working on them in different spots.
Discoverability on the Fediverse is difficult, and this is a prime example.
Can we collect and list these tools in one (or more) place?

Dmitri: Definitely!

Johannes: In the earlier FediForum in March, we also discussed this issue - setting up a single place, group owned, with all these links to projects.

Tim Chambers: https://indieweb.social/@activitypubtestsuite@venera.social

Evan and Dmitri: Also, [TPAC 2023](https://www.w3.org/2023/09/TPAC/) is coming up, a hybrid event (online and in Seville, Spain), let's continue the conversation there too!

Bob Wyman (in chat): How could our SocialWeb protocols be used (or extended) to make this kind of distributed development and testing easier for everyone?

bengo (to Evan, re whether the WG charter applies to SWICG): I think we mostly agree. I think we best steward them by encouraging parallel development of many testing tools, learning from their development, and accepting contributions into the CG, not by developing it in a top-down way in-group, and I don't excpect everyone to agree

Dmitri: Thanks everyone! Let's continue the conversation on our lists / forums!
