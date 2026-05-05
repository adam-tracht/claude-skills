# AI Writing Pattern Catalog

Full reference for deslop. Signal words, problem, before/after for each pattern.

---

## SIGNIFICANCE INFLATION

**Signals:** serves/stands as, testament/reminder, vital/crucial/pivotal/key role, underscores its importance, reflects broader, symbolizing its enduring, represents a shift, marks a turning point, indelible mark, deeply rooted, setting the stage for

Before: *"This initiative marked a pivotal moment in the evolution of regional governance, reflecting broader trends toward decentralization."*
After: *"The institute was established in 1989 to publish regional statistics independently from the national office."*

**Notability inflation signals:** independent coverage, national media outlets, active social media presence, written by a leading expert

Before: *"Her views have been cited in The New York Times, BBC, and Financial Times. She maintains an active social media presence with over 500,000 followers."*
After: *"In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods."*

---

## SUPERFICIAL -ING ANALYSES

**Signals:** highlighting/underscoring/emphasizing..., reflecting/symbolizing..., contributing to..., fostering..., showcasing...

Tacked-on present participle phrases that add fake analytical weight.

Before: *"The color palette resonates with the region's natural beauty, symbolizing Texas bluebonnets, reflecting the community's deep connection to the land."*
After: *"The architect said the blue and green colors reference local bluebonnets and the Gulf coast."*

---

## PROMOTIONAL LANGUAGE

**Signals:** boasts, vibrant, rich (figurative), profound, nestled, in the heart of, groundbreaking, renowned, breathtaking, stunning, must-visit, commitment to excellence

Before: *"Nestled within the breathtaking region, it stands as a vibrant town with stunning natural beauty."*
After: *"The town is known for its weekly market and 18th-century church."*

---

## VAGUE ATTRIBUTION

**Signals:** Industry reports, Observers have cited, Experts argue/believe, Some critics argue, Several sources

Name the source or cut the claim.

Before: *"Experts believe it plays a crucial role in the regional ecosystem."*
After: *"The river supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences."*

---

## FORMULAIC SECTIONS

**Signals:** Despite its [strength]... faces challenges..., Despite these challenges, "Challenges and Legacy" heading, "Future Outlook" heading

Before: *"Despite its industrial prosperity, Korattur faces challenges typical of urban areas. Despite these challenges, Korattur continues to thrive."*
After: *"Traffic congestion increased after 2015 when three new IT parks opened."*

---

## AI VOCABULARY

High-frequency post-2023 tells. Replace or cut.

**Word list:** actually, additionally, align with, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate/intricacies, key (adjective), landscape (abstract), navigate (abstract), pivotal, showcase, tapestry (abstract), testament, underscore (verb), valuable, vibrant, nuanced, ecosystem (abstract), synergy, leverage (abstract)

Before: *"Additionally, this enduring testament to colonial influence showcases how pasta has integrated into the culinary landscape, fostering a vibrant tradition."*
After: *"Pasta dishes, introduced during Italian colonization, remain common, especially in the south."*

---

## COPULA AVOIDANCE

**Signals:** serves as, stands as, marks/represents [a], boasts, features, offers [a]

Before: *"Gallery 825 serves as LAAA's exhibition space and boasts over 3,000 square feet."*
After: *"Gallery 825 is LAAA's exhibition space. It has four rooms totaling 3,000 square feet."*

---

## NEGATIVE PARALLELISMS

**Not X, but Y / not just about X, it's Y** — delays the point by stating what something isn't before saying what it is.

Before: *"It's not just about the beat; it's part of the aggression and atmosphere. It's not merely a song, it's a statement."*
After: *"The heavy beat adds to the aggressive tone."*

**Tailing negation fragments:**
Before: *"The options come from the selected item, no guessing."*
After: *"The options come from the selected item without forcing the user to guess."*

---

## RULE OF THREE (TRICOLON)

LLMs force ideas into groups of three to appear comprehensive. Two items or one usually reads better.

Before: *"The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights."*
After: *"The event includes talks and panels, with time for informal networking between sessions."*

---

## SYNONYM CYCLING

Repetition-penalty behavior causes excessive synonym substitution instead of just repeating the right word.

Before: *"The protagonist faces challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home."*
After: *"The protagonist faces many challenges but eventually triumphs and returns home."*

---

## FALSE RANGES

"From X to Y" where X and Y aren't on a meaningful scale.

Before: *"Our journey has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter."*
After: *"The book covers the Big Bang, star formation, and current theories about dark matter."*

---

## FORMATTING TELLS

**Em dash overuse** — commas, periods, or parentheses almost always work better.

Before: *"The term is promoted by Dutch institutions—not by the people themselves—even in official documents."*
After: *"The term is promoted by Dutch institutions, not by the people themselves, and appears even in official documents."*

**Boldface overuse** — mechanical emphasis on phrases that don't need it.

Before: *"It blends **OKRs**, **KPIs**, and visual tools like the **Business Model Canvas**."*
After: *"It blends OKRs, KPIs, and visual tools like the Business Model Canvas."*

**Inline-header bullet lists** — bold term + colon + sentence.

Before:
```
- **User Experience:** The interface has been improved.
- **Performance:** Algorithms have been optimized.
```
After: *"The update improves the interface and speeds up load times."*

**Title case headings:**
Before: *"## Strategic Negotiations And Global Partnerships"*
After: *"## Strategic negotiations and global partnerships"*

**Emojis in structure:**
Before: `🚀 **Launch Phase:** Q3` / `💡 **Key Insight:** Users prefer simplicity`
After: *"The product launches in Q3. User research showed a preference for simplicity."*

---

## FILLER AND HEDGING

**Filler substitutions:**

| Instead of | Use |
|---|---|
| In order to | To |
| Due to the fact that | Because / Since|
| At this point in time | Now |
| In the event that | If |
| Has the ability to | Can |
| It is important to note that | (just say the thing) |
| It is worth noting that | (just say the thing) |

**Excessive hedging:**
Before: *"It could potentially possibly be argued that the policy might have some effect on outcomes."*
After: *"The policy may affect outcomes."*

**Generic positive conclusions** — the future looks bright, exciting times lie ahead, journey toward excellence, step in the right direction, continues to thrive

Before: *"The future looks bright for the company. Exciting times lie ahead as they continue their journey toward excellence."*
After: *"The company plans to open two more locations next year."*

---

## STYLE HABITS

**Hyphenated word pair overuse** — AI hyphenates common compound modifiers uniformly; humans are inconsistent. Common over-hyphenated pairs: third-party, cross-functional, client-facing, data-driven, decision-making, well-known, high-quality, real-time, long-term, end-to-end. (Technical or unusual compound modifiers: fine to hyphenate.)

**Persuasive authority tropes** — The real question is, at its core, in reality, what really matters, fundamentally, the deeper issue, the heart of the matter. Pretends to cut through noise; the sentence that follows restates an ordinary point with extra ceremony.

Before: *"The real question is whether teams can adapt. At its core, what really matters is organizational readiness."*
After: *"The question is whether teams can adapt. That depends on whether the organization is ready to change its habits."*

**Signposting / announcements** — Let's dive in, let's explore, let's break this down, here's what you need to know, without further ado

Before: *"Let's dive into how caching works in Next.js. Here's what you need to know."*
After: *"Next.js caches data at multiple layers: request memoization, the data cache, and the router cache."*

**Fragmented headers** — heading followed by a one-liner that restates it as a rhetorical warm-up.

Before:
```
## Performance

Speed matters.

When users hit a slow page, they leave.
```
After:
```
## Performance

When users hit a slow page, they leave.
```
