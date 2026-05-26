# Fact Check

Verify every factual claim in the content before it publishes. AI gets product claims, pricing, integrations, stats, and feature availability wrong constantly. These errors damage credibility and can cause real-world harm for buyers who act on them.

## Invocation

`/fact-check`

Then paste the content you want verified.

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **Paste the content to fact-check.**
2. **What products or services are mentioned?** (list the URLs of each product's official website — to use as the primary verification source)
3. **Are there any statistics, research citations, or data claims?** (so these can be prioritised)

---

## Step 2 — Claim Extraction

Read the full content and extract every verifiable claim. Group them:

**Product/Feature Claims**
Any statement about what a product does, what it includes, what it supports, or how it works.
Examples: "HubSpot's free CRM includes contact management and email tracking" / "Notion supports offline editing"

**Pricing Claims**
Any mention of cost, plan names, pricing tiers, free trials, or pricing structures.
Examples: "Starts at $15/month" / "Free plan limited to 5 users" / "Enterprise pricing requires a call"

**Integration Claims**
Any claim that one product connects to or works with another.
Examples: "Integrates with Salesforce, Slack, and Zapier" / "Native Stripe integration"

**Statistical Claims**
Any numbers, percentages, research findings, or data points.
Examples: "Used by over 50,000 companies" / "Reduces churn by 25%" / "According to a 2023 Forrester report"

**Feature Availability Claims**
Which features are on which plans, whether something is in beta, GA, or deprecated.
Examples: "API access is only on the Business plan" / "SSO is included on all paid plans"

**Compliance and Certification Claims**
SOC2, GDPR, HIPAA, ISO certifications, or other regulatory claims.

**Timeline Claims**
Founded dates, product launch dates, "recently released", "now available".

---

## Step 3 — Verification

For each claim extracted, verify it using the primary source. Use WebFetch to check:

**For product/feature/integration claims:** The product's official features page, pricing page, integrations page, or help documentation.

**For pricing claims:** The product's current pricing page (note the date — pricing changes frequently).

**For statistics:** The original source. If the stat says "according to Forrester" — find the Forrester report. If it says "studies show" with no source — that is an immediate unverified flag.

**For compliance claims:** The product's security/trust/compliance page.

Do not accept a claim as verified just because another article repeats it. Trace every claim to a primary source.

---

## Step 4 — Verdict for Each Claim

For each claim, assign:

**Verified** — confirmed from the primary source, matches what the source says
**Outdated** — was true but the source now shows different information (note what changed)
**Unverifiable** — cannot be confirmed from any primary source (note what was checked)
**False** — the primary source contradicts the claim (note the correct information)
**Needs attribution** — the claim may be true but has no source cited and cannot be independently confirmed

---

## Step 5 — Content Corrections

For every claim that is not Verified:
- Write the corrected version of the sentence/passage
- Note what source supports the correction
- If the claim is entirely unverifiable and cannot be replaced with a verified equivalent, recommend removing it

---

## Output

Print two things:

**1. Fact-Check Report**

```
## Fact-Check Report — [content title or keyword]
Date: [today's date]

### Summary
- Claims checked: [N]
- Verified: [N]
- Outdated: [N]
- Unverifiable: [N]
- False: [N]
- Needs attribution: [N]

### Issues Found

#### Outdated Claims
| Claim | Original text | Correct information | Source |
|---|---|---|---|
| [claim] | "[quote]" | [correction] | [URL] |

#### Unverifiable Claims
| Claim | Text | What was checked | Recommendation |
|---|---|---|---|
| [claim] | "[quote]" | [sources checked] | Remove / Rephrase as opinion / Find source |

#### False Claims
| Claim | Original text | Correct information | Source |
|---|---|---|---|

#### Needs Attribution
| Claim | Text | Suggested source to find |
|---|---|---|

### Verified (no changes needed)
[Brief list of major claims that checked out — so the user knows the work was done]
```

**2. Corrected Content**
Output the full content with all corrections applied.

Rules:
- Only change what's in the fact-check report
- If removing an unverifiable claim leaves a structural gap, note it — don't silently hollow out a section
- If a correction changes the article's argument or recommendation, flag this explicitly before the corrected content

---

## Important Rules

- **Never verify from memory.** Every claim check must use a live WebFetch to a primary source.
- **Pricing is dated by definition.** Always note the date pricing was verified and add a note in the content that pricing may change.
- **"Can't find a source" is not verification.** If a source can't be found, the claim is unverifiable — not verified.
- **Competitor claims require competitor's own source.** Don't verify a claim about Competitor X using an article that cites another article.
- **Integration claims are high-risk.** Integrations get deprecated, changed, or moved to higher tiers. Always check the current integrations page.

---

## Standalone Save

If invoked directly, ask:
"Save the corrected content to file? Default: `./factchecked-[date].md`"
Wait for confirmation, then save.
