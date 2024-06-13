---
tags:
  - "#Location"
  - "#POI"
art: z_Assets/POIs/Tableau_BearAndBottle.png
pronounced: HAR-vest HARTH
poitype:
  - Shop [Tavern]
location:
  - "[[Kolberdon]]"
  - "[[Gerrict Park]]"
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
> ###### [[Travel Calculator]] 
>  |
> ---|---|
> **TBD** | `VIEW[round(52 / (({Travel Calculator#MilesPerHour}*{Travel Calculator#HoursPerDay})*{Travel Calculator#SpeedMultiplier}),1)]` Day(s)
> **TBD** | `VIEW[round(0.5 / ({Travel Calculator#MilesPerHour} * {Travel Calculator#SpeedMultiplier}) * 60, 1)]` Minute(s)

# `=this.file.name` <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>

> [!recite]- Introduction
> "The dirt road leading into Kolberdon opens up to reveal The Harvest Hearth, a modest tavern nestled at the heart of the simple farming town. As your party approaches, the scent of freshly tilled soil mingles with the aroma of wholesome home-cooked meals wafting from the open windows. The sound of laughter and the occasional clinking of farm tools creates a comforting melody that resonates with the rhythm of rural life. The exterior of The Harvest Hearth is adorned with hanging baskets of vibrant flowers, adding a touch of color to the rustic charm. As the sun sets, casting a warm golden glow on the surrounding fields, the tavern's inviting atmosphere becomes even more apparent.
>
Stepping through the creaking wooden door, your party is welcomed by the comforting crackle of the hearth and the aroma of hearty stews. The interior of The Harvest Hearth is unpretentious, featuring sturdy wooden tables and benches worn smooth by years of use. Simple oil lamps dangle from the ceiling, offering gentle illumination. The large hearth dominates one wall, its flames casting a warm glow over the room. The atmosphere is cozy, inviting patrons to relax and unwind after a day of labor in the surrounding fields."

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

> [!metadata|characters]- Characters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(occupation, ", ") AS "Occupations", join(link(organization), ", ") AS "Organizations"
> FROM "Campaign"
> WHERE econtains(location, this.file.link) AND contains(tags, "Character") AND !contains(condition, "Dead")
> SORT tags DESC, file.name ASC

## Overview 

The Harvest Hearth is a two-story wooden structure with a thatched roof, its exterior adorned with hanging baskets of vibrant flowers. The interior is unpretentious, featuring sturdy wooden tables and benches worn smooth by years of use. A large hearth dominates one wall, its flames casting a warm glow over the room. Simple oil lamps dangle from the ceiling, offering gentle illumination. The atmosphere is cozy, inviting patrons to relax and unwind after a day of labor in the surrounding fields.

### Clientele:

1. Farmer Grizzlefield - Human, Male: A weathered farmer with calloused hands, enjoying a hearty stew after a long day plowing the fields.
2. Mabel Greenleaf - Halfling, Female: The town's herbalist, sipping on a mug of herbal tea while chatting with patrons about the healing properties of local plants.
3. Constable Alden Stone - Dwarf, Male: The town's diligent constable, savoring a simple ale while keeping a watchful eye on the tavern's patrons.
4. Elsie Tanner - Elf, Female: A skilled archer taking a break from hunting in the nearby woods, enjoying a plate of roasted vegetables.
5. Thessa Wheaton - Gnome, Female: A jovial gnome bard strumming a lighthearted tune on a small instrument, lifting the spirits of everyone in the tavern.

### Food & Drink: Food:

1. Farmer's Stew: A wholesome stew made with locally grown vegetables, tender meat, and savory herbs.
2. Plowman's Pie: A hearty pie filled with layers of cheese, cured meats, and freshly baked bread, a favorite among the farming folk.
3. Roasted Root Medley: An assortment of roasted root vegetables seasoned with herbs, a simple yet flavorful side dish.
4. Orchard Apple Crisp: A delightful dessert made with sweet apples from the town's orchards, topped with a crunchy oat crust.
5. Kolberdon Cornbread: A staple of the region, this moist and buttery cornbread is served warm with a dollop of honey.

### Drinks:

1. Harvest Ale: A light and refreshing ale brewed with grains harvested from the surrounding fields, perfect for a relaxing evening.
2. Herbal Infusion: A soothing tea made from locally foraged herbs, known for its calming properties.
3. Orchard Cider: Freshly pressed apple cider from the town's orchards, a crisp and satisfying beverage.
4. Sodbuster's Sip: A concoction of homemade fruit juices and a splash of fizzy water, a popular non-alcoholic choice.
5. Farmer's Finest Whiskey: A locally distilled whiskey with a smooth finish, enjoyed by those seeking a stronger drink.

## Keyed Locations

> [!kirk|info] Prompt (Remove me)
Create detailed descriptions for each keyed location within the Point Of Interest. Define each room or area with distinct characteristics. Include information on the size, layout, notable features, and potential points of interaction or interest within each location. Describe the ambiance, potential hazards, objects of importance, any interactive elements that might engage the players, or any loot to be found. How does each keyed location contribute to the overall exploration and gameplay experience within this Point of Interest?

### Example


## Current Events

The Harvest Hearth is alive with the fervor of the Kolberdon Crop Contest, an annual event that draws farmers from all around the region. The tavern's main room is adorned with vibrant displays of oversized pumpkins, colorful heirloom tomatoes, and meticulously arranged bouquets of wildflowers. The air is filled with friendly competition as farmers discuss the size of their crops and the techniques employed to yield such impressive results.

In one corner, a group of judges, led by the town's elderly botanist, meticulously examines each entry, engaging in spirited debates about soil quality and irrigation methods. The tension is palpable as contestants anxiously await the results, their eyes nervously darting between their fellow competitors and the esteemed panel of judges. Meanwhile, the atmosphere in The Harvest Hearth is charged with excitement, as patrons place friendly bets and cheer for their favourite contenders. The aroma of celebratory dishes, featuring the winning produce from past contests, wafts from the kitchen, creating a delightful backdrop for the agricultural spectacle unfolding within the simple farming town of Kolberdon.

## History

The Harvest Hearth has been a cornerstone of Kolberdon since the town's founding, providing a welcoming space for farmers and residents to gather, share their experiences, and forge connections. Over the years, it has witnessed the growth and challenges of the community, becoming a symbol of unity and resilience in the face of the changing seasons. The walls of the tavern are adorned with handmade tapestries, each telling a story of the town's agricultural heritage and the enduring spirit of its people.

## Notes

