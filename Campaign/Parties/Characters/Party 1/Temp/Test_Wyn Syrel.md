---
tags:
  - "#Character"
  - "#Player"
art: z_Assets/Players/WynSyrel.png
playedby: Worldsaidhi
pronounced: WYIN SIGH-rel
aliases:
  - Lady Wyn Syrel
ancestry: Elf
heritage: Woodland Elf
gender: Female
pronouns: She/Her
age: Young Adult
occupation:
  - Noble
  - Adventurer
location:
  - "[[Onyxdale]]"
whichparty:
  - "[[Motley Few]]"
condition: Healthy
---

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
>>---|---|
>> **Art** | `INPUT[imageSuggester(optionQuery("")):art]` |
>
>> [!metadata|metadataoption]- Bio
>> #### Bio
>>  |
>>---|---|
>> **Played By** |  `INPUT[textArea:playedby]`
>> **Character Sheet** |  `INPUT[textArea:charactersheet]`
>> **Pronounced** |  `INPUT[textArea:pronounced]`
>> **Aliases** | `INPUT[list:aliases]` |
>> **Ancestry** | `INPUT[Ancestry][suggester:ancestry]` |
>> **Heritage** | `INPUT[Heritage][suggester:heritage]` |
>> **Gender** | `INPUT[Gender][:gender]` |
>> **Pronouns** | `INPUT[Pronouns][:pronouns]`
>> **Age** | `INPUT[Age][:age]` |
>
>> [!metadata|metadataoption]- Info
>> #### Player Info
>>  |
>>---|---|
>> **Occupations** | `INPUT[Occupation][inlineListSuggester:occupation]` |
>> **Organizations** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
>> **Religions** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):religion]` |
>> **Owned Locations** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):ownedlocation]` |
>> **Current Location** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |
>> **Which Party** | `INPUT[inlineListSuggester(optionQuery(#Party AND !"z_Templates"), useLinks(partial)):whichparty]` |
>> **Condition** | `INPUT[Condition][:condition]` |

> [!infobox]+
> # `=this.file.name`
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ###### Played By: `VIEW[{playedby}][text]`
> ###### Bio
>  |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Ancestry** | `VIEW[{ancestry}]` |
> **Heritage** | `VIEW[{heritage}]` |
> **Gender** | `VIEW[{gender}]` |
> **Pronouns** | `VIEW[{pronouns}]` |
> **Age** | `VIEW[{age}]` |
> ###### Info
>  |
> ---|---|
> **Occupations** | `VIEW[{occupation}][text]` |
> **Organization** | `VIEW[{organization}][link]` |
> **Religions** | `VIEW[{religion}][link]` |
> **Owned Locations** | `VIEW[{ownedlocation}][link]` |
> **Current Location** | `VIEW[{location}][link]` |
> **Condition** | `VIEW[{condition}]` |

# **`=this.file.name`** <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>

> [!metadata|servicerequests]- Service Requests
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE econtains(customer, this.file.link) AND contains(tags, "Service") AND !contains(status, "✅") AND !contains(status, "❌")
> SORT organizationtype ASC, file.name ASC

> [!metadata|letters]- Letters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE econtains(holder, this.file.link) AND contains(tags, "Letter")
> SORT organizationtype ASC, file.name ASC

> [!metadata|literature]- Literature
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE econtains(holder, this.file.link) AND contains(tags, "Literature")
> SORT organizationtype ASC, file.name ASC

## Ideals
### Loves

Being treated like 'royalty'

### Hates

Does not like for people to know that is is of higher class  
Getting screwed over without cause

## Goals

Wyn is trying to make a name for herself, For her entire life, she has been in the shadow of her father, though she has no distain for this.

### Short-term


### Long-term


## Traits
#### Perks

Tries to develop friendly relationships with everybody she meets. Includes remember names, faces, any details told.  
Tries to give back to the community

#### Flaws

Vengeance is her number one priority if she is screwed over.

## History
### Birth Location

**Birth Date**: 05/08/000  
**Birth Location:** [[Mytadell]]

### Childhood

Traveled alongside her father far and wide. She enjoyed her time and became close with her father.  
When home wyn, her sister, and her father went on many hunting trips. This is how she learnt to use a bow.

[[Wyn Syrel]] (7 years) and [[Vanderin Irius]] (6 Years) had talked to each other many years ago during a ball hosted in [[Valdian]]. Playfully messing around during the ball, their parents then forced them to dance together for the sake of ‘appearances’. [[Wyn Syrel]] and [[Vanderin Irius]] begrudgingly danced for the amusement of their parents until they could slip away again. Once this ordeal was over they awkwardly continued their playing. Later on they continued their Communication through letters over the years. Talking about their boring days in court and watching the world run past them. Until [[Vanderin Irius]] mentioned that he was going to leave the Capital and assist the people of [[Meshwich]]. [[Wyn Syrel]], intrigued by adventure and yearning to assist in her fathers diplomatic ways, asked if she could assist in which [[Vanderin Irius]] was all too happy to invite her. Other than what they remember of each other as Kids, [[Wyn Syrel]] and [[Vanderin Irius]] had not seen each other since the ball.

### Journey



### Worship


## Notes

[Wyn's Primary Notes](https://docs.google.com/document/d/16YM7cMSC-LP1eKWmC_4xKT1ZqM3M4qWFFqbqTAQNCC0/edit#heading=h.fav6scqmwu85)
[Wyn's Extra Notes](https://docs.google.com/document/d/1E5N44Ty39UPWP5eVb_9WnkxSnsXwEsbT49JItKd2zG4/edit)

