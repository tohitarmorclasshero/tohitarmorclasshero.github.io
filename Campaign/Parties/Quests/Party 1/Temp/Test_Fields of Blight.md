---
tags:
  - Quest
art: z_Assets/Misc/PlaceholderImage.png
adventure: "[[Good Crop Bad Crop]]"
---

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
>> **Art** | `INPUT[imageSuggester(optionQuery("")):art]` |
>
>> [!metadata|metadataoption]- Info
>> #### Info
>>  |
>> ---|---|
>> **Aliases** | `INPUT[list:aliases]` |
>> **Quick Notes** |  `INPUT[textArea:quicknote]`
>> **Adventure** | `INPUT[Null][suggester(optionQuery(#Adventure AND !"z_Templates"), useLinks(partial)):adventure]` |
>> **Status** | `INPUT[Status][:status]` |

> [!infobox]
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> #### Quest Info
>  |
> ---|---|
> **Adventure** | `VIEW[{adventure}][link]` |
> **Status** | `VIEW[{status}]` |

# **`=this.file.name`** 

## Overview
### Summary

The thriving farming town of Kolberdon faces a dire threat as a mysterious blight consumes its fields, jeopardizing the annual harvest festival. Investigate the source of the blight, unravel the connection to a tear in the fabric of the shadow realm, and prevent the impending disaster.

### Storyline

Kolberdon's prosperity relies on its bountiful harvest, and the upcoming festival is crucial for both trade and community morale. As the party delves into the investigation, they discover that a tear in the shadow realm has allowed malevolent forces to seep into the fields, corrupting crops and spreading a blight that resists conventional remedies. The party must close the tear, uncovering the shadowy entities responsible and saving the town from impending famine.

### Inciting Action

Distressed farmers and town officials seek the party's help as the blight rapidly destroys crops. The party may also witness strange occurrences in the fields, such as shadowy figures or eerie whispers, prompting them to investigate further.

### Resolution

- Success: The party identifies the tear in the shadow realm, confronts the entities responsible, and successfully closes the portal. The corrupted crops are healed, and the town can celebrate the harvest festival without fear. The party gains the gratitude of the town and may receive valuable rewards.
- Partial Success: The party manages to close the tear, but some lingering effects remain. While the harvest festival can proceed, the town faces a period of recovery, and rumors of otherworldly threats persist, setting the stage for future adventures.
- Failure: The party fails to close the tear in time, and the shadowy entities gain a stronger foothold. The harvest festival is canceled, and Odinys faces a severe food shortage. The party may need to help the town cope with the aftermath and may become embroiled in larger regional consequences.

## Scenes & Actors
### Characters

1. **Mayor Elinor Greenfield:** The town's leader, seeking the party's aid to save Kolberdon from the blight and preserve the harvest festival.
2. **Elderly Farmer Gideon Willowfield:** A wise and experienced farmer who holds knowledge about the town's agricultural practices and may provide crucial information about the blight.

### Creatures

1. **Shadow Harvesters:** Otherworldly entities originating from the shadow realm, feeding on the life force of crops and causing the blight.
2. **Darkling Sprites:** Mischievous creatures that emerge from the tear, spreading corruption and hindering the party's progress.

### Locations

1. **Sunlit Orchards:** The heart of Kolberdon's farming community, now plagued by the blight. Investigating here will reveal the severity of the issue.
2. **Shadowed Hollow:** A hidden grove where the tear in the shadow realm is located, guarded by the Shadow Harvesters.

### Random Encounters

1. **Blighted Wildlife:** Animals affected by the blight become aggressive, posing a threat to the party as they investigate the fields.
2. **Cursed Crop Circle:** A mysterious glyph appears in the fields, emanating dark energy and attracting more shadowy creatures when approached by the party.

## Notes