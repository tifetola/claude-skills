# Keyword Research Skill

You are running a deep-dive keyword research session for a client. When invoked, follow every step in order. The output is a prioritised list of ~100 keywords with no cannibalization, split across five bottom-funnel content categories.

## Invocation

`/keyword-research <domain>`

Example: `/keyword-research proposify.com`

---

## Step 1 — Gather Client Context

Ask the user two questions in one go:

1. **Do you have any additional context about this client?** (ICP, key use cases, target markets, geography, known competitors, things to avoid, goals). If they say no, proceed from the website alone.
2. **Output location** — where should the report be saved? Default: `./keyword-research-<domain>-<date>.md`

Wait for their answer before proceeding.

---

## Step 2 — Understand the Client

Run the following **in parallel**:

**A. Crawl the website**
Use `WebFetch` to fetch the homepage (`https://<domain>`). Extract:
- What the product/service actually is (in plain English)
- The core value proposition
- Who the target customer is (ICP)
- Key features or capabilities mentioned
- Any industry verticals or use cases highlighted
- Pricing model if visible (e.g. per seat, flat rate, usage-based)

Then fetch 2–3 additional pages that look most useful for understanding the product — e.g. `/features`, `/pricing`, `/solutions`, `/use-cases`, `/about`. Use `WebFetch` for each.

**B. Pull Ahrefs site-level data**
Run these in parallel using the Ahrefs MCP:
- `site-explorer-metrics` for the domain — DR, organic traffic, keyword count
- `site-explorer-organic-keywords` for the domain — top 50 keywords the site already ranks for (to understand positioning and avoid duplication)
- `site-explorer-organic-competitors` — top 10 organic competitors
- `site-explorer-top-pages` — top 10 pages by traffic (to understand what content already works)

**C. Identify competitors**
From the Ahrefs competitor list and anything mentioned on the site, build a list of up to **8 direct competitors**. These will be used for competitor keyword categories. Confirm this list makes sense given what you learned in the web crawl.

After running all three in parallel, synthesise what you've learned into a **Client Intelligence Summary** (print this to the user before proceeding):

```
## Client Intelligence Summary

**Product:** [what it is]
**ICP:** [who buys it]
**Core use cases:** [list]
**Key features/differentiators:** [list]
**Target verticals/industries:** [list]
**Current organic footprint:** [DR, monthly traffic, keyword count]
**Top competitors identified:** [list of up to 8]
**Already ranking for:** [top 10 most relevant keywords they already rank for]
```

Ask the user: "Does this look right, or anything to add/correct before I start keyword research?"

Wait for confirmation before proceeding to Step 3.

---

## Step 3 — Keyword Research by Category

Research keywords across **five categories**. Run as many Ahrefs calls in parallel as possible. For every keyword, you will need: **global search volume**, keyword difficulty (KD), and search intent.

Use `keywords-explorer-overview` to get volume and KD for specific keyword lists. Use `keywords-explorer-matching-terms` and `keywords-explorer-related-terms` to discover candidates. Always use **global** volume (not country-specific) unless the client is explicitly local-only.

Target **~20 keywords per category** (adjust slightly to hit ~100 total).

---

### Category 1 — Product Listicles

**Goal:** Rank for "best X" and "top X" queries where buyers are building shortlists. These are high-converting because the reader is in active evaluation mode. This is also the primary AEO/LLM citation surface — AI engines heavily cite "best X" content.

**Seed patterns to research:**
- `best [product category] software`
- `best [product category] tools`
- `top [product category] platforms`
- `best [product category] for [ICP role]`
- `best [product category] for [industry vertical]`
- `best [product category] for [company size: startups / enterprise / small business]`
- `[product category] software comparison`
- `[product category] tools list`

**Research method:**
- Run `keywords-explorer-matching-terms` with seeds like "best [category]", "top [category]" with `include` filter set to the core product noun
- Run `keywords-explorer-related-terms` on the client's top-traffic keyword to surface related listicle terms
- Filter: global volume ≥ 100/mo, relevance to client's ICP is high

---

### Category 2 — Foundational Landing Pages

**Goal:** Pages the client should own permanently — feature pages, use case pages, industry pages. These establish topical authority and are cited by AI engines for specific capability queries.

**Sub-types to cover (aim for a mix):**

**Features/capabilities** (~5 keywords):
- `[core feature] software`
- `[specific capability] tool`
- `software with [feature]`

**Use cases** (~5 keywords):
- `[product] for [use case]`
- `[use case] software`
- `how to [job to be done]`

**Industries/verticals** (~5 keywords):
- `[product category] for [industry]`
- `[industry] [product category] software`

**Pain-point / problem-aware** (~5 keywords):
- `how to [solve the problem the product solves]`
- `[problem] solution`
- Queries a buyer types when they know they have a problem but haven't found the product yet

**Research method:**
- Use `keywords-explorer-matching-terms` with feature names, use case verbs, industry names
- Cross-reference with the client's top pages to find gaps

---

### Category 3 — Competitor Alternatives

**Goal:** Capture buyers who are unhappy with a competitor and looking to switch. These are the highest-intent queries on the internet for B2B SaaS — the searcher is already using a paid tool and wants out.

**Patterns for each of the top 5–8 competitors:**
- `[competitor] alternatives`
- `alternatives to [competitor]`
- `[competitor] alternative for [ICP]`
- `best [competitor] alternatives`

**Research method:**
- Run `keywords-explorer-matching-terms` with each competitor name + "alternative" as include filter
- Prioritise competitors with the highest search volume on their alternatives query
- Aim for 3–5 keywords per major competitor, fewer for smaller ones
- Target: global volume ≥ 50/mo (alternatives queries are high-intent even at low volume)

---

### Category 4 — Competitor Pricing

**Goal:** Capture buyers deep in the evaluation funnel researching costs before a purchase decision. Pricing pages also appear frequently in AI Overview citations.

**Patterns for each competitor:**
- `[competitor] pricing`
- `[competitor] cost`
- `how much does [competitor] cost`
- `[competitor] price`
- `[competitor] pricing plans`

**Research method:**
- Run `keywords-explorer-overview` for `[competitor] pricing` for each of the top 6–8 competitors
- Only include if global volume ≥ 50/mo
- Aim for 1–2 pricing keywords per major competitor

---

### Category 5 — Competitor Comparisons

**Goal:** Capture buyers who are actively comparing two specific tools. These convert extremely well because the reader has already shortlisted to two options.

**Patterns:**
- `[client brand] vs [competitor]`
- `[competitor] vs [client brand]`
- `[competitor A] vs [competitor B]` (for roundup comparison content where the client can insert themselves)

**Research method:**
- Run `keywords-explorer-matching-terms` with the client's brand name + "vs" as include filter
- Run `keywords-explorer-matching-terms` with competitor names + "vs [other competitor]" to find high-volume head-to-head queries the client can rank for with comparison content
- Prioritise: any "vs" query with global volume ≥ 100/mo; include lower-volume if the competitor is a named target

---

## Step 4 — Deduplicate and Cannibalization Check

Before finalising the list:

1. **Remove duplicates** — same keyword appearing in two categories should be kept only in the most appropriate one.
2. **Check for cannibalization clusters** — if two keywords have nearly identical intent (e.g. "best proposal software" and "top proposal software tools"), keep only the higher-volume one OR note them as a consolidation pair (one page can target both).
3. **Remove keywords the client already ranks for in position 1–5** — these are wins, not opportunities. Check against the Ahrefs data from Step 2.
4. **Remove brand keywords** — pure brand searches (e.g. "[client name] login") are not content opportunities.
5. **Relevance filter** — cut any keyword where a reader finding that article would not plausibly convert into a customer for this client. Be strict.

After filtering, if you are below 100 keywords, run additional `keywords-explorer-matching-terms` calls to top up. If above 100, cut the lowest-relevance keywords first.

---

## Step 5 — Score and Prioritise Each Keyword

For each final keyword, assign a **Priority Score (1–3)**:

| Score | Criteria |
|---|---|
| **3 — High** | Global volume ≥ 500/mo AND KD ≤ 50 AND directly maps to client's core product/ICP |
| **2 — Medium** | Volume 100–500/mo OR KD 51–70 OR one degree from core ICP |
| **1 — Low** | Volume < 100/mo OR KD > 70 OR niche vertical play |

Always note where a low-volume keyword should still be prioritised because of very high buyer intent (e.g. competitor pricing queries at 50/mo are worth targeting).

---

## Step 6 — Generate Report

### Console Summary (print inline)

```
## Keyword Research Summary — <domain>

**Total keywords:** 100
**Category breakdown:**
- Product Listicles: N
- Foundational Landing Pages: N
- Competitor Alternatives: N
- Competitor Pricing: N
- Competitor Comparisons: N

**Priority 3 (High):** N keywords
**Priority 2 (Medium):** N keywords
**Priority 1 (Low / niche):** N keywords

**Quick wins (high priority, low KD):**
[Top 5 keywords with best opportunity score]

**Cannibalization notes:**
[Any pairs flagged as consolidation candidates]
```

### Full Report (save to file)

Save to the agreed path. Structure:

```markdown
# Keyword Research — <domain>
Date: <date>
Researched by: Claude + Ahrefs MCP

## Client Summary
[Paste the Client Intelligence Summary from Step 2]

## Keyword List

### Category 1 — Product Listicles

| # | Keyword | Global Volume | KD | Priority | Notes |
|---|---|---|---|---|---|
| 1 | ... | ... | ... | ... | ... |

### Category 2 — Foundational Landing Pages

#### Features / Capabilities
| # | Keyword | Global Volume | KD | Priority | Notes |
|---|---|---|---|---|---|

#### Use Cases
| # | Keyword | Global Volume | KD | Priority | Notes |
|---|---|---|---|---|---|

#### Industries / Verticals
| # | Keyword | Global Volume | KD | Priority | Notes |
|---|---|---|---|---|---|

#### Pain-Point / Problem-Aware
| # | Keyword | Global Volume | KD | Priority | Notes |
|---|---|---|---|---|---|

### Category 3 — Competitor Alternatives

| # | Keyword | Global Volume | KD | Priority | Competitor | Notes |
|---|---|---|---|---|---|---|

### Category 4 — Competitor Pricing

| # | Keyword | Global Volume | KD | Priority | Competitor | Notes |
|---|---|---|---|---|---|---|

### Category 5 — Competitor Comparisons

| # | Keyword | Global Volume | KD | Priority | Notes |
|---|---|---|---|---|---|

---

## Cannibalization & Consolidation Notes

[List any keyword pairs/clusters that should be targeted on a single page]

## Keywords Already Ranking (excluded)

[List of keywords removed because client already ranks positions 1–5]

## Methodology Notes
- Volume source: Ahrefs global search volume
- KD source: Ahrefs keyword difficulty
- Date of data: <date>
- Competitors researched: [list]
```

---

## Important Rules

- **Never invent volume data** — all volume and KD figures must come from Ahrefs API calls, not estimated.
- **Relevance over volume** — a 200/mo keyword directly relevant to the client's ICP beats a 5,000/mo keyword that attracts the wrong audience.
- **Global volume is default** — only use country-specific volume if the client explicitly targets one market.
- **No cannibalization** — each keyword in the final list should map to a distinct page. If two keywords should share a page, note it but count them as one entry.
- **Competitors must be real** — only research competitors identified from Ahrefs data or confirmed by the user. Do not assume.
- **Flag low-data situations** — if Ahrefs returns no data for a keyword, note it clearly rather than omitting silently.
- **AEO note** — Category 1 (listicles) and Category 3 (alternatives) are the highest-priority AEO surfaces. Explicitly call this out in the report intro.
