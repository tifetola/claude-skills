# On-Page SEO Execution

Package the content correctly for search. Good content with weak on-page SEO loses rankings to weaker content that's better packaged. This step covers titles, headings, semantic structure, snippet optimisation, entities, and FAQs.

## Invocation

`/on-page-seo <keyword>`

Then paste the content you want to optimise.

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **What is the primary keyword?** (and any secondary keywords or variants to work in naturally)
2. **What is the content format?** (listicle, guide, comparison, landing page, etc.)
3. **Paste the content.**
4. **Is there an existing title tag and meta description to keep or replace?** (optional)

---

## Step 2 — Title Tag

Write three title tag options. Rules:
- Primary keyword must appear, ideally near the front
- Under 60 characters (to avoid truncation in SERPs)
- No keyword stuffing — must read naturally
- Must accurately describe the content — no clickbait that the content doesn't deliver
- Match the intent: informational titles don't oversell, commercial titles don't undersell

Rate each option on: keyword position, character count, click appeal, and accuracy.
Recommend one.

---

## Step 3 — H1

Write the H1. It should:
- Include the primary keyword (or a close variant)
- Be different from the title tag (the H1 can be longer and more descriptive)
- Immediately communicate what the reader gets
- Not be a generic label — it should feel like the start of a conversation with the reader

One H1 per page. No H1 that's just the keyword phrase with nothing added.

---

## Step 4 — Heading Structure Audit

Review all existing H2s and H3s in the content:

**Semantic relevance**: Do the headings contain the terms and phrases a reader would use to search for that specific section?

**Keyword distribution**: Is the primary keyword or natural variants present across headings — or is it clustered in only one section?

**Heading quality**: Do the headings describe what's in the section specifically enough that a skimmer can understand the content without reading the body? Vague headings ("More Features", "Other Considerations") are weak.

**Heading hierarchy**: Is the H2 → H3 logic sound? No H3 that's a bigger topic than its parent H2.

Rewrite any headings that fail these checks. Mark rewrites clearly.

---

## Step 5 — Snippet Optimisation

Identify the sections most likely to be pulled as a featured snippet for the primary keyword. Featured snippet formats:

**Paragraph snippet** (for "what is" and definitional queries): The answer must appear as a clean, self-contained paragraph of 40–60 words near the top of the page. It should directly answer the question without preamble.

**List snippet** (for "how to" or "best X" queries): A bulleted or numbered list that answers the query. List items should be concise (under 8 words each ideally) and the list should have 5–8 items.

**Table snippet** (for comparison queries): A clean comparison table with a keyword-relevant column header in the first column.

For the most likely snippet format, review whether the existing content is structured to capture it. If not, recommend the exact edit needed.

---

## Step 6 — Entity Optimisation

Entities are the named things in a piece of content — products, companies, people, places, concepts, standards. Google uses entities to understand topical relevance and depth.

Review the content for:
- Are the key entities for this topic present? (e.g. for "best CRM software" — the major CRM product names should appear, not vague references)
- Are entities named consistently and correctly? (capitalization, exact product names)
- Are related entities present that signal topical authority? (e.g. for a content strategy article — naming specific frameworks, tools, and authors in the space signals depth)
- Are there any critical entities missing that would make this feel thin to a topical authority check?

List any entities that should be added or any that are named incorrectly.

---

## Step 7 — Internal Linking Opportunities

Identify logical internal linking placements:
- Terms or concepts mentioned in the content that should link to a dedicated page on the site
- Related content that would be useful for the reader at key decision points

Note: Do not invent URLs. List the anchor text and the concept/page that should be linked to. The user will verify URLs.

---

## Step 8 — FAQ Section

Determine whether an FAQ section belongs in this content.

An FAQ is worth adding when:
- The People Also Ask questions on the SERP are not answered elsewhere in the content
- The content format naturally raises questions the body doesn't resolve
- The keyword triggers PAA boxes with high-volume sub-questions

If adding an FAQ:
- Write 4–6 questions that are actual questions people search (not made-up softballs)
- Keep each answer to 40–70 words — enough to be useful, formatted for a snippet
- Q&A format, not essay format

If no FAQ is needed: state why and skip.

---

## Step 9 — Meta Description

Write one meta description:
- 140–155 characters
- Must include the primary keyword naturally
- Must describe what the page delivers — not be a generic teaser
- Include a reason to click: specificity, a key benefit, or a direct answer preview
- No quotes or special characters that render poorly in SERPs

---

## Output

Print this block in full:

```
## On-Page SEO — [keyword]
Date: [today's date]

### Title Tag Options
1. [Title] ([X] chars) — [rating: keyword position / click appeal / accuracy]
2. [Title] ([X] chars) — [rating]
3. [Title] ([X] chars) — [rating]
**Recommended:** Option [N]

### H1
[H1 text]

### Heading Changes
- [Original H2] → [Revised H2] — [reason]
- [Original H3] → [Revised H3] — [reason]
- (list only changes — unchanged headings don't need to appear)

### Snippet Opportunity
- Most likely snippet type: [paragraph / list / table]
- Current state: [captures it / nearly there / missing]
- Edit needed: [exact copy change or "none needed"]

### Entity Gaps
- Missing entities to add: [list]
- Incorrectly named entities: [list with corrections]
- Related entities to include for topical depth: [list]

### Internal Linking Opportunities
- Anchor: "[text]" → links to: [concept/page]
- Anchor: "[text]" → links to: [concept/page]

### FAQ Section
[Include full FAQ if recommended, or "Not needed — [reason]"]

### Meta Description
[Final meta description text] ([X] chars)
```

Then output the **full revised content** with all on-page changes applied (updated title, H1, headings, FAQ added if applicable). Mark changed headings with a comment if desired.

---

## Standalone Save

If invoked directly, ask:
"Save the revised content to file? Default: `./seo-[keyword-slug]-[date].md`"
Wait for confirmation, then save.
