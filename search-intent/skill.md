# Search Intent Analysis

Decode precisely what a searcher wants when they type a given keyword. Not the category label — the psychology, the trigger, the job-to-be-done, and the quality bar they hold content to. Everything downstream depends on getting this right.

## Invocation

`/search-intent <keyword>`

Example: `/search-intent best project management software for agencies`

---

## Step 1 — Context Gathering

Ask the user two questions together (skip if already provided by the write-content pipeline):

1. **What product or service is this content for?** (one sentence — helps calibrate buyer framing)
2. **Who is the target audience?** (role, company size, industry — say "unknown" if not clear)

Wait for answers before proceeding.

---

## Step 2 — Real User Research

Do not rely on training data alone. Pull live signals.

Run these searches in parallel using WebSearch:
- The exact keyword as-is
- `[keyword] reddit`
- `[keyword] forum`
- `[keyword] problems` or `[keyword] what nobody tells you`

Use WebFetch to read 2–3 of the most useful results — prioritise Reddit threads, Quora answers, G2/Capterra reviews, or community discussions over vendor content. Real users reveal what they actually want.

Extract:
- The real questions being asked (vs. what the keyword implies on the surface)
- Frustrations with existing answers on this topic
- The language real users use (not marketing language)
- What they do next after finding an answer — what action follows?

---

## Step 3 — Intent Classification

Identify **primary intent** and any **secondary intent**:

| Intent Type | What the searcher is doing |
|---|---|
| **Buying** | Ready to purchase, evaluating final options, needs a push |
| **Comparison** | Evaluating two or more specific options head-to-head |
| **Informational** | Learning — not ready to buy, building understanding |
| **Troubleshooting** | Has a specific problem they're trying to solve right now |
| **Validation** | Decision mostly made, seeking confirmation they're right |
| **Navigational** | Looking for a specific brand or page they already know |

Also determine:
- **Funnel stage**: Top (awareness) / Middle (consideration) / Bottom (decision)
- **Urgency**: Browsing / Researching / Actively evaluating / Ready to act

---

## Step 4 — Deep Intent Profile

Answer each of the following specifically for this keyword. Generic answers are wrong answers.

**The Searcher**
- What job title or role is most likely behind this search?
- What company size or industry context (if relevant)?
- What probably just happened to them that triggered this search today?
- How much do they already know about this topic when they hit search?

**The Transaction**
- What do they want to FIND on the page — the specific deliverable they're expecting?
- What do they want to DO after reading — what action follows?
- What do they need to KNOW — list the 3–5 specific questions this content must answer?
- What would make them hit the back button in the first 10 seconds?
- What would make them bookmark this, share it, or come back to it?

**The Quality Bar**
- How thorough does this need to be to fully satisfy them?
- What proof or evidence would make them trust the content? (data, screenshots, case studies, expert credibility, recency?)
- Does this topic require fresh information (current pricing, new features, recent changes) or is evergreen content sufficient?
- What would a lazy, generic, or AI-slop answer to this query look like — what is the failure mode to avoid?

---

## Step 5 — Framing Recommendation

Write a single paragraph (3–5 sentences) covering:
- The angle and positioning this content should take
- The tone that will land (authoritative / conversational / technical / direct)
- The single most important thing this content must nail to win the click and satisfy the read

---

## Output

Print this block in full:

```
## Search Intent Analysis — [keyword]
Date: [today's date]

**Primary Intent:** [type]
**Secondary Intent:** [type or none]
**Funnel Stage:** [Top / Middle / Bottom]
**Urgency Level:** [Browsing / Researching / Evaluating / Ready to act]

### The Searcher
- [Who they are]
- [What triggered the search]
- [Prior knowledge level]
- [Context / stakes of the decision]

### What They Want
- Find: [specific deliverable expected on the page]
- Do: [action they'll take after reading]
- Know:
  1. [Question 1]
  2. [Question 2]
  3. [Question 3]
  4. [Question 4 if relevant]
  5. [Question 5 if relevant]

### Quality Bar
- Depth: [shallow overview / solid breakdown / deep dive / exhaustive reference]
- Proof required: [what evidence they'll trust]
- Recency sensitivity: [evergreen / needs current data — specify what kind]
- Back-button triggers: [what would immediately fail them]
- Delight factors: [what would make this the definitive resource]

### Framing Recommendation
[Your 3–5 sentence paragraph on angle, tone, and the one thing this must nail]
```

---

## Standalone Save

If invoked directly (not from the write-content pipeline), ask:
"Save to file? Default path: `./intent-[keyword-slug]-[date].md`"
Wait for confirmation, then save.
