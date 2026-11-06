# ActivityPub HTML Discovery 21 Oct 2026

## Present

- Evan Prodromou acct:evanprodromou@socialwebfoundation.org
- a <trwnh.com>

## Agenda

Introductions/administrative

1. Administrative
    a. [W3C Community Contributor License Agreement (CLA)](https://www.w3.org/community/about/process/cla/)
    b. [Positive Work Environment](https://www.w3.org/about/positive-work-environment/)
2. Introductions
3. Implementation progress reports
4. "ActivityPub object", "ActivityPub actor" https://github.com/swicg/activitypub-html-discovery/issues/60
5. rel=alternate https://github.com/swicg/activitypub-html-discovery/issues/48
6. Other progress

Jitsi: https://meet.jit.si/activitypub-html-discovery
Time: 19:00 UTC | 14:00 EST | 11:00 PST

Add comments below to modify or add to the agenda.

## Notes

- CoC and CLA

- Introductions

- Implementation progress reports
   - EP: ActivityPub browser extension https://github.com/social-web-foundation/activitypub-browser-extension
   - EP: Did jekyll-activitypub-static implementation without adding discovery <link> elements or others

- https://github.com/swicg/activitypub-html-discovery/issues/60

Is "ActivityPub object" still the right term?

```json
{
    "@context": "https://www.w3.org/ns/activitystreams",
    "id": "https://place.example/collection",
    "type": "Collection",
    "items": [
        {
            "type": "Place",
           "name": "France",
"id": "https://place.example/collection#place1"
        },
        {
            "type": "Place",
           "name": "Antarctica",
"id": "https://place.example/collection#place2"
        },
        {
            "type": "Place",
            "name": "Texas",
"id": "https://place.example/collection#place3"
"url": {
                           "type": "Link",
                           "href": "https://someother.example/texas.html"
}
        }
    ]
}
```

https://someother.example/texas.html

```html
<html>
<head>
<title>Texas</title>
<link rel="alternate" href="https://place.example/collection#place3" />
</head>
<body>
<h1>Texas</h1>
</body>
</html>
```


