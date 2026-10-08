# Geosocial Task Force, 2025-03-13

## Present

- Dmitri Z.
- Evan Prodromou <acct:evan@cosocial.ca>
- Jeremiah Lee [@Jeremiah@alpaca.gold](https://alpaca.gold/@Jeremiah) (he|they)
- Mike Waggoner <acct:mike@herebox.org>
- [TallTed // Ted Thibodeau](https://github.com/TallTed/) (he/him) (OpenLinkSw.com) (https://mastodon.social/@TallTed)

## Agenda

- Any update from Mike from [last meeting](https://hedgedoc.socialweb.coop/s/D7yKLjJQs)?
- FediForum plan?
- places.pub update

## Minutes

- Mike will put his draft into Hedgedoc
    - Jeremiah and Evan will also start contributing
- Mike: Fediforum: any ideas for a session?
- Mike: Any major fediverse updates since he's been off the grid?
    - Evan: Mastodon announced it will start pulling the replies collection from remote servers. Could mean to pulling in more information, such as location. It previously had been averse about pulling data. ActivityPub is a push/pull. Exciting to see that happening.
    - Evan: Quote posts advances coming soon in Mastodon.
    - Jeremiah: Frequency of Mastodon releases increasing.
- Evan: Live, querably location ids of place objects needed.
    - places.pub: resurrecting 7 year old project!
    - Each place has a URL
    - Supported search
    - Required having a full copy of Open Street Maps database and its search service. That's hundreds of dollars a month! So shut it down.
    - Started setting up PostgreSQL db and trying to revive, but realized it was on the same expensive path.
    - Instead of setting up full PgSQL with LiveQuery and API endpoint, generate the place objects dynamically and statically, use S3 for inexpensive hosting. Planet OSM is 150 GB of data in OSM, $0.02/gb so $3/month instead of $500/month!
    - This approach requires more pre-processing.
    - You can do bounding box exports of Planet OSM data. It has node objects in XML. Some have metadata that's useful, what we would expect to see for a place.
    - Created a Python script to extract the metadata for each node, convert to Activity Streams format, saves to a file. Skipped nodes without metadata.
    - Then used AWS S3 CLI to sync data to an S3 bucket
    - https://places-pub.s3.us-east-1.amazonaws.com/n5639305723.jsonld
    - Meaning: we can have an inexpensive db of queryable locations!
    - Next steps:
        - mapping `places.pub` to the S3 bucket domain
        - Do the full 150 GB for places in the Planet OSM db
        - Get it up on S3 and get it done
        - Add search: name based search and bounding box search
            - Radius search would be nice, but harder
            - Will try AWS ElasticSearch and Lambda to keep it as inexpensive as possible
        - This should be enough to kickstart uses
        - Add an incremental import via the OSM changesets as a first taxonomy
    - Next next: Talk to OSM about using their domain name for this, like social.openstreetmap.org since it's their data.
    - Dmitri: if they operate it, they could then just expose the data directly without having to process it as an optimization.

## Action items

- Draft of the explainer: https://hedgedoc.socialweb.coop/kUPvzmd4SjyN1oGxyrzskQ#
