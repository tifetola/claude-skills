# Editorial Quality Control

The anti-slop pass. The quality bar is simple: would a senior editor at Forbes, The Verge, the New York Times, or a comparable top-tier publication pass this piece without cuts? If the answer is no, it is not finished. Review every piece against that standard and remove everything that makes it weak — filler, repetition, vague claims, robotic phrasing, fake expertise, structural bloat, AI affectation, and lazy contrast structures. This is what separates content worth reading from content that ranks and disappoints.

## Invocation

`/editorial-qc`

Then paste the content you want reviewed.

---

## Step 1 — Context Gathering

Ask the user (skip if called from write-content pipeline):

1. **Paste the content to review.**
2. **What is the keyword and intent?** (so the QC can be calibrated to what the reader actually needs)
3. **Are there any sections that are intentionally brief?** (e.g. an intro that's supposed to be punchy — flag before cutting)

---

## Step 2 — Structural Pass

Read the full piece once before touching anything. Assess:

**Does the opening deliver?**
The first 150 words must either answer the primary question or give the reader a compelling reason to keep reading. If it spends those words on: explaining what the article will cover, motivating why the topic matters, generic setup statements, or describing the reader's pain before addressing it — that's a fail. Note it.

**Does every section earn its place?**
For each H2: could a reader who only read the headline of that section know whether they need to read it? If not, the headline is weak. If a section exists and the content doesn't add anything beyond what was already covered, it shouldn't exist. Note any sections that are redundant or that repeat earlier points under a different label.

**Does the conclusion add anything?**
If the conclusion summarizes what was just written, cut it. A conclusion should tell the reader what to do next, leave them with one final useful thought, or end cleanly. It should not restate points already made.

---

## Step 3 — Sentence-Level Pass

Go through the content sentence by sentence. Flag or fix each of the following:

### Voice and register check

The reader is a B2B founder or CMO who has already hired one agency that disappointed them. They've been in the quarterly review where rankings went up and demos stayed flat. They're not evaluating content — they're making a real decision and they have a limited tolerance for vague.

The target voice is earned authority: someone who's done the thing they're describing, knows exactly where it goes wrong, and says the thing other content doesn't. The authority comes from specific observation, not from big words, hedged qualifications, or thought-leader cadence.

**Flag and rewrite any passage that does one of the following:**

Performs expertise instead of having it. The tell: the passage explains what the reader should care about rather than just getting to the point.
- Bad: "Choosing the right SaaS SEO agency requires careful evaluation of several key factors aligned with your growth objectives."
- Good: "Most of them are general SEO shops with one or two SaaS logos on the deck. You can usually tell within two calls: they pitch traffic instead of pipeline, and their case studies stop at rankings."

Builds to the point instead of leading with it. The tell: the main claim appears in the third or fourth sentence after context-setting.
- Flag any paragraph where the point is buried. Move it to the front. Context follows.

Restates the same claim in multiple consecutive sentences without extending, qualifying, evidencing, or redirecting.
- Bad: "Most agencies track rankings. They focus on keyword positions. This means they report on traffic rather than pipeline."
- Good: "Most agencies track rankings. The ones that move pipeline track attributed trials and booked demos, and they set that reporting up in month one."
- Rule: each sentence must extend, qualify, evidence, or redirect from the previous one. Never restate.

Treats description as a category label. The tell: describes an agency or product by what it IS rather than what it DOES.
- Bad: "A pipeline-focused, full-service B2B SaaS agency."
- Good: "They skip informational content and open every engagement with competitor alternative pages and pricing comparison searches."

Adds warmth, enthusiasm, or reassurance that wasn't asked for.
- Bad: "Great news — there are several excellent options on the market."
- Cut it. No performed positivity.

Hedges a trade-off instead of naming it.
- Bad: "Results may vary depending on your competitive landscape and existing domain authority."
- Good: "SEO takes 4–6 months before pipeline moves. Any agency that says otherwise is selling traffic."

**What the voice check is looking for:**

Every paragraph should leave the reader knowing something specific they didn't know before. If reading a paragraph produces the feeling "that's obvious" or "that doesn't tell me anything," it fails. Rewrite it with a specific observation, number, name, or mechanism.

Personality in this register comes from the specificity of the observation, not from sentence structure or word choice. "Most agencies rank content that doesn't convert" is generic. "Most agencies build a content calendar before they know what your ICP searches in the 30 days before they evaluate tools" is specific. The second version has a voice. The first doesn't, no matter what words you dress it in.

The voice check passes when: every paragraph moves the reader's understanding forward, every claim is specific enough to be useful, and no sentence exists purely to fill space between real claims.

### Filler phrases — delete on sight

- "In today's [X] landscape" / "In today's fast-paced world" / "Now more than ever"
- "It's important to note that" / "It's worth noting" / "It goes without saying"
- "Let's dive in" / "Let's explore" / "Let's take a look" / "Without further ado"
- "In this article, we will..." / "By the end of this article, you'll..."
- "Whether you're a [X] or a [Y]"
- "As we've seen" / "As mentioned above" / "As discussed earlier"
- "In conclusion" / "To summarise" / "To wrap up" / "The bottom line is"
- "At the end of the day" / "All things considered" / "Needless to say"
- "When it comes to [topic],"
- "That being said" / "With that in mind" / "Having said that"
- "Moving forward" / "Going forward" / "First and foremost" / "Last but not least"
- "In other words" (unless the restatement genuinely adds clarity)
- "Simply put" / "Of course," used as a sentence opener
- "This is why..." / "That's because..." / "What this means is..." / "Let me explain..."

### Mechanical transitions — delete or rewrite

These add words without adding meaning:
- "From there, we..." / "Next, we..." / "After that..." / "Following this..."
- "Now that we've covered X, let's move on to Y"
- "With that in mind, let's look at..."

Replace with a sentence that actually says something, or cut the transition entirely and let the next idea follow naturally.

### Generic descriptors — replace with specifics

Every word in this list should trigger a rewrite:
- "comprehensive," "robust," "extensive," "full-service"
- "helps companies," "enables businesses," "allows teams"
- "designed to," "built to," "focused on"
- "cutting-edge," "leverage," "unlock," "game-changing," "best-in-class," "supercharge"
- "ever-evolving landscape," "in today's [anything]"
- "powerful," "seamless," "intuitive" as product descriptors without evidence

Not "helps companies grow" — name the outcome. "Drives demos." "Cuts CAC payback from 18 months to 11."

### Vague claims — make specific or cut

- "Many companies" → which companies? How many?
- "Studies show" / "Research suggests" → which study? Who? When?
- "Experts agree" / "Most experts believe" → which experts? On what evidence?
- "Significant improvement" / "major boost" → how much? Measured how?
- "One of the most popular" → popular by what measure?
- "Widely used" / "commonly used" → by whom? At what scale?
- "This is crucial" / "This is essential" / "This is key" → show it, don't assert it

If a claim can't be made specific, cut it. No fabricated stats. Ever.

### Over-hedging — state as fact or caveat once and move on

Flag any section that uses "typically," "usually," "generally," or "often" more than once. Pick one, state the caveat, move on. Don't hedge the same point repeatedly.

### Punctuation and formatting violations

- Em dashes (—) and en dashes (–): replace with a comma, parentheses, or a new sentence. Parenthetical asides with regular parentheses are fine and encouraged.
- Emojis: remove all.
- Title case in subheadings: convert to sentence case only.
- British English: replace with American English (optimize, organize, color, behavior, analyze).

### Structural bloat — cut or consolidate

- Meta-commentary intros: paragraphs that describe what the article is about rather than being it
- Recap paragraphs inside sections: ending each section with "In summary, we've seen that..."
- Thin headers with one-sentence bodies: if an H3 has one sentence under it, fold it into the parent section
- Over-bulleted content: if a list has 8+ items that could be 2 paragraphs, consider prose
- Unnecessary signposting: "In this section we'll cover..." — just cover it

### Tone problems

- Robotic formality: "It is imperative that users ensure..." → "Make sure you..."
- Fake enthusiasm: "Great news!" / "Exciting update!" / "You're in luck!" — cut
- Over-explaining obvious things: don't define terms the audience already knows
- Passive voice overuse: "it can be seen that" / "it is recommended" → say who sees it and who recommends it

### Sharpness check

Read each paragraph and ask: is this stated as fact, or as observation about a fact? Cut the observation layer.

Bad: "Most marketing agencies are built for it" (built for what?)
Good: Name the failure mode. "Most agencies track MQLs. SaaS companies need CAC payback."

Bad: "They understand long B2B sales cycles"
Good: "They know your sales cycle is 90 days and the buying committee has four people."

Bad: "Three reasons dominate the conversation"
Good: "Three reasons drive the decision."

When the content mentions a client result, check that it reads naturally — not signposted with "For example, [CLIENT NAME] achieved..." Just tell it. "Smartlook went from content that ranked to 600+ new monthly signups. The difference was targeting keywords their buyers actually search before evaluating tools."

### Competitor entries in client listicles — factual, not promotional

If the content is a listicle where the client appears alongside competitors, check every competitor entry for marketing language. Competitor entries exist to inform the reader, not to sell them on a competitor.

Flag and remove from competitor entries:
- Enthusiastic adjectives that function as endorsements: "impressive," "outstanding," "remarkable," "innovative," "leading," "renowned," "transformative," "pioneering"
- Award or credibility claims framed with admiration rather than stated as plain fact
- "Best for" copy that reads like a sales pitch for the competitor
- Results framed with excitement or urgency rather than reported as neutral facts
- Any sentence that makes a reader want to contact the competitor

The client's entry carries the depth, context, and strongest framing. Competitor entries carry accurate, neutral information — enough for the reader to assess fit, no more than that.

Bad: "Sweet Fish Media has built one of the most impressive track records in B2B podcast production, delivering an incredible 22M+ downloads across their client portfolio."
Good: "Sweet Fish Media has run B2B podcast production since 2015, with 10,000+ episodes and 22M+ downloads produced across their client base."

### Agency listicle P2 — mechanism, not case study

In agency entry sections, the second paragraph (P2) must describe the operational or philosophical detail that differentiates this agency from others on the list. It must NOT contain case study content or results claims — those belong in the Key results bullet section.

**The P2 test:** Does this paragraph describe HOW the agency operates? Or does it describe what a client achieved? If the latter, it's in the wrong place.

Good P2 (operational mechanism): "Their model runs lean by design: a small team with no account management layer between the strategist and the client. Every content brief is approved by the founder, and the person running your strategy on day one is the same person running it in month twelve."

Bad P2 (case study in disguise): "One client saw a 182% increase in page-one keywords within six months. Another achieved page-one rankings for competitor alternative searches within 30 days of starting."

If a P2 contains results data, move that content to Key results bullets and rewrite P2 to cover the actual operational differentiator: the hiring model, the methodology, the content approach, the reporting structure, the size and seniority of the team, or the thing about how they work that sets them apart from every other agency claiming to do the same thing.

### Second person — mandatory throughout

The piece addresses the reader as "you." This is non-negotiable. When describing what the reader needs, wants, gets, or should do, "you" is always the subject — not "companies," "businesses," "teams," "marketers," or "founders."

Flag every instance of third-person reader-substitute language:
- "Companies that want X" → "If you want X"
- "Businesses need to consider" → "You need to consider"
- "Clients work directly with the founder" → "You work directly with the founder"
- "Marketers will find" → "You'll find"

Agency or product descriptions can use third person to describe what the subject does ("They run ABM-targeted guest booking"). Any statement about what the reader gets, experiences, or decides uses "you."

### Minimum sentence length — 10 words

No sentence in body copy may be under 10 words. Count every sentence. Short fragments read as AI affectation and get cut from serious publications.

Flag any sentence under 10 words and either expand it with a specific detail or merge it with the adjacent sentence.

Bad: "Not just Spotify." — 3 words, a fragment used for fake emphasis.
Fix: Fold the point into the sentence before it. "Distribution targets LinkedIn, AI search, and niche communities alongside podcast platforms, because those are the channels where your buyers actually evaluate vendors."

Bad: "We're practitioners." — 3 words.
Fix: "We're practitioners who built the system we now sell to clients."

Bad: "That shows in how they work." — 7 words.
Fix: "That background shows directly in how they structure client engagements and where they focus early effort."

This rule applies to informational and descriptive body copy. Headings, subheadings, and bullet list items are exempt. Short declarative sentences under 10 words are also permitted when used as deliberate rhetorical devices — closing an argument cleanly, stating an equivalence, or landing a bold framing statement. The test: does this short sentence carry real argumentative weight? If it's a lazy fragment posing as style, expand it. If it genuinely closes an idea, it can stay. Use them sparingly — once or twice per major section at most.

### No negative-positive contrast structures

This is one of the clearest markers of AI-generated and low-quality writing. Eliminate every instance:

- "Not just X, but also Y" / "Not only X, but Y"
- "[X] isn't [Y]. [It's/They're] [Z]." — stating what something isn't, then flipping to what it is
- "Rather than X, Y" / "Instead of X, Y" used as a rhetorical frame
- Standalone "Not X." as a sentence
- "[X], not [Y]." as a sentence or clause ender used for contrast effect
- "Less like X, more like Y" / "More than just X" / "Beyond just X"

These structures create fake drama by defining things through what they aren't. Every one of them can be rewritten by stating the positive claim directly.

Bad: "Caspian isn't building interview podcasts with better editing. They're producing narrative series that function as brand content."
Fix: "Caspian produces narrative-format series built for enterprise organizations that need podcast content to meet broadcast-quality brand standards."

Bad: "Less like a traditional agency, more like an embedded growth team."
Fix: "They embed inside your strategy and operate with the same context and accountability as an in-house growth team."

Bad: "Not just Spotify." (standalone fragment)
Fix: Fold it into the preceding sentence with a specific reason. "Distribution targets LinkedIn, AI search, and niche communities alongside podcast platforms, because those are the channels where your buyers actually evaluate vendors."

### Style techniques — use when earned

**The equivalence collapse:** When two claims genuinely imply each other, state both directions and close the loop. "Good podcast production is good pipeline strategy. Good pipeline strategy shapes good podcast production." Only use this when the equivalence is real — the technique's power comes from truth, not pattern.

**Bold framing first:** The most confident, definitive statement you can make goes at the opening of the section. Specifics follow. Flag any paragraph that buries its point in the third or fourth sentence after setup and context.

**Criteria before the list:** When introducing options or agencies, the evaluation criteria come first, then the list. Flag any listicle that opens straight into entries without first telling the reader how to evaluate what they're about to read.

### Sentence rhythm check

Read the content aloud. If every paragraph follows the same [statement + explanation + elaboration] pattern, break it up.

The mix should include: varied sentence openings, questions immediately answered, specific examples instead of general descriptions, and the occasional paragraph that opens with context before the main claim.

If five paragraphs in a row open with a noun + verb + object, rewrite two of them to open differently. Every sentence must be at least 10 words, so rhythm variation comes from structure and opening, not from short fragments.

### AI slop patterns — eliminate

- The three-part intro structure: (1) state the problem, (2) acknowledge it's hard, (3) promise this article will solve it
- The closing "reminder" paragraph that tells the reader to "remember" things already explained
- Numbered lists where the numbers are arbitrary and order doesn't matter
- Every list item having exactly the same structure ("Noun + colon + explanation" for all 8 items)
- Forced transitions between every single section
- Bolding random phrases within paragraphs rather than genuinely important terms
- The phrase "in the world of [industry]"
- Fake specificity: "[Product] is used by thousands of companies worldwide" (meaningless)
- The "pro tip" box that contains obvious advice
- Formulaic H2 naming: "Why X Matters", "The Benefits of X", "How to Get Started With X", "What Is X?"

---

## Step 4 — Quality Standards Check

After the sentence-level pass, confirm:

**Specificity**: Does every factual claim have a source, a number, a name, or a concrete example? If not, flag it.

**Logic**: Does each argument hold? Is cause-and-effect asserted without evidence? Are comparisons fair and accurate?

**Consistency**: Are the same products and terms spelled and referenced the same way throughout? Are there contradictions between sections?

**Voice**: Does the piece read like one person wrote it? Flag any sections where the tone shifts to content-marketer-style warmth, hype, or hedging.

**Second person**: Is the reader addressed as "you" throughout? Flag any sentence that substitutes "companies," "businesses," "marketers," or "teams" when the text is describing what the reader needs or gets.

**Sentence length**: Does every sentence in body copy meet the 10-word minimum? Flag every short fragment, even if it was used for rhetorical effect.

**Contrast structures**: Does the piece state claims positively and directly? Flag every negative-positive flip ("X isn't Y, it's Z"), every "not just X but Y," every "rather than X, Y," and every standalone negative sentence.

**Reader respect**: Does the content treat the reader as someone who already understands the basics, or does it over-explain, condescend, or repeatedly reassure them?

**Readability**: Common words. One idea per paragraph. Active voice. Most important information first in every section. Transition words that carry meaning ("but," "so," "still," "instead," "the catch is"). Formatted for scanning. Every sentence does real work.

---

## Output

Produce two things:

**1. Issue Log (printed first)**
List every issue found, grouped by type. Be specific — quote the exact text flagged and explain why it's a problem.

```
## Editorial QC — Issue Log
Date: [today's date]

### Structural Issues
1. [Issue description] — [quoted text or section name] — [recommended fix]

### Filler and Vague Claims
1. [Quote] — [problem] — [fix]

### Tone / Slop Patterns
1. [Quote] — [problem] — [fix]

### Logic / Consistency
1. [Issue]

### Overall Assessment
[2–3 sentences: honest summary of the content's quality level and the most important change needed]

### Publication readiness
Rate the piece on a single scale:
- **Not ready**: Would be cut or heavily rewritten by a senior editor at Forbes, The Verge, or the New York Times. List the top 3 reasons.
- **Close**: Would need one round of targeted edits before a senior editor would accept it. List what's missing.
- **Ready**: Passes the publication bar. A senior editor at a top-tier publication would approve this as written.

Do not mark a piece as Ready if any of the following remain: fragments under 10 words, negative-positive contrast structures, third-person reader-substitute language, vague claims without specifics, filler phrases, AI slop patterns, or robotic formality.
```

**2. Revised Content (after the issue log)**
Produce the full revised version of the content with all issues fixed. Do not summarise changes inline — just output the clean version.

Rules for the revision:
- Do not add new information not in the original (that's a separate step)
- Do not change the structure (that would require a new information architecture pass)
- Do not change the factual claims (that's the fact-check step)
- Only fix what's listed in the issue log — writing quality, not content substance

---

## Standalone Save

If invoked directly, ask:
"Save the revised content to file? Default: `./qc-revised-[date].md`"
Wait for confirmation, then save.
