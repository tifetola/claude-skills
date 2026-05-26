# Research Synthesis

Consume multiple sources on a topic and produce something sharper than any individual source. The goal is not to summarise — it is to find the consensus, the contradictions, the missing angles, and the perspective that makes this content worth reading.

## Invocation

`/research-synthesis <keyword or topic>`

Example: `/research-synthesis best practices for onboarding new SaaS customers`

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **What is this content for?** (product, service, audience — the lens through which to filter relevance)
2. **What format is this content?** (listicle, how-to, comparison, etc. — shapes what research is useful)
3. **Paste your content strategy brief if you have one.** If not, describe the angle and scope.

---

## Step 2 — Source Gathering

Run the following searches in parallel using WebSearch:

- The main keyword / topic
- `[topic] expert opinion`
- `[topic] case study`
- `[topic] data` or `[topic] statistics` or `[topic] research`
- `[topic] mistakes` or `[topic] problems` or `[topic] what nobody tells you`
- `[topic] reddit` or `[topic] forum` — real practitioner experience

Use WebFetch to read 5–8 sources. Prioritise:
- Practitioner-written content (people who've done this, not just written about it)
- Data-backed claims with sources
- Critical or contrarian perspectives
- Recent content (last 12–18 months for anything in a fast-moving space)

Skip:
- Thin vendor content that exists solely to funnel to a CTA
- Listicles that are just reworded copies of other listicles
- Anything that doesn't cite a source for factual claims

---

## Step 3 — Synthesis Analysis

After reading all sources, work through each of these:

**Consensus: What do most credible sources agree on?**
These are the baseline facts, accepted best practices, and settled questions. List them. These belong in the content but don't differentiate it.

**Contradictions: Where do sources genuinely disagree?**
Disagreements are often where the most valuable content lives. For each contradiction found:
- State both positions clearly
- Who holds each position and why?
- What's the most defensible resolution — or is the tension real and worth surfacing?

**Missing Angles: What does nobody cover adequately?**
- Questions that multiple sources raise but none answer well
- The "what about X?" that readers will think of but the content ignores
- The edge cases, exceptions, or caveats that get glossed over
- Practical implementation depth that stays at theory level across most sources

**Stronger Perspective: What's the sharper, more honest version?**
After reading all of this, what is the most useful, direct, accurate thing you can say about this topic that most sources either hedge, miss, or avoid? This becomes the point-of-view the content leads with.

**Quotes and Data Worth Using**
List any specific statistics, findings, or quotes that are:
- Recent (within 2 years for fast-moving topics)
- From a named, credible source
- Specific enough to be useful (not "studies show" generics)
- Relevant to the actual piece being written

Do not include any statistic or claim you cannot trace to a real, named source in the material you've read.

---

## Step 4 — Source Quality Assessment

For each source you used, note:
- Source name / URL
- Type: (practitioner / researcher / vendor / community / news)
- Reliability: (High / Medium / Low — based on specificity, sourcing, and author credibility)
- Key insight extracted

---

## Output

Print this block in full:

```
## Research Synthesis — [keyword/topic]
Date: [today's date]

### Consensus (what's settled)
- [Point]
- [Point]
- [Point]

### Contradictions (where sources disagree)
1. [Contradiction] — [Position A vs Position B] — [Recommended resolution or honest tension to surface]
2. [Contradiction if found]

### Missing Angles (what nobody covers well)
1. [Gap — specific]
2. [Gap]
3. [Gap]

### The Stronger Perspective
[1–2 paragraphs: the most honest, direct, useful thing to say about this topic — the point-of-view that the content should lead with or be structured around]

### Usable Data and Quotes
- "[Statistic or quote]" — [Source name, year]
- "[Statistic or quote]" — [Source name, year]
- (only include if traceable to a real named source)

### Sources Used
| Source | Type | Reliability | Key insight |
|---|---|---|---|
| [name/url] | [type] | [H/M/L] | [insight] |
```

---

## Standalone Save

If invoked directly, ask:
"Save to file? Default: `./research-[topic-slug]-[date].md`"
Wait for confirmation, then save.
