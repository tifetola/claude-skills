# Claude Code SEO Skills

Two production pipelines for SEO content work — one that researches and plans content, one that researches and writes it. 22 skills total. Each can run as a full pipeline with a single command or be invoked phase-by-phase.

---

## Pipelines

| Pipeline | Command | What it does |
|---|---|---|
| **Topic Research** | `/topic-research <domain>` | Account intelligence → opportunity extraction → keyword validation → SERP qualification → commercial filtering → format decisions → prioritized roadmap |
| **Content Writing** | `/write-content <keyword>` | Search intent → SERP analysis → content strategy → product research → outline → draft → QC loop → fact-check → SEO → conversion → publish |

**Typical workflow:** run `/topic-research` to build the content roadmap, then run `/write-content` on each topic from the plan.

---

## Pipeline 1 — Topic Research

> **`/topic-research <client-domain>`**
>
> Full 7-phase pipeline. Account understanding to prioritized content roadmap. Two user approval checkpoints built in. Every phase is also available standalone.

```
/topic-research <client-domain>
       │
       ├── Phase 1: Business Context
       │       ├── Website crawl → product, ICP, pricing, features, differentiators
       │       └── Ahrefs site metrics → DR, top pages, organic keywords, competitors
       │                   ↓ [Approval checkpoint — confirm account picture]
       ├── Phase 2: Opportunity Extraction
       │       └── /opportunity-extraction → 7 types: competitor, objection, feature,
       │                                     use-case, industry, pain, winner expansion
       │                   ↓ [Approval checkpoint — confirm opportunity angles]
       ├── Phase 3: Keyword Validation
       │       └── /keyword-validation → Ahrefs matching + related terms, volume + KD
       │                                 per opportunity cluster
       ├── Phase 4: SERP Qualification
       │       └── /serp-qualification → live SERP check per candidate
       │                                 QUALIFY / CONDITIONAL / KILL verdicts
       ├── Phase 5: Business Fit Filter
       │       └── /business-fit-filter → 5 gates: pipeline, ICP, product fit,
       │                                  client alignment, cannibalization
       ├── Phase 6: Topic Shaping
       │       └── /topic-shaping → format per topic: alternatives page, comparison,
       │                            LP, pricing page, guide, use case, etc.
       └── Phase 7: Prioritization
               └── /topic-prioritization → 6-dimension scoring, 3-tier output,
                                           sequenced build queue
```

### Skills

| Phase | Skill | Command | What it does |
|---|---|---|---|
| **Master** | Topic Research | `/topic-research <domain>` | Runs all 7 phases. Account intelligence → prioritized roadmap. |
| Phase 1 | Business Context | `/business-context <domain>` | Account Intelligence Document: ICP, competitors, objections, commercial priorities, organic footprint. |
| Phase 2 | Opportunity Extraction | `/opportunity-extraction` | Extracts content opportunities from account intelligence. 7 types. Not keywords yet — business angles. |
| Phase 3 | Keyword Validation | `/keyword-validation` | Ahrefs validation: matching terms, related terms, volume + KD per opportunity. Ahrefs validates here — it doesn't set strategy. |
| Phase 4 | SERP Qualification | `/serp-qualification` | Checks what actually ranks. QUALIFY / CONDITIONAL / KILL per keyword. Many topics die here. That's the point. |
| Phase 5 | Business Fit Filter | `/business-fit-filter` | 5 commercial gates. Every surviving keyword passes: pipeline alignment, ICP, product fit, client alignment, cannibalization check. |
| Phase 6 | Topic Shaping | `/topic-shaping` | Assigns content format to every surviving topic. Flags architecture implications. |
| Phase 7 | Topic Prioritization | `/topic-prioritization` | 6-dimension scoring (1–3 each). Tier 1 ≥14, Tier 2 10–13, Tier 3 ≤9. Sequenced build queue. |

---

## Pipeline 2 — Content Writing

> **`/write-content <keyword>`**
>
> Full 10-phase pipeline. One keyword in, publication-ready article out. Quality bar: Forbes / NYT / The Verge. Every phase is also available standalone.

```
/write-content <keyword>
       │
       ├── Phase 1: Intelligence (parallel)
       │       ├── /search-intent      → decode what the searcher actually wants
       │       └── /serp-intelligence  → reverse-engineer what Google rewards
       │
       ├── Phase 2: Strategy
       │       └── /content-strategy   → pick the right format and angle
       │
       ├── Phase 3: Knowledge Building (parallel)
       │       ├── /subject-matter-brief   → verified product facts from live sources
       │       └── /research-synthesis     → consensus, contradictions, missing angles
       │
       ├── Phase 4: Structure
       │       └── /information-architecture → full H1/H2/H3 outline (approval pause)
       │
       ├── Phase 5: Draft Writing
       │
       ├── Phase 6: Quality Control (sequential)
       │       ├── /editorial-qc        → loop until zero issues remain
       │       ├── /fact-check          → verify every claim against primary sources
       │       ├── /on-page-seo         → titles, headings, schema, FAQs, meta
       │       └── /conversion-writing  → CTAs, objection handling, trust signals
       │
       └── Phase 7: Final Output → save to file
               └── /duda-publish        → optional: publish draft to Duda CMS
```

### Skills

| Phase | Skill | Command | What it does |
|---|---|---|---|
| **Master** | Write Content | `/write-content <keyword>` | Runs all 10 phases. One keyword in, publication-ready article out. |
| Phase 1 | Search Intent | `/search-intent <keyword>` | Decodes searcher psychology: primary intent, funnel stage, what makes them bounce, what makes this the definitive resource. |
| Phase 1 | SERP Intelligence | `/serp-intelligence <keyword>` | Reads top 5 results. Extracts the format Google rewards, structural consensus, content gaps, entity patterns. |
| Phase 2 | Content Strategy | `/content-strategy <keyword>` | Format decision, differentiated angle, scope boundaries, target depth. Wrong format = weak outcome regardless of writing quality. |
| Phase 3 | Subject Matter Brief | `/subject-matter-brief <product>` | Live product facts — exact feature names, current pricing, verified integrations, known limitations. Flags `[VERIFY]` for anything unconfirmable. |
| Phase 3 | Research Synthesis | `/research-synthesis <topic>` | Reads 4–6 practitioner sources. Extracts consensus, contradictions, missing angles, the stronger perspective most content hedges. |
| Phase 4 | Information Architecture | `/information-architecture <topic>` | Full H1 → H2 → H3 outline with section descriptions and word count budgets. Pauses for approval before writing begins. |
| Phase 6 | Editorial QC | `/editorial-qc` | The anti-slop pass. Removes filler, repetition, vague claims, AI affectation, structural bloat. Loops until zero issues remain. |
| Phase 6 | Fact Check | `/fact-check` | Every verifiable claim checked against its primary source. Corrects false/outdated information, inserts `[VERIFY]` for anything unconfirmable. |
| Phase 6 | On-Page SEO | `/on-page-seo` | 3 title tag options, H1, heading review, featured snippet optimisation, entity coverage check, FAQ section, meta description. |
| Phase 6 | Conversion Writing | `/conversion-writing` | Primary CTA + mid-article CTA (1500w+), objection sequencing, product mentions integrated naturally — not bolted on. |
| Phase 7 | Duda Publish | `/duda-publish` | Publishes finished article as a draft to Duda CMS via MCP. Saves as draft only — never auto-publishes. |

---

## Standalone Tools

| Skill | Command | What it does |
|---|---|---|
| **Keyword Research** | `/keyword-research <domain>` | Deep-dive keyword session. ~100 prioritised keywords, no cannibalization, split across five bottom-funnel content categories. |
| **SEO Content Audit** | `/seo-content-audit <url>` | Full content audit: thin pages, cannibalization, coverage gaps, update priorities, ranked action list. |

---

## Installation

```bash
git clone https://github.com/tifetola/claude-skills.git ~/.claude/skills
```

Skills are automatically detected by Claude Code from `~/.claude/skills/`. Invoke any skill by typing `/skill-name` in a Claude Code session.

---

## Quick Start

**Run the full topic research pipeline:**
```
/topic-research saas-company.com
```

**Run the full content writing pipeline:**
```
/write-content best prompt management tools
```

**Run a single phase:**
```
/search-intent langsmith alternatives
/serp-qualification langfuse alternatives
/keyword-research elacity.ai
```

**Research then write:**
```
/topic-research elacity.ai
/write-content langsmith alternatives
```

---

## Quality Bar

Every article produced by the writing pipeline is held to one standard: publishable in Forbes, The Verge, or the New York Times without a senior editor requiring cuts or rewrites.

Enforced through:
- An editorial QC loop that repeats until zero issues remain
- Fact-checking against live primary sources — no training-data assumptions
- A writing style guide that bans filler phrases, vague claims, AI affectation, and mechanical transitions
- Conversion optimization that integrates CTAs naturally rather than bolting them on

Every topic plan produced by the research pipeline is held to one standard: every topic must have a clear commercial path to pipeline, not just traffic.

Enforced through:
- SERP qualification that kills topics where the product category doesn't fit
- A commercial gate that filters on ICP match, not just search volume
- Scoring that weights commercial intent and ranking feasibility over raw keyword volume
