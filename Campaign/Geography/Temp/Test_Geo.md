---
tags:
  - "#Location"
  - "#Geography"
art: z_Assets/Geography/Landscape_Odinys.png
banner: on
location:
  - "[[Test_Planet]]"
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
> **Pronounced** |  `INPUT[textArea:pronounced]`
> **Aliases** | `INPUT[list:aliases]` |
> **Terrain** | `INPUT[Terrain][inlineListSuggester:terrain]` |
> **Dominion** | `INPUT[inlineListSuggester(optionQuery(#Character OR #Organization AND !"z_Templates"), useLinks(partial)):dominion]` |
> **Organizations** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
> **Location** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |

> [!infobox]+
> # `=this.file.name`
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ###### Info
>  |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Terrain** | `VIEW[{terrain}][text]` |
> **Dominion** | `VIEW[{dominion}][link]` |
> **Location** | `VIEW[{location}][link]` |

# **`=this.file.name`** <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>

> [!metadata|map]- Map
> ```leaflet
> 
> 
> id: Odinys
> 
> ### Lock pins so they can't be moved
> lock: true
> 
> ### If true, view of map will recenter as you zoom out. 
> recenter: true
> 
> ### If true, disables mouse scroll for zomming in and out of a map. Button controls still work. 
> noScrollZoom: false
> 
> image: [[Map_Odinys.png]]
> 
> ### Map Pixel Height x 1 / (Pixels between Bar Scale / 100)
> ### Map Pixel Width x 1 / (Pixels between Bar Scale / 100) 
> ### Note that this formula requires adjustments depending on your map. The idea is to determine the number of units between your bar scale. We divide by 100 here because my bar scale measures in 100 units. If your maps scale bar measures in units of 50 them you should divide by 50 instead. The idea is to calculate how many pixels are equal to 1 unit. 
> 
> bounds: [[0,0], [221.92, 330.18]]
>
> ### Use this [LINK](https://docs.google.com/spreadsheets/d/1jKQxktYSUFcCJhEkAAPr1wMVBTqUdpEfA5XveUXI17I/edit?usp=sharing) to work out your map's bounds.
>
> height: 600px
> 
> width: 640px
>
> ### This sets where the map starts by default. Set it to the middle (half) of your bounds. 
> lat: 110.96
>
> long: 330.18
>
> ### 0 is no zoom. Negative zoom steps away from the map. Positive zoom steps towards the map. 
> minZoom: 1
> 
> ### Max zoom is 18. 
> 
> maxZoom: 6.5
> 
> ### Hover mouse over the Reset Zoom icon to see your current zoom level. 
> 
> defaultZoom: 1
> 
> ### How far it zooms in or out with each step. Can be in decimals. 
>
> zoomDelta: 0.5
> 
> ### This is a string so can be any text. Change it to match your maps measurement scale. 
> 
> unit: miles
>
> scale: 1
>
> darkMode: false
>
> ```

> [!metadata|county]- Counties
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "County")
> SORT nation ASC, file.name ASC

> [!metadata|settlements]- Settlements
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, settlementtype AS Type, defence AS Defences, join(link(dominion), ", ") AS "Dominion"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Settlement")
> SORT nation ASC, file.name ASC

> [!metadata|location]- Locations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(poitype, ", ") AS Type, join(link(organization), ", ") AS "Organization(s)", join(link(dominion), ", ") AS "Dominion"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "POI")
> SORT tags DESC, poitype ASC, file.name ASC

> [!metadata|organizations]- Organizations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(organizationtype, ", ") AS Type
> FROM "Campaign"
> WHERE contains(location, this.file.link) AND contains(tags, "Organization")
> SORT organizationtype ASC, file.name ASC

> [!metadata|characters]- Characters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(occupation, ", ") AS "Occupations", join(link(organization), ", ") AS "Organizations"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Character") AND !contains(condition, "Dead")
> SORT tags DESC, file.name ASC

## Overview 

> [!kirk|info] Prompt (Remove me)
> Create an overview that encapsulates the spirit and character of this region. Explore its cultural diversity, geographical landmarks, societal values, and any defining aspects that contribute to its identity. What makes this region unique and distinct from others? Paint a vivid picture that captures the essence and allure of this land.

## Current Events

> [!kirk|info] Prompt (Remove me)
> Capture the pulse of the present moment by examining current events. Dive into the ongoing occurrences, societal shifts, or global happenings that are shaping the world today. Analyze the trends, controversies, or innovations unfolding in real-time. What stories are making headlines, and how might these current events influence the future trajectory of the society?

## History

> [!kirk|info] Prompt (Remove me)
> Delve into the historical legacy of the inhabitants of this region. Explore the diverse cultures, migrations, and societal developments that have shaped the people's identity and contributed to the region's tapestry. Investigate the stories of resilience, innovations, and cultural amalgamations that reflect the rich history within this region. How have the people's experiences and interactions shaped the course of this region's history?

## Notes
### Hidden Details


### General Notes

