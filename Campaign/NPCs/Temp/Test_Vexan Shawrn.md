---
tags:
  - "#Character"
  - "#NPC"
art: z_Assets/NPCs/VexanShawrn.png
pronounced: VEX-an SH-warn
ancestry: Human
heritage: Tiefling
gender: Male
pronouns: He/Him
age: Young Adult
sexuality: Gay
alignment: Neutral Evil
language:
  - Common
occupation:
  - Criminal
organization:
  - "[[Hushed]]"
location:
  - "[[Onyxdale]]"
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
>> ---|---|
>> **Art** | `INPUT[imageSuggester(optionQuery("")):art]` |
>
>> [!metadata|metadataoption]- Bio
>> #### Bio
>>  |
>> ---|---|
>> **Pronounced** |  `INPUT[textArea:pronounced]` |
>> **Aliases** | `INPUT[list:aliases]` |
>> **Ancestry** | `INPUT[Ancestry][suggester:ancestry]` |
>> **Heritage** | `INPUT[Heritage][suggester:heritage]` |
> **Creature Type** | `INPUT[textArea:ancestry]` |
> **Creature Sub-Type** | `INPUT[textArea:heritage]` |
>> **Gender** | `INPUT[Gender][:gender]` |
>> **Pronouns** | `INPUT[Pronouns][:pronouns]` |
>> **Age** | `INPUT[Age][:age]` |
>> **Sexuality** | `INPUT[Sexuality][:sexuality]` |
>> **Alignment** | `INPUT[Alignment][:alignment]` |
>
>> [!metadata|metadataoption]- NPC Info
>> #### NPC Info
>>  |
>>---|---|
>> **Languages** | `INPUT[Language][inlineListSuggester:language]` |
>> **Ideals** | `INPUT[textArea:ideals]` |
>> **Flaws** | `INPUT[textArea:flaws]` |
>> **Fears** |  `INPUT[textArea:fears]` |
>> **Mannerisms** |  `INPUT[textArea:mannerisms]` |
>> **Occupations** | `INPUT[Occupation][inlineListSuggester:occupation]` |
>> **Organizations** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
>> **Religions** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):religion]` |
>> **Owned Locations** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):ownedlocation]` |
>> **Current Location** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |
>> **Condition** | `INPUT[Condition][:condition]` |
>
>> [!metadata|metadataoption]- Party Info
>> #### Party Info
>>  |
>> ---|---|
>> **Traveling With** | `INPUT[inlineListSuggester(optionQuery(#Party AND !"z_Templates"), useLinks(partial)):whichparty]` |
>> **Party 1 Relation** | `INPUT[Party1Relation][:party1relation]` |

> [!infobox]+
> # `=this.file.name`
> `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ![[PlaceholderAudio.webm]]
> ###### Bio
>  |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Ancestry** | `VIEW[{ancestry}]` |
> **Heritage** | `VIEW[{heritage}]` |
> **Gender** | `VIEW[{gender}]` |
> **Pronouns** | `VIEW[{pronouns}]` |
> **Age** | `VIEW[{age}]` |
> **Sexuality** | `VIEW[{sexuality}]` |
> **Alignment** | `VIEW[{alignment}]` |
> ###### Info
>  |
> ---|---|
> **Languages** | `VIEW[{language}][text]` |
> **Occupations** | `VIEW[{occupation}][text]` |
> **Organization** | `VIEW[{organization}][link]` |
> **Religions** | `VIEW[{religion}][link]` |
> **Owned Locations** | `VIEW[{ownedlocation}][link]` |
> **Current Location** | `VIEW[{location}][link]` |
> **Condition** | `VIEW[{condition}]` |


# **`=this.file.name`** <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>

> [!metadata|letters]- Letters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE econtains(holder, this.file.link) AND contains(tags, "Letter")
> SORT file.name ASC

> [!metadata|literature]- Literature
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, quicknote AS Notes
> FROM "Campaign"
> WHERE econtains(holder, this.file.link) AND contains(tags, "Literature")
> SORT file.name ASC

## Overview

> [!kirk|info] Prompt (Remove me)
> Craft an encompassing overview of this NPC's essence. Explore their background, motivations, quirks, and role within the world. Highlight the unique traits that define this character, delving into their personality, history, and connections to the setting. What makes this NPC stand out, and how might they influence or interact with the players and the unfolding story?

> [!column|2 no-title]
>
> 
>> [!metadata|ideals] Ideals
> `VIEW[{ideals}][text]`
>
>> [!metadata|flaws] Flaws
> `VIEW[{flaws}][text]`
> 
>> [!metadata|fear] Fears
> `VIEW[{fears}][text]`
>
>> [!metadata|mannerism] Mannerisms
> `VIEW[{mannerisms}][text]`

## Goals

**Goals:** Vexan's primary goal is to protect Watson General and its interests in Onyxdale. As a member of "The Hushed," he also works to ensure the success and prosperity of the gang. Vexan seeks to rise within the gang's ranks and wield his influence to secure the tiefling community's place in the city.

**Motivation:** Vexan's motivation is twofold. He is motivated by a sense of duty and loyalty to Watson General, appreciating the security and stability it brings to Onyxdale. Simultaneously, his ties to "The Hushed" stem from a desire to create a space where tieflings can thrive and be treated as equals in the city, free from discrimination.

## Acquaintances

> [!kirk|info] Prompt (Remove me)
Map out the intricate web of relationships surrounding this NPC. Who comprises their family, friends, and rivals? Explore the dynamics within these connections, detailing the history and events that shaped these relationships. What bonds tie them to their family or friends, and what conflicts or events have led to rivalries? Uncover the stories, shared experiences, or betrayals that have influenced the course of these relationships, shaping the NPC's interactions and choices.

## Current Events

> [!kirk|info] Prompt (Remove me)
> Zoom into the present circumstances surrounding this NPC. What's happening in their life right now? Detail the ongoing events, challenges, or opportunities they're facing. Are they dealing with a personal crisis, pursuing a new goal, or involved in a conflict? Furthermore, what are they actively striving for at this moment? Explore their immediate objectives, aspirations, or plans. How are these current events and goals shaping their decisions and actions in the present narrative?

## History

Vexan was born into a tiefling enclave in Onyxdale, a community that often faced prejudice and suspicion due to their infernal heritage. Growing up, Vexan witnessed firsthand the challenges his people faced, and he resolved to make a difference.

He joined "The Hushed" as a young tiefling seeking to protect and uplift his community. Over time, Vexan's dedication and combat skills caught the attention of Watson General, a prominent figure in the city. Impressed by Vexan's loyalty and discipline, Watson General offered him a position as a guard, tasked with protecting the interests of the establishment.

Vexan's role as a guard for Watson General involves maintaining order, managing security, and dealing with potential threats. His affiliation with "The Hushed" allows him to navigate the criminal underbelly of Onyxdale, gathering information and resources to benefit both his tiefling community and the gang.

Vexan's dual allegiance, to both Watson General and "The Hushed," places him in a delicate position. He must carefully balance the expectations of his employer and the needs of the gang. Vexan, however, sees this as an opportunity to create a bridge between the tiefling community and the broader population, fostering understanding and cooperation.

As tensions rise in Onyxdale, Vexan's skills as a guard and his influence within "The Hushed" make him a crucial figure in the delicate dance between different factions in the city.

## Notes





