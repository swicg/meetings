# 2026-09-10 Geosocial Task Force Meeting

## Present

- Evan Prodromou, <acct:evanprodromou@socialwebfoundation.org>
- Jeremiah Lee, <acct:Jeremiah@alpaca.gold> (he|they)
- Mike Waggoner https://herebox.org/
- [Ted Thibodeau Jr](https://www.linkedin.com/in/TallTed/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)

## Agenda

- Mike: Recap of July meeting
- Jeremiah: Any insight on [Pixelfed Places](https://mastodon.social/@dansup/117246534064279647)?
- Evan: Update on using tags.pub for geosocial data
- Ted: (someday) [Open Issues, dating back to Dec 2024](https://github.com/swicg/geosocial/issues?q=is%3Aissue%20state%3Aopen%20sort%3Aupdated-asc)

## Notes

- Mike: Recap of 2026-07-09 meeting
    - Interest from Terence on the hashtag / microsyntax concept as a bridge to more structured data
    - Agreement on direction
    - Terence has a custom workflow for his Swarm check-ins https://mastodon.social/@Edent/116730711941462905

- Jeremiah: Saw [post](https://mastodon.social/@dansup/117246534064279647), anyone have information on how it's working?
    - Specifically, how to invoke the [MaxMind Geo Cities database](https://www.maxmind.com/en/home)? API? Hosted on instance? Is it going generic to a city or a specific place in a city?
    - Seems to abstract EXIF precise location to generic location
    - Evan: Location is clickable, maybe there is an aggregation page if signed in?
    - Jeremiah: Also has a hashtag, is it manual or added automatically?

- Evan: Update on using tags.pub for geosocial data
    - Previous discussion about using hashtag
    - 600k hashtags used in the fediverse since Feb 2026. 150k monthly active uses.
    - Asked himself: Could the tags be used for geographic aggregation?
    - Extracted Canadian cities from (which?) database and then compared for exact name matches to hashtags. Got 769 matching tags. Canada has ~1000 cities. About 75%!
    - Many duplicated city names. Only about 10% of city names are globally unique. (Montreal exists in CA, FR, US(WI)). Then, focused on Canadian cities that are the largest city with their name and found that there were 664 cities.
        - Mike: Fun data set for duplicate city names globally https://www.geodatos.net/en/homonymous-cities
    - London, Ontario has multiple hashtags commonly used. Searched for #LondonON, #LondonOntario, #LondonCanada
    - 69 three-letter airport code hits. Many start with Y and many are unique strings that do not likely have other uses besides airport codes. ETA, MOY as an example of an ambiguous use.
    - Seems to have enough data to do a data visualization on a map with reasonable degree of confidence with Canadian map with unambiguous name or with provence name
    - Next step is putting together a rule set and a visualization of post as they happen in real time on a map using this data
    - Curious to see if people's behavior changes once there is a visualization. Will people want to use a specific tag in order for it appear in the visualization / aggregation?
    - Need to find a way to visualize it on a map
        - Jeremiah: I've used https://globe.gl/ and it has an extensive API
    - Mike: Has observed people in places with an ambiguous name have come up with unambiguous ways to tag / self-organize use of an identifier
        - Evan: #LondonKY because [London, Kentucky, US](https://en.wikipedia.org/wiki/London,_Kentucky) is a place.
    - Evan: Another hashtag sorting to expand to would be when the name is combined, example of #LondonCulture
    - Evan: Other languages have different names like Londres

- Ted: What about all the open issues? How are they being addressed and resolved?
    - Jeremiah: Will take on clean up task to update to link to what's been covered in the explainer doc

- Evan: Other community groups are doing community group reports. The only official publications that can be done as this type of group.
    - https://www.w3.org/community/socialcg/
    - Is there a publication we should be brining out of this task force? Not a required thing.
    - E2EE and HTML Discovery task forces are working on a report
    - Jeremiah: Is this different from the explainer doc?
        - Evan: Report is more prescriptive, more along the lines of a specification
        - Evan: If we have things that we work on in the group, such as the microsyntax document or places API, that could be interesting publishing.
    - Mike: Will review the other reports to see if this is makes sense for us

- Evan: Another idea for a potential output: providing a rule set for mapping tags to cities, take the learnings from the project and sharing them

- Jeremiah: Will submit pull request with the meeting notes: https://github.com/swicg/meetings

- Next: Fediforum: Oct 6–7, https://fediforum.org/

## Action items

- Jeremiah: Will update open issues with references to explainer
- Mike: Will review other task force reports
