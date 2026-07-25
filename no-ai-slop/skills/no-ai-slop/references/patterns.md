# AI writing pattern catalog

Full reference for the no-ai-slop skill. Signal words, the problem, and a before and after for each pattern. Read this when auditing in Detect mode, when a draft is heavily sloppy, or when you are unsure whether something counts.

## Contents

- [Significance inflation](#significance-inflation)
- [Superficial -ing analysis](#superficial-ing-analysis)
- [Promotional language](#promotional-language)
- [Vague attribution](#vague-attribution)
- [Formulaic sections](#formulaic-sections)
- [AI vocabulary](#ai-vocabulary)
- [Copula avoidance](#copula-avoidance)
- [Negative parallelisms](#negative-parallelisms)
- [Faux-insight setups](#faux-insight-setups)
- [Colon reveals](#colon-reveals)
- [Rule of three](#rule-of-three)
- [Synonym cycling](#synonym-cycling)
- [False ranges](#false-ranges)
- [Dramatic fragmentation](#dramatic-fragmentation)
- [Fake-profound kickers](#fake-profound-kickers)
- [Formatting tells](#formatting-tells)
- [Filler and hedging](#filler-and-hedging)
- [Style habits](#style-habits)

---

## Significance inflation

**Signals:** serves as, stands as, testament, reminder, vital role, crucial role, pivotal, key role, underscores its importance, reflects broader, symbolizing its enduring, represents a shift, marks a turning point, indelible mark, deeply rooted, setting the stage for

Before: *"This initiative marked a pivotal moment in the evolution of regional governance, reflecting broader trends toward decentralization."*
After: *"The institute was established in 1989 to publish regional statistics independently from the national office."*

**Notability inflation signals:** independent coverage, national media outlets, active social media presence, written by a leading expert

Before: *"Her views have been cited in The New York Times, BBC, and Financial Times. She maintains an active social media presence with over 500,000 followers."*
After: *"In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods."*

---

## Superficial -ing analysis

**Signals:** highlighting, underscoring, emphasizing, reflecting, symbolizing, contributing to, fostering, showcasing

Tacked-on present participle phrases that add fake analytical weight. Replace with the actual consequence or cut.

Before: *"The color palette resonates with the region's natural beauty, symbolizing Texas bluebonnets, reflecting the community's deep connection to the land."*
After: *"The architect said the blue and green colors reference local bluebonnets and the Gulf coast."*

Before: *"The launch adds file search, highlighting the team's commitment to better workflows."*
After: *"The launch adds file search, so users can find old drafts without leaving the editor."*

---

## Promotional language

**Signals:** boasts, vibrant, rich (figurative), profound, nestled, in the heart of, groundbreaking, renowned, breathtaking, stunning, must-visit, commitment to excellence

Before: *"Nestled within the breathtaking region, it stands as a vibrant town with stunning natural beauty."*
After: *"The town is known for its weekly market and 18th-century church."*

---

## Vague attribution

**Signals:** industry reports, observers have cited, experts argue, experts believe, some critics argue, several sources, studies show, widely regarded as

Name the source or cut the claim. If the writer has no source, ask rather than inventing one.

Before: *"Experts believe it plays a crucial role in the regional ecosystem."*
After: *"The river supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences."*

---

## Formulaic sections

**Signals:** "Despite its [strength], it faces challenges", "Despite these challenges", a "Challenges and Legacy" heading, a "Future Outlook" heading

Before: *"Despite its industrial prosperity, Korattur faces challenges typical of urban areas. Despite these challenges, Korattur continues to thrive."*
After: *"Traffic congestion increased after 2015 when three new IT parks opened."*

---

## AI vocabulary

High-frequency post-2023 tells. Replace or cut.

**Word list:** additionally, align with, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate, intricacies, key (adjective), landscape (abstract), navigate (abstract), pivotal, showcase, tapestry, testament, underscore (verb), valuable, vibrant, nuanced, ecosystem (abstract), synergy, leverage (abstract), realm, beacon, multifaceted, meticulous, paramount, transformative, elevate, embark, supercharge, harness, ever-evolving

Before: *"Additionally, this enduring testament to colonial influence showcases how pasta has integrated into the culinary landscape, fostering a vibrant tradition."*
After: *"Pasta dishes, introduced during Italian colonization, remain common, especially in the south."*

Note: several of these words are fine in their literal sense. A physical landscape is a landscape. A biological ecosystem is an ecosystem. The tell is the abstract usage.

---

## Copula avoidance

**Signals:** serves as, stands as, marks a, represents a, boasts, features, offers a

Before: *"Gallery 825 serves as LAAA's exhibition space and boasts over 3,000 square feet."*
After: *"Gallery 825 is LAAA's exhibition space. It has four rooms totaling 3,000 square feet."*

Before: *"The app serves as a centralized hub for sponsor management."*
After: *"The app tracks sponsors, drafts, due dates, and approvals in one place."*

---

## Negative parallelisms

**Not X, but Y / not just about X, it's Y.** Delays the point by stating what something is not before saying what it is.

Before: *"It's not just about the beat; it's part of the aggression and atmosphere. It's not merely a song, it's a statement."*
After: *"The heavy beat adds to the aggressive tone."*

Before: *"The question isn't the model. It's the eval."*
After: *"The eval matters more than the model."*

**Negative listing.** "Not a X. Not a Y. A Z." Say Z.

**Tailing negation fragments:**
Before: *"The options come from the selected item, no guessing."*
After: *"The options come from the selected item without forcing the user to guess."*

---

## Faux-insight setups

**Signals:** this is the part most people skip, what most people get wrong, here's what nobody tells you, the part everyone misses, the dirty secret is

These flatter the writer as the lone expert. Cut the setup and let the claim stand on its own.

Before: *"The part everyone misses: distribution is the real moat."*
After: *"Distribution is the moat."*

---

## Colon reveals

A noun phrase, a colon, then a lowercase dramatic reveal. Use colons for lists, labels, and quotes, not fake drama. Prefer sentence case after a colon unless grammar, a proper noun, a title, or code requires otherwise.

Before: *"The detail that makes it work: a separate agent grades it."*
After: *"A separate agent does the grading, which is what makes it work."*

Before: *"The best part: it learns."*
After: *"It learns as you use it."*

---

## Rule of three

Models force ideas into groups of three to appear comprehensive. Two items or one usually reads better.

Before: *"The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights."*
After: *"The event includes talks and panels, with time for informal networking between sessions."*

---

## Synonym cycling

Repetition penalties cause excessive synonym substitution instead of repeating the right word.

Before: *"The protagonist faces challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home."*
After: *"The protagonist faces many challenges but eventually triumphs and returns home."*

Before: *"The agent reviews the draft. The assistant scores the piece. The tool suggests fixes."*
After: *"The agent reviews the draft, scores it, and suggests fixes."*

---

## False ranges

"From X to Y" where X and Y are not on a meaningful scale.

Before: *"Our journey has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter."*
After: *"The book covers the Big Bang, star formation, and current theories about dark matter."*

---

## Dramatic fragmentation

Stacked fragments for manufactured emphasis.

Before: *"Speed. That's it. That's the whole thing."*
After: *"The only advantage is speed."*

---

## Fake-profound kickers

The closing line that turns the point into a metaphor, aphorism, or mic drop. Delete it. Do not rewrite it into a better metaphor and do not preserve its rhythm. End on the clearest concrete sentence already in the draft, or add a plain takeaway or next action.

Before: *"We shipped the migration in four weeks. In the end, infrastructure is just a promise you make to your future self."*
After: *"We shipped the migration in four weeks."*

---

## Formatting tells

**Em dash overuse.** Commas, periods, or parentheses almost always work better. The Before line below is a specimen of the pattern, not permission to use one.

Before: *"The term is promoted by Dutch institutions—not by the people themselves—even in official documents."*
After: *"The term is promoted by Dutch institutions, not by the people themselves, and appears even in official documents."*

**Boldface overuse.** Mechanical emphasis on phrases that do not need it.

Before: *"It blends **OKRs**, **KPIs**, and visual tools like the **Business Model Canvas**."*
After: *"It blends OKRs, KPIs, and visual tools like the Business Model Canvas."*

**Inline-header bullet lists.** Bold term, colon, sentence.

Before:
```
- **User Experience:** The interface has been improved.
- **Performance:** Algorithms have been optimized.
```
After: *"The update improves the interface and speeds up load times."*

**Title case headings:**
Before: *"## Strategic Negotiations And Global Partnerships"*
After: *"## Strategic negotiations and global partnerships"*

**Emoji in structure:**
Before: `🚀 **Launch Phase:** Q3` and `💡 **Key Insight:** Users prefer simplicity`
After: *"The product launches in Q3. User research showed a preference for simplicity."*

**Fragmented headers.** A heading followed by a one-liner that restates it as a rhetorical warm-up.

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

---

## Filler and hedging

**Filler substitutions:**

| Instead of | Use |
|---|---|
| In order to | To |
| Due to the fact that | Because, since |
| At this point in time | Now |
| In the event that | If |
| Has the ability to | Can |
| Made a decision | Decided |
| It is important to note that | (say the thing) |
| It is worth noting that | (say the thing) |

**Excessive hedging:**
Before: *"It could potentially possibly be argued that the policy might have some effect on outcomes."*
After: *"The policy may affect outcomes."*

In scientific writing, hedging often reflects real epistemic caution. Cut the stacked hedges, keep the single accurate one.

**Generic positive conclusions.** The future looks bright, exciting times lie ahead, journey toward excellence, step in the right direction, continues to thrive.

Before: *"The future looks bright for the company. Exciting times lie ahead as they continue their journey toward excellence."*
After: *"The company plans to open two more locations next year."*

---

## Style habits

**Hyphenated word pair overuse.** Models hyphenate common compound modifiers uniformly; humans are inconsistent. Common over-hyphenated pairs: third-party, cross-functional, client-facing, data-driven, decision-making, well-known, high-quality, real-time, long-term, end-to-end. Technical or unusual compound modifiers are fine to hyphenate.

**Persuasive authority tropes.** The real question is, at its core, in reality, what really matters, fundamentally, the deeper issue, the heart of the matter. These pretend to cut through noise, and the sentence that follows restates an ordinary point with extra ceremony.

Before: *"The real question is whether teams can adapt. At its core, what really matters is organizational readiness."*
After: *"The question is whether teams can adapt. That depends on whether the organization is ready to change its habits."*

**Signposting and announcements.** Let's dive in, let's explore, let's break this down, here's what you need to know, without further ado, in this article we will.

Before: *"Let's dive into how caching works in Next.js. Here's what you need to know."*
After: *"Next.js caches data at multiple layers: request memoization, the data cache, and the router cache."*

**Rhetorical setups.** What if I told you, think about it, plot twist, and self-answered question and answer pairs. Drop them and make the point.

**Chatbot artifacts.** Great question, I hope this helps, happy to help, certainly, as an AI. Cut on sight.
