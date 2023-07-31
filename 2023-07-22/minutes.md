# SWICG Meeting July 22, 2023

## Housekeeping

- Attendance
    - @bumblefudge
    - James (https://jamesg.blog)
    - Tantek Çelik (https://tantek.com/)
    - Ben Savage (Meta)
    - Evan Prodromou
    - David Somers (https://omz13.com)
    - Bob Wyman
    - Manton Reece (https://manton.org)
    - Angelo Gladding (https://ragt.ag)
- Topics
    - Introduction of meeting
    - agenda [here](https://socialhub.activitypub.rocks/t/next-swicg-call-scheduling/3388/3) and [here]()
    - holding a SWICG session at [TPAC](https://www.w3.org/2023/09/TPAC/)? at least a casual meet-up for interested parties?
        - Going: Evan, Tantek, Ben, and Juan (99% sure but depends on a visa)
            - Ben: possible Threads<>Webtech session at TPAC?
        - Remote attendance interest?
    - Issue triage meetings lead by Evan P 
        - Triaging of issues (newer issues first)
    - Discussion of CG outputs versus other modes of working
        - bob: but what's the pressing need? what needs updating?
            - bumble and manton: migration topic!
           
    - Account Migration
        - Manton has a [blog post on the subject](https://www.manton.org/2022/12/02/moving-from-mastodon.html)
        - There is no spec, although there are a few interlocking socialhub threads trying to ideate towards an FEP
        - Implementing it requires investigating what does Mastodon do (see socialhub thread)

    - Features to specification
        - evan: Threads topics not covered by AP spec like limiting replies
        - ben: UX/capability parity with Insta is a driving design goal; that's easy intra-Threads, but figuring out how that works across federation is more difficult...

## Chair Selection/election for SWICG
- Chairs
    - evan: nightpool and aaronpk have said they don't have sufficient bandwidth/time
    - evan: one chair is ok, however more is better, for timezones, to help as a backup for meetings
    - Tantek: Encourages a bias toward implementors in a chair role -- should be actively working with specs, keeps the group grounded
    - tantek: process for volunteering?
    - evan: email to the list, James sent an email
    - james: has experience with some IndieWeb specs (WebSub, IndieAuth, jf2)
    - evan: have you talked to aaron about chairing?
    - james: yes, aaron has noted his inability to keep up with the time commitments for the group. 
    - james: my prior experience does not include CG chairing, looking for mentorship from a previous chair
    - evan: have you talked to dmitri?
    - james: yes, aaron has been talking with dmitri, haven't heard back in a few weeks
    - evan: if you had the help of tantek and dmitri in getting started, the processes aren't overwhelming, and it would be great to have another hand
    - evan: is there anything else that we would need?
    - evan: would love to have a third person in that role too (chair)
    - tantek: agreed, a third would be good
    - juan: might be able to chair, but not sure about time commitment, may know more in the next month
    - juan: haven't run a CG before, have been active in another CG for a year
    - evan: better to have more candidates for chairs than fewer!

## Issue review
- Final 15 minutes dedicated to issue review?
  - Weekly triage for issue queues
    - Presently reviewing https://github.com/w3c/activitystreams/issues?q=is%3Aissue+is%3Aopen+label%3A%22Needs+Group+Input%2FDecision%22
    - Discussion on Issue #440: https://github.com/w3c/activitystreams/issues/440
  - Implementer feedback on issues
    - Evan: Implementers, please see issue with this label: 
https://github.com/w3c/activitystreams/issues?q=is%3Aissue+is%3Aopen+label%3A%22Needs+Group+Input%2FDecision%22
  - ActivityStreams and ActivityPub triage process
    - Evan: what do people think about how this is going?
    - Tantek: grateful for all this work!
    - Comment from Bob in chat: Also, folk **should be watching the additions to the WIki Primers** which is the main output of the triage process: [AP Primer](https://www.w3.org/wiki/ActivityPub/Primer) and [ActivityStreams primer](https://www.w3.org/wiki/Activity_Streams/Primer) are getting more useful every two weeks!
  - Use of GitHub
    - Presentation on GitHub process by Evan
  - Test suite
    - Ben: where is it, how do I participate?
      - Evan: we have two test suites.
        - ActivityPub has server-to-server protocol and client-to-server interface
          - There are at least two projects working to automated test processing both with the Mastodon API and the ActivityPub API
            - https://elk.zone/@activitypubtestsuite@venera.social is one
          - We should get to a point in the next month or two where we have a process for driving a test server and saying the server can be tested against Mastodon, etc.
          - Current state is manual testing -- we want to have a test suite.
            - This has led to a lot of trial and error, skipping over tests if they seem too hard
              - We want automated testing to happen soon
      - Ben: interested in sub-group meetings (special topic calls?) for test suites
        - Evan: should be major part of agenda for next meeting
          - Ben: would like to discuss regularly

## Housekeeping
  - Meeting time
    - Q: from James:
      - Can I propose we move the meeting time back to allow for easier participation of people on the West Coast?
      - Can we also choose a note-taking tool that does not require authentication? (i.e. Etherpad)

## Action Items
- ben: document list of features that Meta would be interested in supporting with ActivityPub (e.g. limiting replies), share with list
