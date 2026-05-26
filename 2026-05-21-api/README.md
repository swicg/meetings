# ActivityPub API Taskforce 21 May 2026

## Present

- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- a <trwnh.com>
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- Charles Iliya Krempeaux <acct:reiver@mastodon.social>
- bumblefudge.com
- Django Doucet <acct:django@mediaformat.org>

## Agenda

1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
    a. [movies.pub](https://movies.pub/)
    b. [films.swf.pub](https://films.swf.pub/)
    c. [ActivityPub OAuth example](https://swicg.github.io/activitypub-api/examples/oauth/index.html)
4. Server features #2
5. Scope bonanza #69

## Notes

- Introductions: Charles (Reiver)
- Implementation progress reports
    a. [movies.pub](https://movies.pub/)
    b. [films.swf.pub](https://films.swf.pub/)
    - Reiver: Activity structure?
    - EP: View/Video
    c. [ActivityPub OAuth example](https://swicg.github.io/activitypub-api/examples/oauth/index.html)
    d. MP: Fediverse reader uses social API (!!!!!)
        - Currently used WP
        - Will be released in the next few days
        - Read/write interface (wowowow)
        - bumblefudge: storage problem?
        - MP: it's using storage from WP, live view of the inbox, look up interactions
    e. reiver: Microdon, ProToGo, AssetFlow
         - Microdon
        - Light-weight, General-purpose (not sure) ActivityPub backend separated from UI
        - https://codeberg.org/reiver/microdon
        - Uses an external `inbox` (remote inbox)
            - remote inbox software a separate project
    - ProToGo
        - Career site app (LinkedIn) called ProToGo
        - uses Microdon for backend
        - Resume in JSON-LD, possible FEP (fep-6158)
            - "FEP-6158: ActivityPub 'Resume' Object: JSON Resume expressed as JSON-LD"
        - from JSON-Resume expressed as JSON-LD and reusing ActivityPub vocabulary
    - AssetFlow
        - payments layer for Fediverse and Social Web
        - maybe work with ILF (!) (AssetFlow)
    f.  Django: developing prototype PWA using social API
        - No URL currently
        - EP: add an issue for tracking implementations (clients, servers, libraries, other...?)
        - DD: add Nuages to implementation list
 - Server features
    - "what features do I have to support?"
    - Evan: Add a user story for access to content object collections as well as activities
