---
tags:
  - "#Character"
  - "#NPC"
art: z_Assets/NPCs/Rahix.png
pronounced: RAH-ix
ancestry: Fetchling
gender: Male
pronouns: He/Him
age: Mature Adult
sexuality: Bisexual
alignment: True Neutral
language:
  - Common
  - Necril
location:
  - "[[Kolberdon]]"
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

Rahix is an enigmatic and knowledgeable fetchling who has dedicated his life to the study of the Shadow Plane. With his deep understanding of its mysteries and intricacies, he serves as a valuable resource for those seeking to explore the shadowy realms beyond. Rahix's keen intellect and unwavering curiosity make him an invaluable ally for adventurers and scholars alike.

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

Rahix's primary goal is to uncover the secrets of the Shadow Plane and unravel its mysteries. He seeks to expand his knowledge of this elusive realm and share his findings with those who dare to venture into its depths. Rahix hopes to shed light on the shadowy unknown, dispelling fear and superstition through the power of understanding.

## Acquaintances

> [!kirk|info] Prompt (Remove me)
Map out the intricate web of relationships surrounding this NPC. Who comprises their family, friends, and rivals? Explore the dynamics within these connections, detailing the history and events that shaped these relationships. What bonds tie them to their family or friends, and what conflicts or events have led to rivalries? Uncover the stories, shared experiences, or betrayals that have influenced the course of these relationships, shaping the NPC's interactions and choices.

## Current Events

> [!kirk|info] Prompt (Remove me)
> Zoom into the present circumstances surrounding this NPC. What's happening in their life right now? Detail the ongoing events, challenges, or opportunities they're facing. Are they dealing with a personal crisis, pursuing a new goal, or involved in a conflict? Furthermore, what are they actively striving for at this moment? Explore their immediate objectives, aspirations, or plans. How are these current events and goals shaping their decisions and actions in the present narrative?

## History

Rahix was born into a family of fetchlings who had long left the Shadow Plane. From a young age, he was fascinated by the mysterious and ever-shifting nature of the shadowy realm, spending countless hours exploring its eerie landscapes and studying its peculiar inhabitants. As he grew older, Rahix dedicated himself to the pursuit of knowledge, delving deeper into the secrets of the Shadow Plane and honing his skills as a researcher and scholar. Now, in his twilight years, Rahix remains as curious and driven as ever, continuing his quest to unlock the mysteries of the shadowy unknown.

## Notes





