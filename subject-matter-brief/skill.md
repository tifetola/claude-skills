# Subject Matter Brief

Build enough domain knowledge on the product, service, or topic to avoid writing shallow, inaccurate, or operationally useless content. AI without this step produces technically plausible but practically wrong content — feature names that don't exist, integrations that aren't real, comparisons that miss the point.

## Invocation

`/subject-matter-brief <product or topic>`

Example: `/subject-matter-brief HubSpot CRM`
Example: `/subject-matter-brief customer onboarding SaaS`

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **What is this content for?** (product being written about, audience, and content type)
2. **Are there any specific claims, features, or comparisons this content needs to make?** (list anything that requires factual accuracy — pricing, integrations, plan tiers, capabilities)
3. **Are there known competitor products involved?** (if comparison or alternatives content)

---

## Step 2 — Primary Source Research

Go to the source. Do not rely on training data for product-specific facts — it goes stale fast.

Run WebFetch on the following, in parallel where possible:

**For product/tool content:**
- The product's homepage
- The product's pricing page
- The product's features page(s) or capabilities page
- The product's integrations page (if relevant to the content)
- Any comparison pages the product itself publishes

**For topic/concept content:**
- 2–3 authoritative sources on the topic (industry publications, practitioner blogs, academic/research sources)
- The Wikipedia article if one exists (for definitional accuracy)

Extract from what you read:
- Core value proposition (what problem does this solve, for whom)
- Actual feature names (exact names as the product calls them — not paraphrases)
- Pricing tiers and what's included at each level (note the date — pricing changes)
- Key integrations (what it connects to natively vs. via Zapier/API)
- Positioning claims the product makes about itself
- Known limitations or things it explicitly does not do

---

## Step 3 — Competitor Cross-Check (if relevant)

If competitors are involved in the content (comparison, alternatives, pricing page):

Use WebFetch to check the competitor's own site for:
- Their current pricing (same date caveat)
- Feature differentiation claims they make
- Integration list

Do not make feature comparison claims from memory. If you can't verify a claim from a live source, flag it as "needs verification."

---

## Step 4 — Buyer Pain Point Mapping

Based on what you've read (and any Reddit/review research from the research synthesis step), map:

**What buyers value most about this product** — the outcomes they care about, not the features
**What buyers complain about** — real friction points from G2, Capterra, Reddit, Trustpilot, or app store reviews
**What buyers compare this against** — the alternatives they actually consider
**Where buyers get confused** — pricing tiers, limitations, setup complexity, anything that creates objections

Run a quick WebSearch for `[product] reviews` and `[product] reddit` to supplement if you don't have this from research synthesis.

---

## Step 5 — Accuracy Checklist

Before writing anything, confirm you have verified (or flagged as unverified):

- [ ] Product name spelled correctly (including capitalisation — "HubSpot" not "Hubspot")
- [ ] Feature names are the product's actual names, not paraphrases
- [ ] Pricing reflects current published pricing (note the date)
- [ ] Integration claims are based on the product's actual integration page
- [ ] No capability claims that can't be traced to the product's own documentation
- [ ] Competitor claims are sourced from competitor's own site (not memory)

Anything that cannot be verified from a live source gets flagged with [VERIFY] in the brief.

---

## Output

Print this block in full:

```
## Subject Matter Brief — [product/topic]
Date: [today's date]
Sources checked: [list URLs]

### Product Overview
- What it is: [one sentence]
- Core value proposition: [what problem, for whom]
- Primary audience: [who buys this]

### Feature Inventory (verified)
- [Feature name — exact]: [what it does, which plan it's on]
- [Feature name — exact]: [what it does, which plan it's on]
- [Add as many as relevant]

### Pricing (as of [date])
| Plan | Price | Key inclusions |
|---|---|---|
| [Plan name] | [$/mo] | [features] |

### Integrations (verified)
- Native: [list key ones]
- Via Zapier/Make: [note if applicable]
- API: [yes/no]

### Buyer Pain Points
- Values: [what buyers love / outcomes they get]
- Complaints: [real friction points from reviews]
- Objections: [common hesitations before buying]
- Alternatives considered: [what they compare this against]

### Known Limitations
- [What this product explicitly does not do or does poorly]

### Accuracy Flags
- [VERIFY]: [anything that could not be confirmed from a live source]
```

---

## Standalone Save

If invoked directly, ask:
"Save to file? Default: `./brief-[product-slug]-[date].md`"
Wait for confirmation, then save.
