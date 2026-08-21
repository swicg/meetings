# ActivityPub API Task Force Meeting 20 Aug 2026

## Present

- Ben Pate <@benpate@mastodon.social>
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Bumblefudge (but driving)
- Django Doucet <acct:django@social.coop>

## Agenda

https://github.com/swicg/activitypub-api/issues/82

1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
	    https://www.w3.org/policies/code-of-conduct/#code-of-conduct
2. Introductions
3. Implementation progress reports
4. Basic profile update
    a. https://swicg.github.io/activitypub-api/basicprofile
    b. User stories: #1, #2, #3, #4, #5, #6, #10, #12, #29, #30, #33, #64, #74
    c. What next?
5. Rich Authorization Requests (RAR) #72
    a. Include in Basic Profile?
    b. Separate document?
6. FedID
    a. #81 

Video: https://meet.jit.si/activitypub-api
Time: 16:00 UTC | 11:00 EST | 8:00 PST

To recommend additions or changes to the agenda, please comment below.

## Notes

Evan: noted W3C contributor license agreement, positive work environment rules. Have difficult conversations, be nice. 

### Progress Reports

Django: 
    presented at FOSSY/Fedicon. 
    SeekItem proposal is very helpful in synchronizing activities from server to client.
    demo of Nuages application: web application that uses ActivityPub API
    demo uses a WordPress back end 
    work continues on parsing and classifying activities. For example, home collection and notifications collections aren't mutually exclusive.
    component system built in Preact, DaisyUI for CSS
    
    Evan: WordPress is working on a reader that uses the ActivityPub API
    Bumblefudge: what is the synchronization mechanism? Polling every so often?
    Django: 
        sync is collection traversal. background sync on login. SSE not yet implemented
        also noted ActivityPub C2S toolkit by Steve Bate (https://github.com/steve-bate/activitypub-c2s-toolkit/)

Evan: 
    implementation progress, and demo ofap-components.
    "It's definitely ok"
    WebFinger browser
    Uses lit component library
    Plain JSON parsing of ActivityStreams - which has caused many problems
    Now porting activitystrea.ms library (from 2012, built for NodeJS) to run in a browser as of version 4

### Basic Profile
https://swicg.github.io/activitypub-api/basicprofile

Evan: have we covered the right user stories in this profile? How minimal is minima?
Django: 
    how do we weigh trade-offs of the developer experience? 
    Unwritten assumption is that we're forced to sync everything.  
    Inbox is not a feed. 
    So this forces a "thick client" model.
    Endpoints for Content feed and notification feed
    server-based annotations on feeds (liked, following, muted) would make it easier to developer
    
    Evan:
        this is a bare minimum to sell APAPI to server developers, then level up and improve on the baseline

"Level 1" "More than Basic Profile" "Thin Client"
   - SSE
   - Seekitem
   - Type-ahead search
   - Home/notifications feeds
   - Server annotations
   - "Server-wide feeds" (Federated, Local, ...)
    

Ben: Proposed we write a document that enumerates the specific features for Level 0, Level 1, Level 2.  This would be an index of the existing specs
Evan: The index would point to specific parts of the existing standards documents. 
"Definition of 'Level 1'" - equivalent (?) of the developer experience of a platform like Twitter"
Evan: could we build an equivalent developer experience to ATProto? e.g. Push notifications?
Bumblefudge: referencing meme: draw the rest of the @#$ owl.  We're drawing the rest of the owl here.  Nobody makes a second general client on ATProto. They're making custom extensions and apps that you can sign into using your BSky identity, and sits on the ATProto firehose.
Evan: I don't mind using ATProto, or Twitter2018 as a reference for the developer experience we build.
Ben: Let's model the Mastodon API. They're already doing this.
Evan: There are older standard APIs (e.g. AtomPub) that enabled common blogging clients.
Ben: Micropub is another example.
Evan: for next month, please take a look at the basic profile. What is negotiable?
Evan: one item that came up in E2EE was CORS issue vs. proxyUrl. So how much is required.
Django: it would be hard to survive without proxyUrl.

### OAuth "Rich Authorization Requests" (RARs)
https://github.com/swicg/activitypub-api/issues/72
https://datatracker.ietf.org/doc/html/rfc9396

Evan: 
    RARs are an alternate client authorization mechanism using JSON. 
    It is a much more complex authorization mechanism, with more fine grained permissions for the client.
    RARs fix an anti-pattern in the ATProto exosystem, where too much is packed into the scopes string
    
Bumblefudge:
    The first version of ATProto was very simplistic. Very few nouns and verbs.  
    Level 2 increased the number of available primitives
    What broke down was when there were too many combinations of noun:noun:verb packed into a string.
    RARs are just a JSON syntax for specifying all of this instead of packing everything into a string.
    ATProto regretted to committing to strings when it was simple, then being stuck with strings once it got complicated.
    It can be very difficult to implement arbitrary extensions in strings instead of JSON.
    Strings break everyone's parsers, so ATProto is considering moving to RARs instead.
    For our implementation, "Level 1" would be fine with strings.
    But we'll need RARs when we get to (a hypothetical) "Level 3" with arbitrary extensions.
    
Evan:
    Let's consider RARs as a "Level 1" for detailed control levels.
        
 Meeting Adjourned.
