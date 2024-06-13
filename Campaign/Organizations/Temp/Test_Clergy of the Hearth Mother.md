---
tags:
  - Organization
art: z_Assets/Organizations/Tableau_ClergyoftheHearthMother.png
pronounced: KLER-gee of the H-earth MO-ther
organizationtype:
  - Faith
hierarchy: "[[Clergy of the Hearth Mother Hierarchy]]"
head:
  - "[[Ruck Sul]]"
worship:
  - "[[Sil'jun]]"
hq: 
location:
  - "[[Valdian]]"
  - "[[Onyxdale]]"
  - "[[Kolberdon]]"
  - "[[Test_Geo]]"
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
> **Type** | `INPUT[OrganizationType][inlineListSuggester:organizationtype]` |
> **Hierarchy** | `INPUT[Null][suggester(optionQuery("Campaign/Organizations/Hierarchies"), useLinks(partial)):hierarchy]` | 
> **Head** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):head]` |
> **Steward** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):steward]` |
> **Parent Organization** | `INPUT[inlineListSuggester(optionQuery(#Organization AND !"z_Templates"), useLinks(partial)):organization]` |
> **Worship** | `INPUT[inlineListSuggester(optionQuery(#Character AND !"z_Templates"), useLinks(partial)):worship]` |
> **HQ** | `INPUT[Null][suggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):hq]` |
> **Operating Areas** | `INPUT[inlineListSuggester(optionQuery(#Location AND !"z_Templates"), useLinks(partial)):location]` |

> [!infobox]+
> # `=this.file.name`
> ###### `VIEW[!\[\[{art}\]\]][text(renderMarkdown)]`
> ###### Info
> | |
> ---|---|
> **Aliases** | `VIEW[{aliases}][text]` |
> **Type** | `VIEW[{organizationtype}][text]` |
> **Hierarchy** | `VIEW[{hierarchy}][link]` |
> **Head** | `VIEW[{head}][link]` |
> **Steward** | `VIEW[{steward}][link]` |
> **Parent Organization** | `VIEW[{organization}][link]` |
> **Worship** | `VIEW[{worship}][link]` |
> **HQ** | `VIEW[{hq}][link]` |

# `=this.file.name` <span style="font-size: medium">"`VIEW[{pronounced}]`"</span>

> [!kirk|info] Info (Remove me)
> Organization: Organizations can be anywhere from a small band of misfits to an entire Nation.

> [!metadata|geography]- Geography
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion"
> FROM "Campaign"
> WHERE contains(tags, "Geography") AND econtains(organization, this.file.link)
> SORT dominion ASC, file.name ASC

> [!metadata|county]- County
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(terrain, ", ") AS Terrain, join(link(dominion), ", ") AS "Dominion"
> FROM "Campaign"
> WHERE contains(tags, "County") AND econtains(organization, this.file.link)
> SORT dominion ASC, file.name ASC

> [!metadata|settlements]- Settlements
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, settlementtype AS Type, defence AS Defences, join(link(dominion), ", ") AS "Dominion"
> FROM "Campaign"
> WHERE contains(tags, "Settlement") AND econtains(organization, this.file.link)
> SORT dominion ASC, file.name ASC

> [!metadata|district]- Districts
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(districttype, ", ") AS Type
> FROM "Campaign"
> WHERE contains(tags, "District") AND econtains(organization, this.file.link)
> SORT districttype ASC, file.name ASC

> [!metadata|location]- Locations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(poitype, ", ") AS Type, join(link(organization), ", ") AS "Organization(s)"
> FROM "Campaign"
> WHERE contains(tags, "POI") AND econtains(organization, this.file.link)
> SORT poitype ASC, file.name ASC

> [!metadata|organizations]- Child Organizations
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(organizationtype, ", ") AS Type
> FROM "Campaign"
> WHERE contains(tags, "Organization") AND econtains(organization, this.file.link)
> SORT organizationtype ASC, file.name ASC

> [!metadata|characters]- Characters
> ```dataview
> TABLE join(aliases, ", ") AS Aliases, join(occupation, ", ") AS "Occupations", join(link(organization), ", ") AS "Organizations"
> FROM "Campaign"
> WHERE contains(tags, "Character") AND econtains(organization, this.file.link) AND !contains(condition, "Dead")
> SORT tags DESC, file.name ASC

## Overview

## Culture
### Mission
The mission of the Clergy of the Hearth Mother is to foster healing, compassion, and the passage to the next life. Through their dedication to the goddess Jil'jun, they strive to alleviate suffering, bring comfort to the afflicted, and guide souls with love and reverence. With their knowledge of medicinal arts and spiritual practices, they seek to restore balance, nurture well-being, and ensure a peaceful transition for all who come under their care. In doing so, they embody the eternal cycle of life and death, embracing the profound interconnectedness of existence and spreading the healing light of the Hearth Mother's grace throughout the world.

### Conduct
The Clergy of the Hearth Mother conducts themselves with unwavering compassion, reverence, and a commitment to healing. They embody the values of selflessness and service, placing the needs of others above their own. With gentle hearts and skilled hands, they offer solace, care, and guidance to those in need, upholding the sanctity of life and honoring the transition to the afterlife. Their conduct is guided by a deep sense of empathy and respect for all beings, as they strive to bring healing, comfort, and the enduring presence of Sil'jun's grace into the lives of those they touch.

### Recruitment & Training
The Clergy of the Hearth Mother follows a diligent process for recruiting and training their members. Prospective candidates are sought among those who display a genuine compassion for others and a calling to serve. Through careful observation and assessment, individuals who show aptitude for healing, empathy, and a deep connection to the divine are identified.

Once selected, recruits undergo a comprehensive training program that encompasses both practical and spiritual teachings. They learn the art of healing, studying medicinal herbs, remedies, and various healing techniques. Training also includes honing their empathic skills, learning to listen attentively, and offering guidance and solace to those in need. They immerse themselves in the sacred texts and rituals associated with Sil'jun, deepening their understanding of life, death, and the transition between realms.

The training is conducted under the guidance of experienced members of the clergy, who serve as mentors and instructors. Recruits are encouraged to develop their own spiritual connection with Sil'jun through prayer, meditation, and introspection. They are instilled with the core values of compassion, reverence, and selflessness, understanding that their service is a sacred duty to alleviate suffering and guide souls with love and care.

As part of their training, recruits also participate in practical experiences, assisting in healing rituals, tending to the sick and wounded, and supporting funeral rites. Through these hands-on encounters, they gain firsthand knowledge and develop the necessary skills to carry out their sacred duties.

Throughout their training, the recruits are closely supervised and evaluated to ensure they uphold the principles and standards of the Clergy of the Hearth Mother. Those who demonstrate exceptional aptitude, devotion, and alignment with the values of the clergy may be selected for further specialization in specific areas of healing or spiritual guidance.

By carefully recruiting and diligently training their members, the Clergy of the Hearth Mother ensures a dedicated and compassionate cohort of healers and guides who embody the teachings and grace of Sil'jun, bringing comfort, hope, and healing to all they encounter.

### Ranks
1.  Initiates: These are the entry-level members of the clergy who have recently joined and are in the early stages of their training. Initiates undergo a period of acclimation and basic instruction in the teachings, rituals, and practices of the Hearth Mother.

2.  Acolytes: Acolytes have progressed beyond the initiate stage and are actively engaged in their training. They have demonstrated dedication, commitment, and the potential for growth within the clergy. Acolytes assist in ceremonies, rituals, and other clerical duties under the guidance of more senior members.

3.  Novices: Novices have completed their initial training and have been deemed ready for more advanced instruction. They have gained a deeper understanding of the doctrine, rituals, and spiritual practices associated with the Hearth Mother. Novices often serve as assistants to more experienced clergy members, gaining practical experience and refining their skills.

4.  Healers/Guides: This rank encompasses those who have specialized in healing or spiritual guidance, focusing their studies and practice on these specific areas. Healers excel in the arts of physical and spiritual healing, while Guides specialize in providing counsel, comfort, and guidance to those in need. They are recognized for their advanced skills and are often sought after for their expertise.

5.  Priests/Priestesses: Priests and Priestesses are recognized as spiritual leaders within the Clergy of the Hearth Mother. They have completed extensive training, demonstrating profound knowledge, wisdom, and an unwavering commitment to the teachings and values of Sil'jun. They conduct ceremonies, lead worship services, offer guidance, and are responsible for overseeing the spiritual well-being of the community.

6. Hierarch: Revered for their wisdom and extensive knowledge, the Hierarch of the Clergy embody the culmination of a lifetime dedicated to the service of Sil'jun. These respected individuals possess profound understanding of the teachings and practices of the Hearth Mother, providing guidance, mentorship, and spiritual counsel to the clergy. With their experience, Hierarchs take on leadership roles within local temples and regional congregations, overseeing the spiritual well-being of their communities and contributing to the growth and development of the faith. Their presence is a source of inspiration, stability, and profound insight within the clergy.

7.  High Priest/Priestess: The High Priest or High Priestess holds the highest rank within the clergy of a given region. They are the spiritual authority and leader of the Clergy of the Hearth Mother. The High Priest/Priestess is chosen based on their exceptional knowledge, experience, and leadership qualities. They guide the direction of the clergy within their region, make important decisions, and serve as a representative of Sil'jun's divine will.

8. Hearthdivine: The Heathdivine is the highest rank within the Clergy, considered the direct representative and voice of the Hearth Mother herself. This esteemed position is held by an individual who has demonstrated exceptional wisdom, profound spiritual connection, and an unwavering commitment to the divine teachings of Sil'jun. The Hearthdivine oversees the entire clergy and serves as the ultimate spiritual authority, guiding the direction, rituals, and practices of the faith. Their words are considered sacred, and they are revered as a living embodiment of the Hearth Mother's will and grace. The Hearthdivine is often consulted in matters of great importance and may play a significant role in shaping the faith and its interaction with the broader world.

### Uniforms & Equipment
1.  Robes: The core component of the uniform is a flowing robe made of fine, soft fabric. The robe is predominantly white, representing purity, healing, and the transition to the afterlife. It is often adorned with intricate embroidery or patterns in shades of red, symbolizing the vitality of life and the passion for aiding others.

2.  Sash or Belt: A wide sash or belt in a vibrant shade of red is worn around the waist, serving both as a functional accessory and a symbol of the Clergy's dedication. The sash or belt may feature embroidered symbols or patterns that represent aspects of Sil'jun's domain, such as hearts, leaves, or ethereal motifs.

3.  Mantle or Cloak: Over the robe, members may wear a mantle or cloak made of lightweight material in a deep red hue. The cloak may have a hood that can be raised or lowered, providing protection from the elements and adding an air of mystique to their appearance.

4.  Amulet or Symbol: Each member of the clergy wears an amulet or pendant that bears the symbol of the Hearth Mother. The symbol often consists of a stylized representation of a hearth or a combination of a flame and a heart. The amulet is typically crafted from precious metals, adorned with gemstones, or engraved with intricate designs.

5.  Headdress: Some members of higher rank or specialization may wear a headdress or headpiece as a mark of their elevated status. It may feature feathers, gems, or intricate metalwork in the colors of red and white, signifying their deeper connection to the goddess and their specific role within the clergy.

6.  Healing Implements: Members of the clergy often carry a variety of healing implements, such as salves, herbal pouches, and bandages. These items are kept in small pouches or pockets attached to their belts or carried in specially designed bags. The implements symbolize their commitment to healing and provide practical tools for their work.

7.  Sacred Texts: Some members may carry small, ornate books or scrolls containing sacred texts, hymns, and prayers associated with the Hearth Mother. These texts are regarded as invaluable sources of wisdom and guidance, and are consulted during ceremonies and rituals.

It's worth noting that while there may be a general uniform and equipment guidelines, variations may exist based on individual preferences, regional traditions, region or specific roles within the clergy.

### Example
## Acquaintances

> [!kirk|info] Prompt (Remove me)
> Map out the network of relationships this organization maintains with other groups and individuals. Who are their allies, rivals, or adversaries? Detail the nature of these connections, whether they're alliances based on shared interests, longstanding rivalries, or uneasy truces. What events or conflicts have shaped these relationships? Furthermore, explore the interactions and dealings this organization has with influential individuals or entities outside its circle. How do these connections influence the organization's operations and goals?

## Current Events

> [!kirk|info] Info (Remove me)
> Zoom into the present landscape of this organization. What is currently happening within its ranks? Detail ongoing developments, internal conflicts, or achievements. Is the organization facing challenges, undergoing reforms, or enjoying newfound success? Furthermore, what are its current objectives or endeavors? Explore the immediate goals or missions the organization is striving to accomplish. How are these current events and goals influencing the actions and dynamics within the group?

## History

The history of the Clergy of the Hearth Mother stretches back centuries, rooted in the ancient times when the teachings of Sil'jun first spread throughout the land. It is said that Sil'jun, the Hearth Mother, was a divine being who embodied the essence of life, good health, and the transition to the afterlife. Her teachings emphasized the importance of nurturing the body, mind, and soul, and fostering compassion and healing in all aspects of existence.

In the early days, Sil'jun's teachings were passed down through oral traditions, with her followers forming small communities and tending to the sick, wounded, and spiritually lost. Over time, the devotion to Sil'jun grew, and her influence spread across the realms. Recognizing the need for organized guidance and support, the Clergy of the Hearth Mother was officially established as a dedicated institution.

The clergy became the custodians of Sil'jun's teachings, responsible for preserving the sacred knowledge and rituals associated with the Hearth Mother. They built temples, shrines, and healing sanctuaries, serving as beacons of hope and centres of communal care. The clergy's role expanded beyond healing, encompassing the guidance of souls during their passage from the mortal realm to the afterlife.

Throughout its history, the Clergy of the Hearth Mother has weathered numerous challenges and faced periods of adversity. There were times when the faith of Sil'jun was marginalized, and the clergy faced persecution from other religious orders or power-seeking forces. However, through resilience, perseverance, and the unwavering faith of its members, the clergy always managed to endure.

One significant event in the history of the clergy occurred during a time of great turmoil, when the kingdom they resided in was torn apart by rebellion. The citizens grew tired of the lack of effort and care from the ruling crown, and their frustrations boiled over into a rebellion that spread across the kingdom. During this time, the clergy found themselves caught in the crossfire, as some saw them as symbols of the oppressive regime.

However, rather than aligning themselves with the ruling class, the clergy chose to side with the people, embracing their suffering and offering solace and guidance. They used their healing skills to tend to the wounded and their spiritual wisdom to provide comfort during these tumultuous times. Their support and dedication to the people played a crucial role in the eventual resolution of the rebellion and the restoration of peace.

Today, the Clergy of the Hearth Mother stands as a beacon of hope, compassion, and healing in the world. They continue to provide comfort, guidance, and spiritual support to those in need, nurturing the body, mind, and soul with their teachings and practices. The clergy's rich history serves as a testament to their unwavering commitment to Sil'jun's divine grace, and they remain a cherished and respected institution within the realms they serve.

## Notes



