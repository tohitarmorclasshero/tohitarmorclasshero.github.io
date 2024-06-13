---
tags:
  - "#Party"
art: z_Assets/Parties/MotleyFew.png
journeyboard: "[[Motley Few Journey Board]]"
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
> **Aliases** | `INPUT[list:aliases]` |
>> **Journey Board** | `INPUT[Null][suggester(optionQuery("Campaign/Parties/Journey Boards"), useLinks(partial)):journeyboard]` | 

# **<center>`=this.file.name`</center>**

> [!metadata|characters] Characters
>> [!cards|dataview 5] **Parties**
>>```dataview
>> TABLE WITHOUT ID
>>	embed(link(art)) AS "Art",
>>     "<span style='display: block; text-align: center; margin-bottom: 5px;'>" + link(file.link, Title) + "</span>" AS Title
>> FROM "Campaign"
>> WHERE econtains(whichparty, this.file.link) AND contains(tags, "Character") AND !contains(condition, "Dead")
>> SORT tags DESC, file.name ASC
>>```

> [!metadata|sessionlogs]- Session Logs `VIEW[{journeyboard}][link]`
>> [!cards|dataview 3]
>>```dataview
TABLE WITHOUT ID
>>     "<span style='display: block; border-bottom: 2px solid var(--accent); text-align: center; margin-bottom: 5px;'>" + link(file.link, Title) + "</span>" AS Title,
>>     "<span style='display: block; border-bottom: 2px solid var(--accent); text-align: center; margin-bottom: 5px;'>" + sessiondate + "</span>" AS SessionDate,
>>	quicknote AS "QuickNotes"
>> FROM "Campaign"
>> WHERE econtains(whichparty, this.file.link) AND contains(tags, "SessionNote")
>> SORT date(sessiondate, "dd/MM/yyyy") DESC LIMIT 9
>>```

> [!metadata|adventure]- Adventures
>> [!cards|dataview 3]
>>```dataview
TABLE WITHOUT ID
>>     "<span style='display: block; border-bottom: 2px solid var(--accent); text-align: center; margin-bottom: 5px;'>" + link(file.link, Title) + "</span>" AS Title,
>>	quicknote AS "QuickNotes"
>> FROM "Campaign"
>> WHERE econtains(whichparty, this.file.link) AND contains(tags, "Adventure") AND !contains(status, "✅") AND !contains(status, "❌")
>>SORT file.name ASC
>>```

## NPC Relations
> [!column|3 no-title]
>
>> [!metadata|family] Family
>> ```dataview
>> TABLE join(aliases, ", ") AS Aliases
>> FROM "Campaign"
>> WHERE econtains(party1relation, "Family") AND !contains(condition, "Dead")
>> SORT file.name ASC
> 
>> [!metadata|ally] Ally
>> ```dataview
>> TABLE join(aliases, ", ") AS Aliases
>> FROM "Campaign"
>> WHERE econtains(party1relation, "Ally") AND !contains(condition, "Dead")
>> SORT file.name ASC
>
>> [!metadata|friend] Friends
>> ```dataview
>> TABLE join(aliases, ", ") AS Aliases
>> FROM "Campaign"
>> WHERE econtains(party1relation, "Friend") AND !contains(condition, "Dead")
>> SORT file.name ASC
>
>> [!metadata|like] Like
>> ```dataview
>> TABLE join(aliases, ", ") AS Aliases
>> FROM "Campaign"
>> WHERE econtains(party1relation, "Like") AND !contains(condition, "Dead")
>> SORT file.name ASC
> 
>> [!metadata|dislike] Dislike
>> ```dataview
>> TABLE join(aliases, ", ") AS Aliases
>> FROM "Campaign"
>> WHERE econtains(party1relation, "Dislike") AND !contains(condition, "Dead")
>> SORT file.name ASC
> 
>> [!metadata|enemy] Enemy
>> ```dataview
>> TABLE join(aliases, ", ") AS Aliases
>> FROM "Campaign"
>> WHERE econtains(party1relation, "Enemy") AND !contains(condition, "Dead")
>> SORT file.name ASC
> 

## **Notes**

-----