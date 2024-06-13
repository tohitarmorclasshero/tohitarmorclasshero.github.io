---
tags:
  - "#Location"
  - "#POI"
art: z_Assets/Misc/PlaceholderImage.png
location:
  - "[[Onyxdale]]"
  - "[[Cherry Loop]]"
organization:
  - "[[Fortunism]]"
poitype:
  - Temple
banner: on
---

```meta-bind-js-view 
{art} as art {banner} as banner
--- 
if (context.bound.art !== "z_Assets/Misc/PlaceholderImage.png" && context.bound.banner === "on")  { 
    const str = ` ![[${context.bound.art}|banner-fade]]` ;
    return engine.markdown.create(str); 
} else { return ""; }
```

> [!metadata|metadata]- Metadata 
>> [!metadata|metadataoption]- System
>> #### System
>>  |
>> ---|---|
> **Tags** | `INPUT[Tags][inlineListSuggester:tags]` |
>
>> [!metadata|metadataoption]- Art
>> #### Art
>>  |
>> ---|---|
> **Art** | `INPUT[imageSuggester(optionQuery("")):art]` |
> **Banner** | `INPUT[toggle(onValue(on), offValue(off)):banner]` |
>
>> [!metadata|metadataoption]- Info
>> #### Info
>>  |
>> ---|---|
>> **Pronounced** |  `INPUT[textArea:pronounced]`
>> **Aliases** | `INPUT[list:aliases]` |
>> **Type** | `INPUT[POIType][inlineListSuggester:poitype]` |
>> **Dominion** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):dominion]` |
>> **Owners** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):owner]` |
>> **Assistant** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):assistant]` |
>> **Organization** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
>> **Location** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |

> [!infobox]+
> # `=this.file.name`
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ###### Info
>  |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Type** | `VIEW[{poitype}][text]` |
> **Dominion** | `VIEW[{dominion}][link]` |
> **Owners** | `VIEW[{owner}][link]` |
> **Assistant** | `VIEW[{assistant}][link]` |
> **Organization** | `VIEW[{organization}][link]` |
> **Location** | `VIEW[{location}][link]` |

# `=this.file.name` <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>
> [!kirk|info] Info (Remove me)
> Point of Interest: A location within your world, anything from a homes, shops, forts, volcanos or dungeons.

> [!recite]- Introduction
> A script for the GM to read when the party arrive to this location for the first time.

> [!metadata|map]- Map
> ```leaflet
> id: TBD
> image: [[PlaceholderImage.png]]
> height: 600px
> width: 640px
> lat: 50
> long: 50
> minZoom: 1
> maxZoom: 5
> defaultZoom: 2
> unit: meters
> scale: 1
> darkMode: false
> ```

> [!metadata|location]- Locations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(poitype, ", ") AS Type, join(link(organization), ", ") AS "Organization(s)"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Location")
> SORT tags DESC, poitype ASC, file.name ASC

> [!metadata|characters]- Characters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(occupation, ", ") AS "Occupations", join(link(organization), ", ") AS "Organizations"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Character") AND !contains(condition, "Dead")
> SORT tags DESC, file.name ASC

## Overview 

> [!kirk|info] Prompt (Remove me)
> Provide an overview encapsulating the essence of this place. What defines its significance? What key events or recurring activities shape its Identity? Explore the heart of this location, capturing its essence in the unfolding pages of history.

## Keyed Locations

> [!kirk|info] Prompt (Remove me)
Create detailed descriptions for each keyed location within the Point Of Interest. Define each room or area with distinct characteristics. Include information on the size, layout, notable features, and potential points of interaction or interest within each location. Describe the ambiance, potential hazards, objects of importance, any interactive elements that might engage the players, or any loot to be found. How does each keyed location contribute to the overall exploration and gameplay experience within this Point of Interest?

### Example


## Current Events

> [!kirk|info] Prompt (Remove me)
> Capture the present pulse within this Point of Interest. What's happening right now in this dynamic location? Are there recent developments, ongoing activities, or sudden changes that have affected the atmosphere? Delve into the current events, integrating them into the fabric of this place. How might these immediate occurrences influence encounters or quests within this Point of Interest or surrounding area, adding depth and intrigue to your players' exploration?

## History

> [!kirk|info] Prompt (Remove me)
> Explore the echoes of history within this location. What significant events have shaped its narrative? Unravel the tales engrained within its grounds, uncovering not just what happened, but also the narratives woven around these events. What stories persist, and are there misconceptions veiling the true essence of these historical moments?

## Notes
### Hidden Details


### Notes

