# SERP Intelligence

Reverse-engineer what Google is currently rewarding for a keyword. Understand the format, depth, structure, and gaps in the top-ranking content — so you can beat it, not clone it.

## Invocation

`/serp-intelligence <keyword>`

Example: `/serp-intelligence best CRM for small business`

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **What is the intent behind this keyword?** (paste from intent analysis if available, or describe briefly)
2. **What product or service is this content for?** (helps identify content gaps and relevance signals)

---

## Step 2 — SERP Snapshot

Run a WebSearch for the exact keyword. Note:
- Which result types dominate: articles, listicles, comparison pages, product pages, tools, videos, featured snippets?
- Is there a featured snippet? If so, what format is it — paragraph, list, table?
- Are there People Also Ask questions visible? List them.
- What are the top 3–5 organic result titles?
- Are there ads? How many? (Signals commercial intent intensity)
- Do results look fresh (recent dates) or old (no dates)?

Run a second search for `[keyword] site:reddit.com` and a third for `[keyword] -site:[common vendors]` to see non-vendor perspectives.

---

## Step 3 — Top Page Analysis

Use WebFetch to read the top 5 organic results (skip YouTube, Reddit, and pure product pages for this analysis unless they dominate the SERP).

For each page, extract and record:

**Format & Structure**
- What content format is it? (listicle, guide, comparison, landing page, tool, glossary)
- What is the H1?
- List the H2s in order — these reveal the structural template Google prefers
- Does it use tables, comparison grids, or visual elements?
- Approximate word count (short = under 1000, medium = 1000–2500, long = 2500+)

**Depth & Approach**
- Does it answer the question immediately or build up slowly?
- Is it specific and detailed or vague and general?
- What's the primary proof mechanism: case studies, data, screenshots, expert quotes, brand authority?
- What makes this page's angle different from the others (or does every page say the same thing)?

**Conversion & Intent Handling**
- Does the page push toward a product/CTA or is it purely editorial?
- Is there a clear winner/recommendation or does it stay deliberately neutral?

---

## Step 4 — Pattern Extraction

After reading all five pages, identify the patterns:

**What Google Is Rewarding**
- Format Google is clearly preferring (e.g. "10 best X" listicle with feature breakdowns)
- Sections that appear in 3+ of the top 5 results (structural consensus)
- Depth standard: what level of detail do top results go to?
- Freshness signals: are top results regularly updated? Are dates prominent?
- Snippet structure: if there's a featured snippet, what exact format does it use?

**Entity Patterns**
- What products, brands, tools, or named concepts appear across multiple top results?
- What are they being compared against?
- Are there any industry-specific terms or frameworks that recur?

**Content Gaps**
What is missing or weak across the top 5 results? Look for:
- Questions raised but not fully answered
- Perspectives that nobody covers (e.g. enterprise vs. SMB view, specific industries, edge cases)
- Outdated information that hasn't been refreshed
- Opinions or recommendations that are hedged to the point of uselessness
- Missing practical depth (e.g. "how to implement" after "why to use")
- Anything a reader would need to search a second time to get

---

## Step 5 — Opportunity Assessment

Rate this keyword's content opportunity across three dimensions:

**Format Opportunity (High / Medium / Low)**
Is there a better format that Google hasn't fully rewarded yet, or is the current format clearly locked in?

**Depth Opportunity (High / Medium / Low)**
Is there a clear gap between what's ranking and what a truly thorough piece would cover?

**Angle Opportunity (High / Medium / Low)**
Is there a differentiated angle, perspective, or positioning that none of the top results takes?

---

## Output

Print this block in full:

```
## SERP Intelligence — [keyword]
Date: [today's date]

### SERP Landscape
- Dominant format: [listicle / comparison / guide / landing page / mixed]
- Featured snippet: [yes — format: paragraph/list/table | no]
- People Also Ask questions:
  1. [question]
  2. [question]
  3. [question]
- Top result titles:
  1. [title]
  2. [title]
  3. [title]
  4. [title]
  5. [title]
- Freshness signals: [most results dated / undated / actively maintained]
- Commercial intent signals: [ads present / no ads / heavy ads]

### Structural Consensus (sections appearing in 3+ top results)
- [Section name]
- [Section name]
- [Section name]
- [Section name]

### Format Google Is Rewarding
[2–3 sentences describing the format, depth, and structure of top results]

### Entity Patterns
- Products/tools named across multiple results: [list]
- Recurring comparison framing: [e.g. "X vs Y" or "for small business vs enterprise"]
- Industry terms or frameworks that recur: [list]

### Content Gaps Found
1. [Gap — be specific. What's missing and why it matters]
2. [Gap]
3. [Gap]
4. [Gap if found]

### Opportunity Assessment
- Format opportunity: [High / Medium / Low] — [one line reason]
- Depth opportunity: [High / Medium / Low] — [one line reason]
- Angle opportunity: [High / Medium / Low] — [one line reason]

### Winning Recommendation
[2–3 sentences: the format, depth, and angle that gives this piece the best chance to rank and actually satisfy readers better than what's there]
```

---

## Standalone Save

If invoked directly, ask:
"Save to file? Default: `./serp-[keyword-slug]-[date].md`"
Wait for confirmation, then save.
