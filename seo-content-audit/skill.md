# SEO Content Audit Skill

You are running a comprehensive SEO content audit. When this skill is invoked, follow the steps below precisely and completely.

## Invocation

`/seo-content-audit <domain>`

Example: `/seo-content-audit example.com`

---

## Step 1 — Gather Client Context

Ask the user:
1. **What does this client do?** (brief description of their products, services, and target audience)
2. **Are there any content topics that are off-limits to delete?** (e.g. legal pages, cornerstone content)
3. **Output location** — where should the report be saved? Default: `./seo-audit-<domain>-<date>.md`

Wait for answers before proceeding.

---

## Step 2 — Fetch & Parse the Sitemap

Use `WebFetch` to retrieve the sitemap. Try these in order until one works:
- `https://<domain>/sitemap.xml`
- `https://<domain>/sitemap_index.xml`
- `https://www.<domain>/sitemap.xml`

If the sitemap is an index (contains `<sitemap>` tags), fetch each child sitemap and combine all `<loc>` URLs into a single flat list.

Extract every URL from `<loc>` tags. Store the full list. If there are more than 200 URLs, note this and proceed with the full list — do not truncate.

---

## Step 3 — Pull Ahrefs Site-Level Data

Use the Ahrefs MCP to pull an overview of the site. Run these in parallel:
- `site-explorer-metrics` for the domain — get overall DR, organic traffic, keywords
- `site-explorer-pages-by-traffic` — get all pages sorted by traffic (use `limit: 500`)
- `site-explorer-top-pages` — get top pages by traffic

Cross-reference the Ahrefs page list against the sitemap URL list. Note any pages in the sitemap that have zero Ahrefs data (these are likely orphaned or very new).

---

## Step 4 — Per-Page Data Collection

For each URL in the sitemap, collect the following. Batch Ahrefs calls where possible:

**From Ahrefs:**
- `site-explorer-organic-keywords` for the URL — how many keywords it ranks for, top keyword, top keyword position
- `site-explorer-backlinks-stats` for the URL — number of referring domains
- Traffic from the `pages-by-traffic` data pulled in Step 3

**From GSC (if available via Ahrefs GSC tools):**
- `gsc-page-history` for the URL — 6-month traffic trend
- `gsc-pages` for clicks, impressions, CTR, average position

**Direct content fetch:**
- Use `WebFetch` to fetch the page
- Extract: page title, meta description, H1, approximate word count (count words in main body text), and a brief content summary (2-3 sentences describing what the page is actually about)

---

## Step 5 — Score Each Page

Score each page across four dimensions. Use a 1–3 scale for each.

### Traffic Score (1 = bad, 3 = good)
- **1** — Less than 10 monthly organic visits AND traffic has declined or stayed flat over 6 months
- **2** — 10–100 monthly visits OR traffic is declining
- **3** — 100+ monthly visits with stable or growing trend

### Content Depth Score (1 = thin, 3 = substantial)
- **1** — Under 300 words, or mostly boilerplate/list with no substantive information
- **2** — 300–700 words, some useful information but lacks depth
- **3** — 700+ words with substantive, well-structured content

### Relevance Score (1 = irrelevant, 3 = core)
Based on the client description from Step 1:
- **1** — Content has no clear connection to the client's offerings or audience
- **2** — Tangentially related — could serve the audience but isn't core
- **3** — Directly aligned with the client's core products, services, or audience

### Backlink Score (1 = no links, 3 = well-linked)
- **1** — 0 referring domains
- **2** — 1–5 referring domains
- **3** — 6+ referring domains

---

## Step 6 — Classify Each Page

Use the scores to assign a classification:

| Classification | Criteria |
|---|---|
| **DELETE** | Traffic ≤ 1, Relevance = 1, Backlinks = 1. Or: Traffic = 1, Depth = 1, Relevance = 1 regardless of backlinks. These pages offer no value. |
| **DELETE (with redirect check)** | Traffic = 1, Relevance = 1, but Backlinks ≥ 2. Deletion recommended but check if a redirect is needed first. |
| **UPDATE — Relevance** | Relevance = 1 or 2, Traffic ≥ 2, Depth ≥ 2. Page has traffic but isn't aligned — consider repositioning or rewriting. |
| **UPDATE — Thin** | Depth = 1 or 2, Relevance = 3, Traffic ≤ 2. Page is on-topic but needs more substance to compete. |
| **UPDATE — Decaying** | Traffic = 1 (was higher based on trend), Depth ≥ 2, Relevance ≥ 2. Page used to perform but is fading — needs a refresh. |
| **CONSOLIDATE** | Multiple pages on the same or very similar topic. Flag the group and suggest a canonical target. |
| **KEEP** | Traffic ≥ 2, Relevance ≥ 2, Depth ≥ 2. Page is performing and relevant — leave it alone. |

---

## Step 7 — Generate Report

### Console Summary (print inline in chat)

Print a brief summary:
- Total URLs audited
- Counts per classification (DELETE, UPDATE, CONSOLIDATE, KEEP)
- Top 5 deletion candidates (URL + one-line reason)
- Top 5 update candidates (URL + one-line reason)
- Any consolidation clusters found

### Full Report (save to file)

Save a full markdown report to the path agreed in Step 1. Structure:

```
# SEO Content Audit — <domain>
Date: <date>
Audited by: Claude + Ahrefs MCP

## Client Context
<what the client does, from Step 1>

## Summary
| Classification | Count |
|---|---|
| DELETE | N |
| DELETE (redirect check) | N |
| UPDATE — Relevance | N |
| UPDATE — Thin | N |
| UPDATE — Decaying | N |
| CONSOLIDATE | N |
| KEEP | N |
| **Total** | N |

## Domain Overview
- Domain Rating: X
- Total organic traffic: X/mo
- Total organic keywords: X
- Total URLs in sitemap: X

---

## Pages to DELETE

| URL | Traffic/mo | Referring Domains | Reason |
|---|---|---|---|
| ... | ... | ... | ... |

---

## Pages to DELETE (check redirect first)

| URL | Traffic/mo | Referring Domains | Reason |
|---|---|---|---|

---

## Pages to UPDATE — Decaying Traffic

| URL | Traffic/mo | Traffic Trend | Top Keyword | Reason |
|---|---|---|---|---|

---

## Pages to UPDATE — Thin Content

| URL | Word Count | Traffic/mo | Top Keyword | Reason |
|---|---|---|---|---|

---

## Pages to UPDATE — Relevance Issues

| URL | Traffic/mo | Top Keyword | Issue |
|---|---|---|---|

---

## Consolidation Candidates

Group by cluster. For each cluster:
- List all URLs in the cluster
- Recommended canonical URL to keep
- Suggested action for the others (redirect to canonical)

---

## Pages to KEEP

| URL | Traffic/mo | Top Keyword | Notes |
|---|---|---|---|

---

## Methodology Notes
- Traffic data source: Ahrefs
- GSC data: [included / not available]
- Sitemap parsed: <url>
- Total URLs in sitemap: N
- Date of data: <date>
```

---

## Important Notes

- **Never skip the content fetch** — always read the actual page before scoring. Ahrefs data alone is not enough to judge quality or relevance.
- **Flag uncertainty** — if you can't determine relevance for a page, mark it as "REVIEW NEEDED" rather than guessing.
- **Respect the off-limits list** from Step 1 — never classify those pages as DELETE regardless of scores.
- **Backlinks protect pages** — always note referring domains before recommending deletion. Pages with backlinks should default to UPDATE before DELETE.
- If `WebFetch` fails for a URL (404, timeout, redirect loop), note it in the report as a potential broken/orphaned page — these are often strong DELETE candidates.
- If Ahrefs returns no data for a URL, note it but still fetch and score the content directly.
