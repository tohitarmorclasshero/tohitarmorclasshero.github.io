---
tags:
  - "#Character"
  - "#Player"
art: z_Assets/Players/VanderinIrius.png
playedby: Hook
pronounced: VAN-DER-in IR-EE-us
aliases:
  - Lord Vanderin Alexander Veron Irius II
ancestry: Human
pronouns: He/Him
age: Young Adult
occupation:
  - Noble
  - Adventurer
  - Mage
location:
  - "[[Onyxdale]]"
whichparty:
  - "[[Motley Few]]"
condition: Healthy
heritage: Versatile Heritage
gender: Male
religion:
  - "[[Clergy of the Hearth Mother]]"
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

Mischief, Kindness, Reading and Learning. Neutral criminality (Pickpocketing and stealing from people more well off)
Achieving news spells, expanding his knowledge. Feeling like he is developing his skills.

### Hates

Bullies, Criminals that seek to harm in their activities.

## Goals

Make lots of Money to expand spells known.
Become a renowned Wizard of the Arcane arts.
Make a name for himself, making his Parents and sisters proud.

## Traits
### Perks
**Well Mannered.** Being from a noble background it was usually required.
**Kind.** Seemingly only to people that deserve it.
**Merciful.** But only when they have not been too disruptive and if they are cooperating. But his past creeps in and can take over some times.
**Heroic.** Mostly if he is protecting someone.

### Flaws
**Haunted.** Scared to be judged for the mistake he made causing harm to innocents.
**Coward.** If things are looking really bad, If he can reach the people he cares about. Vanderin would most likely cut and run.
**Murderer.** Has killed people. He has also killed some innocents by mistake and it continues to haunt him.
**Thief.** Sometimes, more for the thrill and normally from people better off.
**Cruel.** Can be if his past catches up to him and takes control.
**Rude.** Only for people he has a distaste for.

## History
### Birth Location

**Birth Date**:  01/10/TBD 
**Birth Location:** [[Valdian]]

### Childhood

Vanderin spent most of his childhood reading books and playing tricks on people. Keeping an even balance of Intellect childlike humor.

Became a Soldier for 9 months fighting against the [[Garmwick Rebellion]]. 5 Years ago (17 Years Old)
Was apart of the [[Xahra Battalion]]

[[Wyn Syrel]] (7 years) and [[Vanderin Irius]] (6 Years) had talked to each other many years ago during a ball hosted in [[Valdian]]. Playfully messing around during the ball, their parents then forced them to dance together for the sake of ‘appearances’. [[Wyn Syrel]] and [[Vanderin Irius]] begrudgingly danced for the amusement of their parents until they could slip away again. Once this ordeal was over they awkwardly continued their playing. Later on they continued their Communication through letters over the years. Talking about their boring days in court and watching the world run past them. Until [[Vanderin Irius]] mentioned that he was going to leave the Capital and assist the people of [[Meshwich]]. [[Wyn Syrel]], intrigued by adventure and yearning to assist in her fathers diplomatic ways, asked if she could assist in which [[Vanderin Irius]] was all too happy to invite her. Other than what they remember of each other as Kids, [[Wyn Syrel]] and [[Vanderin Irius]] had not seen each other since the ball.

### Journey

During the army, Vanderin was quickly pushed to Sergeant because of his Fathers influence. The responsibility of looking after his men quickly took its toll on Vanderin and he began to have sleepless nights. One night during a chaotic chase for rebels in the city of [[Onyxdale]]. Vanderin and his men chased a band of rebels through the streets. The band took refuge in a house and began raining arrows down on his men. Getting close Vanderin Fire-balled the house and then pushed in. Just to find countless bodies. Bodies of Women, Children and townsfolk appeared to have tried to hide from the fighting. Seeing that the Rebels had fled the building before he got there. Vanderin became Catatonic and had to be pulled back and cared for by his men. Vanderin’s spell book was left behind at the house. He is Continuously haunted by this memory.

### Worship

[[Keata]] - To learn and expand his knowledge and seek to protect others. They have helped Vanderin by bestowing the gift of the Arcane arts onto him.

## Notes

[Vanderin's Notes](https://docs.google.com/document/d/1lm9TQ_aGTFFMl65su1EAF1lze_8A4g7T12pSzXEuEwc/edit)