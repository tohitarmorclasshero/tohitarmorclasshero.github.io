---
tags:
  - "#Location"
  - "#Settlement"
art: z_Assets/Settlements/Flag_Onyxdale.png
pronounced: ON-ICKS-dayle
settlementtype: Large Town
terrain:
  - Urban
  - River
defence: Strong
location:
  - "[[Test_Geo]]"
population: 12,634
export:
  - Onyx
  - Stone
  - Iron
  - Coal
  - Weapons
governmenttype:
  - Democracy
ruler:
  - "[[Anmera Geldeck]]"
leader:
  - "[[Dyrek Revenmar]]"
organization:
  - "[[Onyxdale Guards]]"
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
> **[[Kamderah]]** | `VIEW[round(52 / (({Travel Calculator#MilesPerHour}*{Travel Calculator#HoursPerDay})*{Travel Calculator#SpeedMultiplier}),1)]` Day(s)
> **[[Kolberdon]]** | `VIEW[round(45 / (({Travel Calculator#MilesPerHour}*{Travel Calculator#HoursPerDay})*{Travel Calculator#SpeedMultiplier}),1)]` Day(s)

# **`=this.file.name`** <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>
> [!recite]- Introduction
As the players approach Onyxdale, they first see the town nestled in a valley surrounded by high, rocky cliffs. The cliffs are dotted with several mines, from which black onyx is extracted and processed. The mines give the town its name, and the players can see miners coming and going from the entrances, carrying heavy loads of ore.
>
The air is filled with the sounds of hammers and pickaxes echoing from the mines, as well as the calls of birds of prey that soar overhead. The players can also smell the pungent scent of smoke and ash, as the town's many forges work to process the onyx into usable materials.
>
**Entering Onyxdale:**
As the players enter Onyxdale, they find themselves on a wide cobblestone street that runs through the center of town. The buildings are sturdy, made of stone and wood, and many of them are adorned with intricate carvings of onyx. The town is bustling with activity, as merchants and tradespeople go about their business and citizens hurry from place to place.
>
The town square is a lively hub of activity, with vendors selling their wares and people gathered to talk and trade. In the center of the square is a tall statue of the town's founder, a miner who discovered the onyx deposits and established the town.
>
The players can see several important buildings as they look around the town square. There is a large temple dedicated to Moradin, the dwarven god of creation and patron of miners and craftsmen. There is also a well-guarded blacksmith's forge, where the town's master smiths work to create intricate and beautiful objects from the onyx.
>
The players can also see a group of rough-looking miners gathered in a corner of the square, talking and laughing. They are covered in soot and have the look of hard workers who have seen their fair share of danger.
>
**Smells:**
As the players move through Onyxdale, they will be hit with a mixture of different scents. The first thing they'll likely smell is the acrid odor of smoke from the forges and kilns, mixed with the scent of hot metal and ashes. There's also the earthy smell of the mines, with a hint of sulfur, as well as the more pleasant scents of fresh-baked bread, roasting meats, and sweet pastries from the town's bakeries and taverns.

> [!metadata|map]- Map
> ```leaflet
> id: Onyxdale
> image: [[Map_Onyxdale.png]]
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

> [!kirk|info] Prompt (Remove me)
> Craft an overarching depiction of this settlement's essence. Explore its layout, cultural diversity, prominent landmarks, and economic activities. Highlight the unique features that define this place, portraying its societal dynamics and significance within the region. What makes this settlement stand out, and how do its characteristics contribute to its identity in the broader context of the region?

## Current Events

> [!kirk|info] Prompt (Remove me)
> Zoom into the present pulse of life within this settlement. What current events are shaping the daily life of its inhabitants? Explore the recent developments, ongoing activities, or societal changes that are influencing the atmosphere here. Dive into the immediate concerns, celebrations, or challenges faced by the residents. How are these current events impacting the dynamics and future trajectory of this settlement?

## History

### Rebellion

The town of Onyxdale was founded about a century ago by a group of dwarves who discovered a rich vein of black onyx in the surrounding hills. The dwarves saw the potential of the onyx as a valuable material for crafting, and they set about establishing a settlement to mine and process the ore.

At first, the town was small and isolated, with just a few hardy pioneers. But as word of the onyx spread, more and more miners and tradespeople arrived, and the town grew into a bustling community.

One of the early leaders of the town was a dwarf named [[Grimnar Stonehear]], who is remembered as the town's founder. Grimnar was a skilled miner and blacksmith, and he used his knowledge and cunning to ensure that Onyxdale prospered. Under his leadership, the town became a major center of onyx production, and the mines produced more and more of the valuable material.

As the town grew, so did its influence. The dwarves of Onyxdale established trade relationships with nearby cities and towns, and the onyx became highly prized for its beauty and durability. The town also became a religious center, as the dwarves built a large temple to [[Test_God]], their patron deity. The priests of [[Test_God]] presided over the mines and the town, and their blessings were said to ensure safe and productive mining.

Despite its success, Onyxdale has faced its share of challenges over the years. There have been cave-ins and other dangers in the mines, as well as a very recent conflict where many of it's streets were used as battleground during in [[Odinys Rebellion]]. But the dwarves of Onyxdale have always been a hardy and resilient people, and they have persevered through adversity.

Today, Onyxdale is a thriving town, with a bustling economy, a rich cultural heritage, and a close-knit community. Many of it's streets have been postly repaired from [[Odinys Rebellion]], but some still lay in disaray. The onyx mines continue to produce high-quality material, and the town's blacksmiths are renowned for their skill and craftsmanship. The temple of [[Test_God]] is a major center of worship and learning, and the town's citizens are proud of their heritage and the history of their town.

### **Sika the Onyx Serpent**

100 years ago the Solvant Lagoon was once home to a massive black water serpent that terrorized the local villages and fishermen. The creature was said to be over 100 feet long, with a body as thick as a great tree trunk, and eyes that glowed like embers in the dark.

Many fishermen claimed to have seen the serpent swimming in the lagoon, and some even reported that it had attacked their boats, dragging them underwater and devouring the crew. The serpent was said to be so fearsome that it was able to swallow whole whales and dolphins without breaking a sweat.

The villagers were so afraid of the serpent that they began making offerings to it, hoping to appease its wrath and prevent it from attacking their boats. Some even believed that the serpent was a god, sent to punish them for their sins.

Eventually, a group of brave warriors and hunters banded together to slay the serpent. They crafted a massive harpoon out of the strongest wood and sharpened it to a razor edge. Then, they lured the serpent into shallow waters, where it was easier to attack.

The battle was long and grueling, with the serpent thrashing and lashing out at its attackers. But in the end, the warriors were victorious, plunging the harpoon into the serpent's heart and killing it.

To this day, fishermen in the Tolnan Lagoon still tell stories of the black water serpent and the brave warriors who defeated it. Some even claim that the serpent's ghost still haunts the lagoon, seeking revenge on those who dare to disturb its resting place.

Sika's Skull can be found in the [[Jarl's Hall (Onyxdale)]] and Sika image is used on the Coat of Arms to this day.


Plot: Players will need to find clues on how to draw out the beast. One clue os every year of celebration of when Sika fell, they light fireworks to celebrate. Along with other holidays. However, other loud noises and a lot could also do the lidays. However, other loud noises and a lot could also do the trick.

[[Phelia Malgil]] 

Muror - Catfolk

Vres Keens - Halfling]

Ennet Dodd - Drow

[[Olden Khemmid]] - Presumed dead during the fight

## Notes
### Hidden Details


### General Notes

