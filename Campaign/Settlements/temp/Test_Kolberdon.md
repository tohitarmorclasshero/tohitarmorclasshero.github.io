---
tags:
  - "#Location"
  - "#Settlement"
art: z_Assets/Settlements/Landscape_Kolberdon.png
pronounced: COL-ber-donn
settlementtype: Small Town
terrain:
  - Farmland
  - Urban
defence: Average
location:
  - "[[Test_Geo]]"
governmenttype:
  - Democracy
population: 9,542
export:
  - Grain
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
>> **Tags** | `INPUT[Tags][inlineListSuggester:tags]` |
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
>> **Type** | `INPUT[SettlementType][:settlementtype]` |
>> **Terrain** | `INPUT[Terrain][inlineListSuggester:terrain]` |
>> **Defences** | `INPUT[Defence][:defence]`
>> **Location** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |
>
>> [!metadata|metadataoption]- Demographics
>> #### Demographics
>>  |
>> ---|---|
>> **Dominion** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):dominion]` |
>> **Rulers** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):ruler]` |
>> **Leaders** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):leader]` |
> **Organizations** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
>> **Government Type** | `INPUT[GovernmentType][inlineListSuggester:governmenttype]` |
>> **Population** |  `INPUT[textArea:population]`
>
>> [!metadata|metadataoption]- Commerce
>> #### Commerce
>>  |
>> ---|---|
>> **Imports** | `INPUT[Goods][inlineListSuggester:import]` |
>> **Exports** | `INPUT[Goods][inlineListSuggester:export]` |

> [!infobox]+
> # `=this.file.name`
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ###### Info
>  |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Type** | `VIEW[{settlementtype}][text]` |
> **Terrain** | `VIEW[{terrain}][text]` |
> **Defences** | `VIEW[{defence}]` |
> **Location** | `VIEW[{location}][link]` |
> ###### Demographics
>  |
> ---|---|
> **Rulers** | `VIEW[{ruler}][link]` |
> **Leaders** | `VIEW[{leader}][link]` |
> **Dominion** | `VIEW[{dominion}][link]` |
> **Government Type** | `VIEW[{governmenttype}][text]` |
> **Population** | `VIEW[{population}][text]` |
> ###### Commerce
>  |
> ---|---|
> **Imports** | `VIEW[{import}][text]` |
> **Exports** | `VIEW[{export}][text]` |
> ###### [[Travel Calculator]] 
>  |
> ---|---|
> **[[Onyxdale]]** | `VIEW[round(45 / (({Travel Calculator#MilesPerHour}*{Travel Calculator#HoursPerDay})*{Travel Calculator#SpeedMultiplier}),1)]` Day(s)

# **`=this.file.name`** <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>
> [!recite]- Introduction
> "The journey through rolling hills and golden fields culminates in the sight of Kolberdon, a simple farming town that stretches lazily along the banks of the winding Utoxton River. As your party approaches, the scent of freshly tilled earth and ripening crops permeates the air. The sun casts a warm glow over the rustic landscape, and the distant sounds of livestock and cheerful chatter indicate the heart of the region's agricultural life. A gentle breeze carries with it the whispers of the fields, and the simple beauty of Kolberdon unfolds before you.
>
Entering the town, the rhythm of daily life becomes apparent. Farmers tend to their crops, plowing fields with diligent care. The marketplace is alive with activity, as vendors proudly display the bounties of the harvest. Simple wooden homes dot the landscape, each surrounded by small plots of vegetables and herb gardens. Children play by the riverbank, their laughter harmonizing with the gentle flow of the Utoxton. Kolberdon exudes a sense of hardworking simplicity, where the connection to the land is evident in every furrowed brow and calloused hand."

> [!metadata|map]- Map
> ```leaflet
> id: Kolberdon
> image: [[Map_kolberdon.png]]
> height: 600px
> width: 640px
> lat: 45
> long: 50
> minZoom: 1
> maxZoom: 5
> defaultZoom: 1
> unit: meters
> scale: 1
> darkMode: false
> ```

> [!metadata|district]- Districts
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(districttype, ", ") AS Type
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "District")
> SORT districttype ASC, file.name ASC

> [!metadata|location]- Locations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(poitype, ", ") AS Type, join(link(location), ", ") AS "Location", join(link(organization), ", ") AS "Organization(s)"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "POI")
> SORT tags DESC, poitype ASC, file.name ASC

> [!metadata|organizations]- Organizations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(organizationtype, ", ") AS Type
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Organization")
> SORT tags DESC, file.name ASC

> [!metadata|characters]- Characters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(occupation, ", ") AS "Occupations", join(link(organization), ", ") AS "Organizations"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Character") AND !contains(condition, "Dead")
> SORT tags DESC, file.name ASC

## Overview

Kolberdon is a vital farming town, supplying the region with the majority of its food. The town is surrounded by expansive fields of wheat, barley, and various vegetables, creating a patchwork quilt of vibrant colors during the growing season. The Utoxton River not only provides a steady water source for irrigation but also serves as a natural boundary, enhancing the town's picturesque setting. Wooden windmills dot the landscape, harnessing the river's energy to grind grains and power simple machinery. The heart of Kolberdon is its communal spirit, with the townsfolk relying on each other to weather the challenges of farming life.

## Current Events

[[Good Crop Bad Crop]] - A mysterious blight has begun to spread through the once-thriving fields surrounding Kolberdon, threatening the town's primary source of sustenance. Crops wither and die, their leaves turning a sickly shade of black. Desperation hangs in the air as farmers struggle to contain the blight, but their efforts seem futile against this unnatural affliction. The marketplace, once bustling with the vibrancy of fresh produce, now stands eerily quiet, its stalls empty and its people anxious. The townsfolk are urgently seeking the aid of adventurers to investigate the origin of the blight, discover a cure, and save Kolberdon from the impending famine.

## History

Kolberdon's history is deeply rooted in the agricultural traditions of the region. Founded by a group of settlers seeking fertile land, the town has flourished over the years, adapting to changing seasons and weather patterns. The resilience of the townsfolk has been tested by various challenges, from harsh winters to occasional raids by bandits seeking to exploit the town's resources. Despite these hardships, Kolberdon stands as a testament to the enduring spirit of those who toil the land, providing sustenance for the entire region and fostering a sense of unity among its residents.

## Notes

