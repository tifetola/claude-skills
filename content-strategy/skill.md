# Content Strategy

Determine the right content format for a keyword. Wrong format = weak outcome regardless of how good the writing is. This skill makes the format decision explicit before a word gets written.

## Invocation

`/content-strategy <keyword>`

Example: `/content-strategy monday.com alternatives`

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **Paste your intent analysis and SERP intelligence if you have them.** If not, describe the keyword's intent and what you know about what's currently ranking.
2. **What product or service is this content for?** What's the commercial goal — drive signups, inform buyers, rank for brand terms?

---

## Step 2 — Format Mapping

Using the intent analysis and SERP intelligence, determine the correct content format from this list:

| Format | When to use it |
|---|---|
| **Listicle** | "Best X" or "Top X" — buyer is building a shortlist |
| **Alternatives page** | "[Competitor] alternatives" — buyer wants to switch |
| **Comparison page** | "[A] vs [B]" — buyer is deciding between two known options |
| **How-to / Guide** | "How to X" — instructional, step-based content |
| **Explainer / Glossary** | "What is X" — definitional, informational, building understanding |
| **Use case page** | "[Product] for [use case]" — connecting product to a specific job |
| **Landing page** | High-commercial keyword, conversion is the primary goal |
| **Pricing page** | "[Competitor] pricing" — buyer researching cost before committing |
| **Integration page** | "[Product A] + [Product B]" — connecting two tools |
| **Problem/solution page** | Pain-point aware query — problem first, solution second |
| **Review page** | "[Product] review" — validation-seeking buyer |
| **Roundup / Comparison hub** | Multiple products evaluated on criteria |

If the format is unclear, look at what the top 3 SERP results chose and whether there's a reason to deviate.

---

## Step 3 — Format Justification

For the chosen format, answer:

**Why this format?**
What about the intent and SERP pattern makes this the correct choice?

**What would go wrong with a different format?**
Pick the most tempting alternative format and explain why it would underperform.

**Are there hybrid signals?**
Some keywords need a hybrid (e.g. a listicle that opens with an explainer section). If so, define the primary format and the secondary element.

---

## Step 4 — Angle and Positioning

The format is what it is. The angle is what makes it the best version.

Determine:

**Primary angle**: What is the single strongest, most differentiated framing for this piece?

Options to consider:
- Deeper / more honest than competitors (no fluff, real comparisons)
- More specific (targeting a sub-audience competitors treat generically)
- More current (competitors are outdated, we lead with recency)
- Stronger opinion (competitors hedge everything, we make real recommendations)
- More practical (competitors explain what, we explain how)
- More buyer-focused (competitors feature-dump, we speak to outcomes)

**Positioning against SERP**: What will make a reader choose this result over the existing top 3?

---

## Step 5 — Scope Definition

Define the boundaries of this piece:

**In scope**: What this article covers
**Out of scope**: What it explicitly does not cover (prevents bloat and keeps it tight)
**Target depth**: Short (500–1000w) / Medium (1000–2000w) / Long (2000–3500w) / Exhaustive (3500w+)

Depth should match the searcher's expectations and the competitive standard — not exceed it arbitrarily, and not fall short of it.

**Primary CTA**: What should the reader do at the end? (Start trial / book demo / read related article / no CTA — purely informational)

---

## Output

Print this block in full:

```
## Content Strategy — [keyword]
Date: [today's date]

**Format:** [chosen format]
**Angle:** [one sentence — the differentiated positioning]

### Format Justification
[2–3 sentences: why this format, what breaks with alternatives]

### Hybrid Elements (if any)
[Describe any secondary format element, or "none"]

### Scope
- In scope: [bullet list]
- Out of scope: [bullet list]
- Target depth: [word range]
- Primary CTA: [action or "none — purely informational"]

### Positioning Statement
[2–3 sentences: what makes this piece earn the click over existing results, who it's specifically for, and what it delivers that competitors don't]
```

---

## Standalone Save

If invoked directly, ask:
"Save to file? Default: `./strategy-[keyword-slug]-[date].md`"
Wait for confirmation, then save.
