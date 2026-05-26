# Conversion Writing

Make the content do its job. Traffic that reads and leaves is a wasted ranking. This step ensures the content is structured to move readers toward action — without turning it into a sales pitch that undermines trust.

## Invocation

`/conversion-writing`

Then paste the content you want to review.

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **What is the primary conversion goal?** (start trial / book demo / sign up free / read related article / contact sales / no CTA — editorial only)
2. **What product or service is this content promoting?** (and its key differentiator or strongest offer)
3. **Who is the reader at the point of conversion?** (what have they just read, where are they in the buying journey)
4. **Paste the content.**

---

## Step 2 — Conversion Audit

Read the full content and assess:

**CTA Presence and Placement**
- Is there a CTA? If yes, where does it appear?
- Is the placement logical — does the CTA appear after the reader has been given enough information to want to act?
- Is there a mid-article CTA where appropriate (long content should not have readers waiting until the very end)?
- Does the CTA match the reader's stage? A reader who just learned what a product does should not immediately see "Buy now." They might see "See how it works."

**Objection Handling**
What would stop this reader from taking action? Common objections:
- "Is this the right tool for my situation?"
- "What does it actually cost?"
- "Is it hard to set up?"
- "What if I sign up and it doesn't work?"
- "Can I trust this recommendation?"

Does the content address these objections before asking for action? Or does it leave them unanswered and expect the reader to just convert?

**Proof Elements**
Conversion requires trust. Does the content include:
- Specific, concrete claims (not just "powerful" and "easy to use")
- Named examples, case studies, or use cases
- Social proof signals (customer counts, notable logos, ratings — only if verifiable)
- Recency signals (the content is current and maintained)

**Product Mentions**
If this is commercial content, is the product mentioned naturally in context — or only in a bolted-on CTA at the end? Product mentions should appear where they're relevant to the reader's question, not just as a promotional layer added after the editorial content.

**Decision Support**
Does the content help the reader make a confident decision — or does it give them information without helping them apply it?
- Does it include a recommendation (for comparison/listicle content)?
- Does it address "who is this for / who is this not for"?
- Does it explain what to do next after reading?

---

## Step 3 — CTA Optimisation

Write the optimised CTAs for this piece. Rules:

**Be specific**: "Start your free trial" is better than "Get started." "See how [Product] handles [use case]" is better than "Learn more."

**Match the commitment to the reader's stage**: A reader at the top of the funnel is not ready for "Book a demo." They're ready for "See how it works" or "Read the 5-minute overview."

**Connect CTA to what was just read**: If the preceding section talked about a specific pain point, the CTA should connect to the relief. Example: "Tired of [pain point]? [Product] handles this differently — [link]."

**One primary CTA per section**: Don't stack CTAs. Multiple CTAs in one location compete with each other and reduce conversion.

Provide:
- Primary CTA (end of article): [exact copy + placement context]
- Mid-article CTA (if article is over 1500w): [exact copy + which section it follows]
- Inline product mention (if applicable): [natural in-body placement suggestion]

---

## Step 4 — Trust Signal Audit

Review what makes the content trustworthy and what might undermine trust:

**Builds trust:**
- Specific, named examples
- Acknowledging the product's limitations or when it's not the right fit
- Accurate feature claims (not overselling)
- Current information (pricing, features are as of a specified date)

**Undermines trust:**
- Superlatives without evidence ("the best", "industry-leading", "world-class")
- Claims that sound promotional but not informational
- Avoiding any mention of the product's weaknesses when writing comparison content
- CTAs that appear before the reader has been given value

Flag anything that undermines trust and recommend the fix.

---

## Output

Print this block:

```
## Conversion Review — [content title or keyword]
Date: [today's date]

### Conversion Audit Summary
- CTA present: [yes / no]
- CTA placement: [good / needs moving — specify where]
- Objections addressed: [list which are handled and which are missing]
- Proof elements: [what's present, what's missing]
- Product integration: [natural / bolted-on / missing]
- Decision support: [recommendation present / absent / weak]

### Objection Gaps to Fill
1. [Objection not addressed] — [suggested fix: where in the content to address it and how]
2. [Objection]

### Trust Signal Issues
1. [Issue] — [recommended fix]

### Recommended CTAs
- **Primary CTA (end of article):** "[exact copy]"
  Placement: [after which section]
- **Mid-article CTA:** "[exact copy]" or "Not needed — [reason]"
  Placement: [after which section]
- **Inline product mention:** [specific sentence suggestion]
```

Then output the **full revised content** with all conversion changes applied — CTAs added, objections addressed, trust issues fixed.

Do not add new factual content. Only add CTA copy, objection-handling copy, and adjust framing where needed.

---

## Standalone Save

If invoked directly, ask:
"Save the revised content to file? Default: `./conversion-[date].md`"
Wait for confirmation, then save.
