# Information Architecture

Organise everything you know about this keyword into a structure that's logical, skimmable, and satisfying. Bad structure kills good content. This step turns research into a precise outline before writing starts.

## Invocation

`/information-architecture <keyword>`

Example: `/information-architecture best project management tools for remote teams`

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **Paste your research outputs:** intent analysis, SERP intelligence, content strategy brief, research synthesis, and subject matter brief — whatever you have.
2. **Do you have a template to work from?** If yes, paste it now. The outline will be reconciled with the template.
3. **What's the target depth?** (short ~800w / medium ~1500w / long ~2500w / exhaustive ~4000w)

---

## Step 2 — Answer First

Identify the primary question this content answers. Write the one-sentence answer right now — before building the structure.

This is the answer the intro must deliver, or the opening section must resolve, within the first 100–150 words of the piece. Content that makes readers scroll for the answer loses them.

**The answer:** [write it now]

---

## Step 3 — Section Planning

Using the intent analysis, SERP intelligence, and research:

**Must-have sections** — things the searcher will definitely expect:
List each section and write one sentence on what it delivers and why it belongs.

**Value-add sections** — things competitors don't cover that should be included based on gaps found:
List each and explain the gap it fills.

**Cut list** — things that seem relevant but don't actually serve this specific searcher:
List what's being excluded and why.

---

## Step 4 — Sequence Logic

Order the sections. Apply these principles:

1. **Lead with the answer** — the most important thing first. No preamble, no context-setting before the value.
2. **Earn complexity** — if the content gets more detailed as it goes, make sure simpler/more important material is earlier.
3. **Match the searcher's journey** — the sequence should mirror the questions a reader naturally asks as they go deeper.
4. **Group related content** — sections that belong together should sit together, not be scattered.
5. **End with action** — the last substantive section should tell the reader what to do next.

Write out the sequence with a one-line rationale for why each section appears where it does.

---

## Step 5 — Template Reconciliation

If a template was provided:

- Map each template section to your planned sections
- Where the template has sections not in your plan: decide whether to include them (if they serve the searcher) or cut them (if they're format boilerplate that doesn't fit this piece)
- Where your plan has sections not in the template: decide whether to add them or fold them into existing template sections
- Flag any genuine conflicts between what the searcher needs and what the template prescribes — surface these for the user to decide

If no template was provided: skip this step.

---

## Step 6 — Full Outline

Build the complete H1 → H2 → H3 outline with:
- The H1 (working title — optimised for the keyword)
- All H2 sections in order
- H3 subsections where needed (only add H3 if a section genuinely requires subdivision — don't nest for the sake of it)
- A one-sentence description of what each section covers
- Approximate word count budget for each section (should add up to the target depth)
- Placement marker for any CTAs, tables, lists, or special elements

---

## Output

Print this block in full:

```
## Information Architecture — [keyword]
Date: [today's date]

### Primary Answer
[The one-sentence answer this content delivers upfront]

### Section Plan

**Must-have:**
- [Section name]: [what it delivers, why it's here]
- ...

**Value-add (filling gaps competitors miss):**
- [Section name]: [gap it fills]
- ...

**Cut (excluded and why):**
- [What was cut]: [reason]

### Full Outline

**H1:** [working title]

**Intro** (~[X]w)
[What the intro does — delivers the primary answer, sets the frame, no throat-clearing]

**H2: [Section title]** (~[X]w)
[What this section covers]
  - H3: [Sub-section] (~[X]w) — [what it covers]
  - H3: [Sub-section] (~[X]w) — [what it covers]

**H2: [Section title]** (~[X]w)
[What this section covers]

[... continue for all sections]

**CTA / Conclusion** (~[X]w)
[What the close does — what action the reader takes]

**Total target:** ~[X]w

### Template Notes (if template was provided)
- Added from template: [list]
- Cut from template: [list and reason]
- Conflicts flagged: [any genuine tension between template and searcher need]
```

---

## Standalone Save

If invoked directly, ask:
"Save to file? Default: `./outline-[keyword-slug]-[date].md`"
Wait for confirmation, then save.
