# Write Content (Master Pipeline)

Full content production pipeline — from a single keyword to a finished, published-ready article. The quality bar is publication in Forbes, The Verge, the New York Times, or a comparable top-tier outlet. Every draft goes through a write-edit loop (Phase 6A) that repeats until the piece is editorially clean before moving to fact-checking, SEO, and conversion. Runs all 10 sub-processes in sequence: intent analysis, SERP intelligence, content strategy, subject matter briefing, research synthesis, information architecture, draft writing, editorial QC loop, fact-checking, on-page SEO, and conversion optimisation.

Each sub-process can also be run independently as its own skill.

## Invocation

`/write-content <keyword>`

Example: `/write-content best CRM for small business`

---

## Step 0 — Setup

Ask the user these questions all at once before doing anything else:

1. **What product or service is this content for?** (one sentence — what it does and who it's for)
2. **Who is the target audience?** (role, company size, industry — be specific)
3. **What is the primary conversion goal?** (start trial / book demo / sign up free / no CTA — editorial only)
4. **Do you have a content template to use?** If yes, paste it now. If no, the structure will be built from scratch.
5. **Output file path:** Where should the final article be saved? Default: `./content-[keyword-slug]-[date].md`

Wait for all answers before proceeding.

---

## Phase 1 — Intelligence (run both in parallel)

### 1A. Search Intent Analysis

Do not rely on training data. Run these searches in parallel using WebSearch:
- The exact keyword
- `[keyword] reddit`
- `[keyword] forum`
- `[keyword] problems` or `[keyword] what nobody tells you`

Use WebFetch to read 2–3 community/forum results (Reddit, Quora, G2 reviews — not vendor pages). Extract what real searchers actually want in their own words.

Determine:
- **Primary intent**: Buying / Comparison / Informational / Troubleshooting / Validation / Navigational
- **Secondary intent** (if present)
- **Funnel stage**: Top / Middle / Bottom
- **The searcher**: who they are, what triggered the search, how much they know
- **What they want to find, do, and know** — list the specific questions this content must answer
- **Back-button triggers**: what would immediately fail them
- **Delight factors**: what would make this the definitive resource
- **Framing recommendation**: angle, tone, and the one thing this content must nail

Print the intent analysis before moving to Phase 1B.

### 1B. SERP Intelligence

Run a WebSearch for the exact keyword. Note: dominant result types, featured snippet format, People Also Ask questions, top 5 organic titles, freshness signals, ad presence.

Use WebFetch to read the top 5 organic results (skip YouTube and pure product pages unless they dominate). For each page, extract:
- Format (listicle / guide / comparison / landing page)
- H2 structure — list all headings
- Approximate depth (short / medium / long)
- Proof mechanisms used
- Differentiating angle (or lack of one)

Then extract the patterns:
- Format Google is rewarding
- Sections appearing in 3+ results (structural consensus)
- Depth standard
- Snippet structure (if featured snippet exists)
- Entity patterns (products, brands, concepts appearing repeatedly)
- Content gaps — what none of the top 5 covers adequately

Print the SERP intelligence before moving to Phase 2.

---

## Phase 2 — Strategy

Using Phase 1 outputs, determine:

**Content format** — choose from: listicle / alternatives page / comparison page / how-to guide / explainer / use case page / landing page / pricing page / integration page / problem-solution page / review / roundup

**Why this format**: one sentence — why this format matches the intent and SERP pattern

**Primary angle**: the single most differentiated framing for this piece vs. what's already ranking

**Scope**:
- In scope: what this article covers
- Out of scope: what it explicitly does not cover
- Target depth: short (500–1000w) / medium (1000–2000w) / long (2000–3500w) / exhaustive (3500w+)

Print the strategy decision before moving to Phase 3.

---

## Phase 3 — Knowledge Building (run both in parallel)

### 3A. Subject Matter Brief

Go to primary sources. Do not use training data for product-specific facts.

Use WebFetch in parallel to check:
- The product homepage
- The product pricing page
- The product features page
- The product integrations page (if relevant)
- Competitor sites if comparison content is involved

Extract: exact feature names (as the product calls them), current pricing and plan tiers, verified integrations, known limitations, buyer pain points from reviews (run a quick WebSearch for `[product] reviews reddit` or `[product] G2` to supplement).

Flag anything with [VERIFY] that cannot be confirmed from a live source.

### 3B. Research Synthesis

Run WebSearch for:
- The main topic/keyword
- `[topic] expert opinion`
- `[topic] case study` or `[topic] data`
- `[topic] mistakes` or `[topic] what nobody tells you`

Use WebFetch to read 4–6 sources. Prioritise practitioners and data-backed content. Skip thin vendor content.

Extract:
- **Consensus**: what credible sources agree on
- **Contradictions**: where sources genuinely disagree and what the resolution is
- **Missing angles**: what nobody covers adequately
- **Stronger perspective**: the most honest, direct thing to say that most sources hedge or miss
- **Verified data and quotes**: specific stats with named sources (discard any unattributed stats)

Print subject matter brief and research synthesis before moving to Phase 4.

---

## Phase 4 — Information Architecture

Using all Phase 1–3 outputs, build the full outline.

**Answer first**: Identify the primary question and write the one-sentence answer that the intro must deliver within the first 100–150 words.

**Section planning**:
- Must-have sections (what the searcher expects)
- Value-add sections (gaps from SERP intelligence)
- Cut list (what seems relevant but doesn't serve this searcher)

**Sequence logic**: Lead with the answer → earn complexity → match searcher's journey → group related content → end with action.

**Template reconciliation** (if template was provided): Map template sections to planned sections. Flag any genuine conflicts between what the searcher needs and what the template prescribes.

**Full outline**: H1 → H2 → H3 structure with one-sentence description of each section and word count budget. Total should match the target depth from Phase 2.

Print the full outline, then **pause here**. Ask the user:

> "Here's the outline. Any changes before I write the draft? You can also paste your template now if you haven't already."

Wait for approval or edits. Apply any changes to the outline. Then proceed to Phase 5.

---

## Phase 5 — Draft Writing

Write the full article. Follow these rules absolutely:

**Structure**
- Follow the approved outline exactly. Do not add, remove, or reorder sections without flagging it.
- Honour the word count budgets per section. Don't blow out one section at the expense of others.
- If a template was provided, use its structural format. Adapt it to serve this specific piece — the template is a starting point, not a cage.

**Opening**
- Deliver the primary answer within the first 100–150 words. No preamble.
- Do not open with: what this article will cover, why this topic matters, acknowledgement that this is a common question, or any statement about the reader ("if you're a [role]..."). Open with the answer or the most valuable thing first.

**Writing quality — non-negotiable rules**
- Every claim must be specific. No vague generics.
- Every factual statement must trace to the research gathered in Phases 3–4. Do not introduce facts not in the brief.
- Use exact product names, exact feature names, exact pricing as verified in Phase 3. No paraphrasing product capabilities.
- If a stat, date, or specific fact is needed but wasn't verified, write [FACT CHECK: describe what's needed] inline rather than inventing it.
- Write for the specific reader identified in Phase 1. Match the depth of knowledge they bring.

**Voice and register — this is non-negotiable**

The reader is a B2B founder or CMO who has already hired one agency that disappointed them. They've sat through the quarterly review where rankings climbed and demos stayed flat. They know the difference between a traffic win and a pipeline win. Write to that specific person. Not to a generalized "B2B leader." Not to the abstract concept of someone evaluating agencies.

What "operator-to-operator" actually means in practice:

It means you've done the thing you're explaining. You know exactly where it goes wrong. You say what other content doesn't, because you've seen the failure mode firsthand. The authority comes from the specificity of the observation, not from big words, hedged qualifications, or thought-leader cadence.

Bad (performing expertise): "Choosing the right SaaS SEO agency requires careful evaluation of several key factors that align with your growth objectives and budget constraints."

Good (having expertise): "Hiring a SaaS SEO agency is hard partly because most of them are general SEO shops with one or two SaaS logos on the deck. You can usually tell within two calls: they pitch traffic instead of pipeline, and their case studies stop at rankings."

The second version works because it's specific about the actual failure mode. That specificity IS the voice.

**How to build a paragraph that actually moves:**

Every paragraph has a destination. Start at one understanding, end at a different one. Not by restating the same claim three different ways — by progressing:

1. State the point first (the most direct, confident version — no setup, no context, no warming up)
2. Evidence or qualify it (the specific fact, name, number, or mechanism that makes it true)
3. Draw the implication for the reader ("Which means if you're evaluating them..." / "The catch is...")

If the reader's understanding hasn't moved by the end of the paragraph, cut it or merge it with adjacent content.

**How to connect sentences:**

Each sentence connects to the previous one by doing exactly one of these four things:

- **Extending:** adds detail or specificity to the previous claim
- **Qualifying:** limits the scope or adds a caveat (do this once per section, not repeatedly)
- **Evidencing:** gives the proof — a name, number, or concrete example
- **Redirecting:** uses "but," "so," "still," "the catch is," or "which means" to pivot the argument

Never restate a previous sentence with different words. Never add a sentence that could be deleted without losing meaning. Every sentence does work or it doesn't exist.

Bad (restating the same idea three ways):
"Most agencies track rankings. They focus on keyword positions as their primary metric. This means they report on traffic rather than pipeline."

Good (extending then redirecting):
"Most agencies track rankings. The ones that move pipeline track attributed trials and booked demos, and they set that reporting up in month one before content even goes live."

**How to describe an agency or product:**

Describe by what it does, not what category it falls into. "A pipeline-focused agency" is a label. "They skip informational content and open every engagement with competitor alternative pages and pricing comparison searches" is a description. The second version tells you what working with them looks like.

When describing a service, always answer: what does the client actually see or experience as a result of this approach? That's the real description. Everything else is a category label dressed up as copy.

**How to write results:**

State them plainly and move on. No setup ("For example, when [CLIENT] came to us..."), no framing ("This impressive result demonstrates..."), no enthusiasm. Just tell it.

"Smartlook went from content that ranked to 600+ new monthly signups. The shift was targeting the keywords buyers search during tool evaluation, not during the awareness phase."

The client name, the number, and the mechanism. That's the entire structure.

**How to handle trade-offs and weaknesses:**

State them directly. Readers trust content that names the catch. "SEO takes 4–6 months before pipeline moves. Any agency that says otherwise is selling you traffic you can screenshot but can't close." A piece that never acknowledges a downside reads like a brochure. A piece that names the downside and explains it reads like advice.

**How personality works in this register:**

Personality comes from the observation, not the delivery. You don't make writing interesting by adding "look" before a point or opening with a rhetorical question. You make it interesting by saying something specific and true that other content doesn't.

Generic: "Most agencies rank content that doesn't convert."
Specific: "Most agencies build a content calendar before they know what your ICP searches in the 30 days before they evaluate tools."

The personality is in the specificity of the take. Not in the packaging.

**Sentence opening variation:**

If three paragraphs in a row open with "[Company name] is..." or "[Company] has...", rewrite two of them. Alternatives with more structural energy:

- Open with the mechanism: "The model here runs lean by design..."
- Open with the number or result, then explain: "Order.co's conversion rate went up 39X."
- Open with the implication for the reader: "If you're evaluating them, ask about..."
- Open with the qualifier that limits scope: "For companies already past Series A..."

**What the reader should feel at the end of each section:**

Not impressed. Informed. Like they learned something that would have taken them two weeks of sales calls to figure out on their own. That's the bar. If they feel like they just read marketing copy, rewrite it.

**Hard forbidden patterns — zero tolerance:**

Setup and explanation language (just state the point):
- "This is why..." / "That's because..." / "What this means is..." / "In other words..." / "Let me explain..."

Mechanical transitions:
- "From there, we..." / "Next, we..." / "After that..." / "Following this..."

Generic descriptors (use specifics instead):
- "comprehensive," "robust," "extensive," "full-service"
- "helps companies," "enables businesses," "allows teams"
- "designed to," "built to," "focused on"
- Not "helps companies grow" — say "drives demos" or name the outcome

Over-hedging (state as fact or caveat once and move on):
- Don't use "typically," "usually," "generally," "often" more than once per section

Hype words:
- "cutting-edge," "leverage," "unlock," "in today's [anything]," "game-changing," "best-in-class," "supercharge," "ever-evolving landscape"

Vague claims (name it or don't say it):
- "many companies," "studies show," "industry experts agree"

Unnecessary signposting:
- "In this section we'll cover..." — just cover it

Filler phrases:
- "In today's landscape" / "Now more than ever" / "It's important to note" / "It's worth mentioning"
- "Let's dive in" / "Let's explore" / "As we've seen" / "As mentioned above"
- "In conclusion" / "To summarise" / "Whether you're a [X] or a [Y]"

Negative-positive contrast structures — eliminate every instance:
- "Not just X, but also Y" / "Not only X, but Y"
- "[X] isn't [Y]. [It's/They're] [Z]." — stating what something isn't, then flipping to what it is
- "Rather than X, Y" / "Instead of X, Y" as a rhetorical frame
- Standalone "Not X." as a one-sentence paragraph
- "[X], not [Y]." as a sentence or clause ender used for contrast effect
- "Less like X, more like Y" / "More than just X" / "Beyond just X"

State the positive claim directly. Define things by what they are, not by what they aren't.

Punctuation and formatting bans:
- Em dashes (—) and en dashes (–). Use commas, parentheses, or start a new sentence instead. Parenthetical asides with regular parentheses are fine and encouraged.
- Emojis. None.
- Title case in subheadings — sentence case only.

**Agency listicle paragraph structure — P2 is the mechanism, never the case study:**

In agency entry sections, the paragraph structure is:

- **P1:** Who the agency is and what they fundamentally do — origin, model, and core specialization in one paragraph.
- **P2:** The one operational or philosophical detail that genuinely differentiates this agency from others on the list. This is NOT a case study, NOT a results claim, NOT marketing language from their website. It's the thing a client would only discover after two months of working with them. How do they actually operate? What's the mechanism that produces their results? Examples: direct founder access with no account management layer; a methodology that targets purchase-intent keywords before touching informational content; a guest-booking process tied to ICP account lists rather than podcast audience size; a content model that runs sprint-based instead of retainer-based.

Do NOT write P2 as a case study. Results belong in the Key results bullet section. If P2 is describing what a client achieved, it's in the wrong place — move that content to Key results and write the actual operational differentiator instead.

Good P2: "Their model runs lean by design: a small team with no account management layer between the strategist and the client. Every content brief is approved by the founder, and the person running your strategy on day one is the same person running it in month twelve."

Bad P2 (this is a case study, not a P2): "One client saw a 182% increase in page-one keywords within six months. Another achieved page-one rankings for competitor alternative searches within 30 days of starting."

The distinction: P2 explains the mechanism. Key results report the outcome.

**Sharpness rules:**

Cut setup. State things as fact, not as observation.

Bad: "Most marketing agencies are built for it" (built for what?)
Good: Name the failure mode directly. "Most agencies track MQLs. SaaS companies need CAC payback."

Bad: "They understand long B2B sales cycles"
Good: "They know your sales cycle is 90 days and the buying committee has four people."

Bad: "Three reasons dominate the conversation"
Good: "Three reasons drive the decision."

Show, don't tell. A specific client and a specific result beats any amount of explanation. Integrate client names naturally with transitions — don't signpost them ("For example, [CLIENT NAME] achieved..."). Just tell the story.

**Second person — mandatory throughout:**

Address the reader as "you" in every section that speaks to what they need, get, experience, or decide. This is non-negotiable.

- "Companies that want pipeline" → "If you want pipeline"
- "Clients work directly with the founder" → "You work directly with the founder"
- "Businesses need to consider budget" → "You need to consider budget"

Agency and product descriptions can use third person for the subject ("They run ABM-targeted guest booking"). Any statement about the reader's experience, outcome, or decision uses "you."

**Minimum sentence length — 10 words:**

Every sentence in body copy must be at least 10 words. Count every sentence before publishing. Short fragments are AI affectation. They get cut from serious publications on sight.

If a sentence is under 10 words: expand it with a specific detail that adds meaning, or merge it with the adjacent sentence.

This applies to body copy only. Headings, subheadings, and bullet list items are exempt.

Bad: "That shows in how they work." — 7 words.
Fix: "That background shapes how they structure client work and where they concentrate early effort."

Bad: "We're practitioners." — 3 words.
Fix: "We're practitioners who built the same system we now sell to clients."

**Sentence rhythm and structure:**

Vary structure to avoid robotic cadence. Mix: varied sentence openings, questions you immediately answer, specific examples instead of general descriptions, and paragraphs that sometimes open with context before landing the main claim.

Bad (predictable):
"Omniscient Digital is an organic growth agency founded in 2019. They cover SEO strategy, content production, and GEO. Their methodology leads with research before producing anything."

Better (varied):
"The founding team came out of in-house growth roles at HubSpot and Shopify, and that background shapes how they work with clients. You get a team that operates inside your strategy, with the context and accountability of an embedded partner."

If five paragraphs in a row open with a noun + verb + object, rewrite two of them to open differently.

**Short declarative sentences — use deliberately, not habitually:**

The 10-word minimum applies to informational and descriptive sentences. Short declarative sentences (under 10 words) are permitted only as deliberate rhetorical devices, used sparingly (once or twice per major section at most). The test: does this short sentence carry genuine argumentative weight and close an idea cleanly? Or is it a lazy fragment masquerading as style? If the latter, expand it.

**The equivalence collapse — use when two things truly are the same:**

When two claims genuinely imply each other, state both directions and then close the loop in one short line. This is a structural technique borrowed from Ben Goodey's writing and works specifically when the equivalence is real, not rhetorical.

Example: "Good podcast production is good pipeline strategy. Good pipeline strategy shapes good podcast production. The two are the same investment."

Do not use this structure for things that are not genuinely equivalent. The power comes from the truth of the claim, not the pattern itself.

**Open with the bold framing, then earn it:**

Lead sections with the most confident, definitive statement you can make, then back it up with specifics. Do not build to the point through setup and context. The point goes first.

Bad: "There are many factors to consider when choosing a B2B podcasting agency, including..."
Good: "Who you invite as a guest matters as much as what you say, and most agencies get this wrong."

**Criteria before the list:**

When introducing a list of agencies or options, state the evaluation criteria first, then deliver the list. This frames the reader's expectations before they start reading entries and positions the author as a thoughtful selector, not an aggregator.

Example: "When evaluating a B2B podcast agency, look for three things: named case studies with specific outcomes, a guest strategy tied to your ICP, and reporting that connects the show to your CRM. Here are the ten that passed that bar."

**Readability rules:**

- Common words. Cut anything not doing work.
- Common words over fancy ones: "use" not "utilize," "help" not "facilitate," "about" not "regarding"
- Most important information first in every section
- Define jargon the first time — once, briefly, then move on
- Active voice as default. Passive only when the doer genuinely doesn't matter.
- Transition words that carry meaning: "but," "so," "still," "instead," "the catch is"
- One main idea per paragraph. 2–4 sentences.
- Format for scanning — the reader is probably skimming

**Evidence rules:**

Every concrete claim needs evidence: a stat, a study result, an expert quote, a benchmark, a named data point. Don't overstuff citations. No fabricated stats. If you don't have a real number, leave it out or say so. If a stat was verified in Phase 3, use it. If not, write [FACT CHECK: describe what's needed] and continue.

**American English throughout:**
optimize, organize, color, behavior, analyze — not their British equivalents.

**Competitor descriptions in client listicles — factual, not promotional:**

When the content is a listicle where the client appears alongside competitors, describe competitors accurately and specifically, but strip every trace of marketing language from their entries. Your job is to inform the reader so they can make a decision, not to sell them on a competitor.

For competitor entries:
- State what they do, what results they've produced, and who they're best for — factually and specifically
- Do not use language that makes a competitor sound exceptional, exciting, or compelling to hire
- Do not use adjectives that function as endorsements: "impressive," "outstanding," "remarkable," "innovative," "leading," "renowned," "award-winning" (unless it's a verifiable fact like a named award, stated flatly)
- Do not frame competitor results in a way that generates excitement or urgency — report the number, stop there
- Do not write "Best for" entries for competitors that read like a sales pitch

The client's entry gets depth, context, and the strongest framing. Competitor entries get accurate, neutral information — enough for the reader to understand fit, no more.

Bad (promotional): "Sweet Fish Media has built one of the most impressive track records in B2B podcast production, with an incredible 22M+ downloads across their client portfolio and a reputation for transforming how companies approach video-first content."
Good (factual): "Sweet Fish Media has run B2B podcast production since 2015, with 10,000+ episodes and 22M+ downloads produced across their client base. Their model covers audio and YouTube video from a single recording."

**Publication quality bar:**
The finished piece must be publishable in Forbes, The Verge, the New York Times, or a comparable top-tier publication without a senior editor requiring cuts or rewrites. Write to that standard from the first sentence. If a passage would get cut in a serious publication, rewrite it before moving on.

Write the complete draft. Print it in full.

---

## Phase 6 — Quality Control (run sequentially)

### 6A. Editorial QC loop — run until the draft is clean

This phase runs as a loop. Do not move to 6B until the draft passes with zero issues remaining.

**Round 1:** Review the full draft against every rule in Phase 5. Fix every issue found. Apply all fixes directly to the draft.

Check for:
- Structural failures: intro that doesn't answer, conclusion that only restates, sections that repeat earlier content, sections that could be merged
- Sentence-level failures: filler phrases, vague claims, robotic formality, hedging, over-explaining
- Second person violations: "companies/businesses/teams" used where "you" belongs
- Sentences under 10 words: every body copy sentence must meet the minimum; expand or merge any that don't
- Negative-positive contrast structures: "X isn't Y it's Z," "rather than X, Y," "not just X but Y," "less like X more like Y," standalone "Not X." sentences
- AI slop patterns: three-part intro formula, closing reminder paragraphs, every list item with identical structure, forced section transitions, bolding random phrases
- Publication bar: would a senior editor at Forbes, The Verge, or the New York Times pass this sentence? If not, rewrite it.

**Round 2:** Re-read the full draft after fixes. Run every check again from the top.

**Round 3+:** Repeat until a full read-through produces zero issues. Only then mark the draft as editorially clean and proceed to 6B.

Do not produce an issue log in pipeline mode — fix and continue until clean.

### 6B. Fact Check

Extract every verifiable claim (product features, pricing, integrations, statistics, compliance claims, timelines).

Use WebFetch to verify each claim against its primary source:
- Product claims → product's own features/pricing/integrations page
- Stats → original study or report, not secondary coverage
- Competitor claims → competitor's own site

For each issue found:
- **Outdated**: note the correct current information
- **False**: correct it and note the source
- **Unverifiable**: insert [VERIFY: describe the claim] rather than publishing an unverifiable claim
- **Pricing**: add a note that pricing was verified as of [date] and may change

Apply all verified corrections to the draft.

### 6C. On-Page SEO

Write three title tag options (primary keyword near front, under 60 chars, reads naturally). Recommend one.

Write the H1 (includes keyword, different from title tag, communicates value immediately).

Review all H2s and H3s: semantic relevance, keyword distribution, heading quality, hierarchy logic. Rewrite any that are weak.

Identify featured snippet opportunity: what format (paragraph/list/table) and whether the current content captures it. Make the edit if needed.

Check entity coverage: are the key named products, brands, tools, and concepts present? Flag missing entities.

Write the FAQ section if warranted (PAA questions not answered in body, 4–6 questions, 40–70 word answers each).

Write the meta description (140–155 chars, includes keyword, specific, click-worthy).

Apply all SEO changes to the draft.

### 6D. Conversion Writing

Review:
- Is there a CTA? Is it placed after the reader has received enough value to want to act?
- Are the main objections addressed before asking for action?
- Are product claims specific enough to build trust (vs. superlatives with no evidence)?
- Is the product mentioned naturally in context, or only in a bolted-on close?

Write the primary CTA (end of article) and mid-article CTA if the piece is over 1500 words. CTAs must be specific and connected to what was just read — not generic "Get started" copy.

Apply all conversion changes to the draft.

---

## Phase 7 — Final Output

Print the complete, final article in full — including:
- Title tag (recommended option)
- Meta description
- H1
- Full article body with all revisions from Phase 6
- FAQ section (if added)

Then save the article to the path confirmed in Step 0. If the path wasn't confirmed, use `./content-[keyword-slug]-[date].md`.

After saving, print a one-line summary:
```
Article saved to [path] — [word count]w — [title tag]
```

---

## Pipeline Rules

- **Never skip a phase.** Every phase exists because content without it is weaker. If a phase seems unnecessary for a specific piece, note why and get user confirmation before skipping it.
- **Never invent facts.** If information isn't found in research, write [FACT CHECK: describe what's needed] and continue. Do not hallucinate product features, pricing, stats, or company names.
- **Pause at Phase 4.** The outline review is the only required user checkpoint mid-pipeline. The rest runs to completion.
- **Template is a guide, not a constraint.** If the template has a section that genuinely doesn't serve this searcher, flag it and explain why — don't silently omit it or force-fit content into it.
- **Phase 6A is a loop, not a single pass.** Run editorial QC, fix every issue, run it again. Repeat until the draft is clean. Do not proceed to 6B with any known issues remaining.
- **The publication bar is non-negotiable.** Every sentence in the final draft must pass a senior editor at Forbes, The Verge, or the New York Times. If it wouldn't survive that edit, rewrite it before outputting.
