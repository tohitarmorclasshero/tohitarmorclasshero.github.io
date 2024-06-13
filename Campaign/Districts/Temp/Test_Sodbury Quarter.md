---
tags:
  - "#Location"
  - "#District"
art: z_Assets/Misc/PlaceholderImage.png
pronounced: SOD-bury QUAR-ter
districttype:
  - Residential
  - Agricultural
location:
  - "[[Kolberdon]]"
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
> **Pronounced** |  `INPUT[textArea:pronounced]`
> **Aliases** | `INPUT[list:aliases]` |
> **Type** | `INPUT[DistrictType][inlineListSuggester:districttype]` |
> **Organizations** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
> **Location** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |

> [!infobox]+
> # `=this.file.name`
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ###### Info
>  |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Type** | `VIEW[{districttype}][text]` |
> **Location** | `VIEW[{location}][link]` |

# **`=this.file.name`** <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>

> [!recite]- Introduction
> "As you enter Sodbury Quarter, a symphony of lively sounds fills the air – the clinking of tankards at the local tavern, the laughter of children playing nearby, and the occasional bleat of sheep from a nearby pasture. The aroma of freshly baked bread mingles with the earthy scent of the surrounding farmland, creating a wholesome atmosphere that welcomes visitors to this quaint area."

> [!metadata|map]- Map
> ```leaflet
> id: SodBuryQuarter
> image: [[Map_SodburyQuarter.png]]
> height: 600px
> width: 640px
> lat: 50
> long: 50
> minZoom: 1
> maxZoom: 5
> defaultZoom: 1
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

> [!metadata|organizations]- Organizations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(organizationtype, ", ") AS Type
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Organization")
> SORT tags DESC, file.name ASC

## Overview 

Sodbury Quarter, nestled in the gentle embrace of Kolberdon, is the beating heart of the town's agricultural life. This primarily residential district caters to the hardworking lower class, where modest cottages dot the landscape alongside small family farms. The scent of freshly plowed earth and the distant lowing of cattle permeate the air, creating a warm and rustic atmosphere.

## Keyed Locations

1. **Harvest Haven:** A communal gathering space at the center of Sodbury Quarter, where farmers come together to share stories, trade produce, and organize community events. During harvest festivals, this area transforms into a lively fairground with games and food stalls.
2. **Tiller's Rest Inn:** A cozy inn known for its affordable lodgings and hearty, home-cooked meals. Many travelers passing through Kolberdon choose to stay here, immersing themselves in the simple pleasures of the farming life.
3. **Green Acres Market:** A bustling marketplace where local farmers set up stalls to sell their fresh produce, handmade crafts, and dairy products. It's a hub of activity during market days, creating a sense of camaraderie among the residents.


## Current Events

The recent onset of a harsh blight has affected the crops in Sodbury Quarter, leading to a decline in yields and increased financial strain on the residents. The community is rallying together to find innovative solutions, from sharing resources to organizing a cooperative effort to combat the blight. The local herbalist is rumored to possess a remedy, but tensions rise as supplies run low.

## History

Originally established as a humble farming settlement, Sodbury Quarter grew alongside Kolberdon, its residents contributing to the town's prosperity through hard work and dedication to the land. Over the years, the district has weathered various challenges, from unpredictable weather patterns to occasional raids from marauding creatures. Despite these hardships, the resilient community has always managed to bounce back, creating a tight-knit and supportive environment that defines the essence of Sodbury Quarter.

## Notes

