---
tags:
  - "#Hub"
---


![[HubBackground.png|banner-fade]]

# <center>**Vault Hub**</center>

> [!metadata|party] Parties
>> [!cards|dataview 5] **Party**
>> ```dataview
>> TABLE WITHOUT ID
>> "<span style='display: block; text-align: center; margin-bottom: 5px;'>" + link(file.link, Title) + "</span>" AS Title,
>> embed(link(art)) AS "Art"
> FROM !"z_Templates"
>> WHERE contains(tags, "Party")
>> SORT file.name asc
>> ```

## Quick References

> [!metadata|metadataoption]- Quick References
> #### Quick References
>  |
> ---|---|
> **Character** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):characters]` |
> **Locations** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates")):locations]` |
> **Miscellaneous** | `INPUT[inlineListSuggester(optionQuery("" AND !"z_Templates")):misc]` |

> [!column|3 no-title]
>> [!metadata|characters] People
>> `VIEW[{characters}][link]`
>
>> [!metadata|location] Locations
>> `VIEW[{locations}][link]`
>
>> [!metadata|misc] Misc
>> `VIEW[{misc}][link]`

## Calendar

> [!metadata|calendar] Calendar
> ```calendarium
> ```

## Dataviews

> [!metadata|plane]- Planes
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion", join(link(location), ", ") AS "Location"
> FROM "Campaign"
> WHERE contains(tags, "Existence")
> SORT dominion ASC, file.name ASC

> [!metadata|planet]- Planets
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion", join(link(location), ", ") AS "Location"
> FROM "Campaign"
> WHERE contains(tags, "Planet")
> SORT dominion ASC, file.name ASC

> [!metadata|geography]- Geography
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion", join(link(location), ", ") AS "Location"
> FROM "Campaign"
> WHERE contains(tags, "Geography")
> SORT dominion ASC, file.name ASC

> [!metadata|county]- County
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion", join(link(location), ", ") AS "Locations"
> FROM "Campaign"
> WHERE contains(tags, "County")
> SORT dominion ASC, file.name ASC

> [!metadata|settlements]- Settlements
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, settlementtype AS Type, defence AS Defences, join(link(dominion), ", ") AS "Dominion", join(link(location), ", ") AS "Locations"
> FROM "Campaign"
> WHERE contains(tags, "Settlement")
> SORT dominion ASC, file.name ASC

> [!metadata|district]- Districts
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(districttype, ", ") AS Type, join(link(location), ", ") AS "Location"
> FROM "Campaign"
> WHERE contains(tags, "District")
> SORT districttype ASC, file.name ASC

> [!metadata|location]- Locations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(poitype, ", ") AS Type, join(link(organization), ", ") AS "Organization(s)", join(link(location), ", ") AS "Locations"
> FROM "Campaign"
> WHERE contains(tags, "POI")
> SORT poitype ASC, file.name ASC

> [!metadata|organizations]- Organizations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(organizationtype, ", ") AS Type, hq AS HQ
> FROM "Campaign"
> WHERE contains(tags, "Organization")
> SORT organizationtype ASC, file.name ASC

> [!metadata|characters]- Characters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(occupation, ", ") AS "Occupations", join(link(organization), ", ") AS "Organizations", join(link(location), ", ") AS "Locations"
> FROM "Campaign"
> WHERE contains(tags, "Character")
> SORT tags DESC, file.name ASC

> [!metadata|servicerequests]- Service Requests
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE contains(tags, "Service")
> SORT file.name ASC

> [!metadata|letters]- Letters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE contains(tags, "Letter")
> SORT file.name ASC

> [!metadata|literature]- Literature
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE contains(tags, "Literature")
> SORT file.name ASC


## Ideas

> [!metadata|items]- Items
> ```dataview
> TABLE
> FROM "Ideas/Items"
> SORT file.name ASC

> [!metadata|jokes]- Jokes
> ```dataview
> TABLE
> FROM "Ideas/Jokes"
> SORT file.name ASC

> [!metadata|location]- Locations
> ```dataview
> TABLE
> FROM "Ideas/Locations"
> SORT file.name ASC

> [!metadata|quests]- Quests / Adventures
> ```dataview
> TABLE
> FROM "Ideas/Quests"
> SORT file.name ASC

## Random Notes
> [!cards|dataview 7]
> ```dataview
> TABLE WITHOUT ID
> "<span style='display: block; text-align: center; margin-bottom: 2px;'>" + link(file.link, Aliases) + "</span>" AS Aliases,
> embed(link(art)) AS "Art"
> FROM "Campaign"
> FLATTEN [ [(seed) => (seed * 1103515245 + 12345) % 2147483648]] AS random
> FLATTEN [number(dateformat(date("now"), "x"))] AS seed
> SORT random[0](seed + file.size)
> LIMIT 14



