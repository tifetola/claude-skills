# Claude Content Automation Skills

14 Claude Code custom skills for a complete SEO content production pipeline — from keyword research to published, conversion-optimized article.

The `/write-content` master skill orchestrates all phases in sequence. Every sub-skill can also be invoked independently.

---

## Pipeline

```
/write-content <keyword>
       │
       ├── Phase 1: Intelligence (parallel)
       │       ├── 1A. /search-intent      → decode what the searcher actually wants
       │       └── 1B. /serp-intelligence  → reverse-engineer what Google rewards
       │
       ├── Phase 2: Strategy
       │       └── /content-strategy       → pick the right format and angle
       │
       ├── Phase 3: Knowledge Building (parallel)
       │       ├── 3A. /subject-matter-brief   → verified product facts from live sources
       │       └── 3B. /research-synthesis     → consensus, contradictions, missing angles
       │
       ├── Phase 4: Structure
       │       └── /information-architecture  → full H1/H2/H3 outline (user approval pause)
       │
       ├── Phase 5: Draft Writing
       │
       ├── Phase 6: Quality Control (sequential)
       │       ├── 6A. /editorial-qc        → loop until zero issues remain
       │       ├── 6B. /fact-check          → verify every claim against primary sources
       │       ├── 6C. /on-page-seo         → titles, headings, schema, FAQs, meta
       │       └── 6D. /conversion-writing  → CTAs, objection handling, trust signals
       │
       └── Phase 7: Final Output → save to file
               └── /duda-publish           → optional: publish draft to Duda CMS
```

---

## Skills

### Master Pipeline

| Skill | Invocation | Description |
|---|---|---|
| **Write Content** | `/write-content <keyword>` | Runs all 10 phases in sequence. One keyword in, publication-ready article out. Quality bar: Forbes / NYT / The Verge. |

---

### Phase 1 — Intelligence

| Skill | Invocation | Description |
|---|---|---|
| **Search Intent** | `/search-intent <keyword>` | Decodes the psychology behind a query: primary intent, funnel stage, what would make a searcher bounce, and what would make this the definitive resource. |
| **SERP Intelligence** | `/serp-intelligence <keyword>` | Reads the top 5 organic results and extracts the format Google rewards, structural consensus, content gaps, and entity patterns. |

---

### Phase 2 — Strategy

| Skill | Invocation | Description |
|---|---|---|
| **Content Strategy** | `/content-strategy <keyword>` | Determines the right content format (listicle, comparison, how-to, etc.), the differentiated angle, scope boundaries, and target depth. Wrong format = weak outcome regardless of writing quality. |

---

### Phase 3 — Knowledge

| Skill | Invocation | Description |
|---|---|---|
| **Subject Matter Brief** | `/subject-matter-brief <product>` | Fetches live product facts — exact feature names, current pricing, verified integrations, known limitations — from primary sources. Flags anything unverifiable with `[VERIFY]`. |
| **Research Synthesis** | `/research-synthesis <topic>` | Reads 4–6 practitioner sources and extracts consensus, contradictions, missing angles, and the stronger perspective that most content hedges. |

---

### Phase 4 — Structure

| Skill | Invocation | Description |
|---|---|---|
| **Information Architecture** | `/information-architecture <topic>` | Builds the full H1 → H2 → H3 outline with section descriptions and word count budgets. Answers the primary question first, then structures complexity logically. Pauses for user approval before writing begins. |

---

### Phase 6 — Quality Control

| Skill | Invocation | Description |
|---|---|---|
| **Editorial QC** | `/editorial-qc` | The anti-slop pass. Reviews against the standard: would a senior editor at Forbes, The Verge, or the NYT pass this? Removes filler, repetition, vague claims, AI affectation, and structural bloat. Loops until zero issues remain. |
| **Fact Check** | `/fact-check` | Extracts every verifiable claim and checks each against its primary source. Corrects false or outdated information, inserts `[VERIFY]` for anything unconfirmable. |
| **On-Page SEO** | `/on-page-seo` | Writes 3 title tag options, H1, reviews all headings, optimises for featured snippets, checks entity coverage, writes FAQ section, and writes the meta description. |
| **Conversion Writing** | `/conversion-writing` | Adds a primary CTA and mid-article CTA (for 1500w+ pieces), handles objection sequencing, and ensures product mentions are integrated naturally — not bolted on. |

---

### Research & Audit

| Skill | Invocation | Description |
|---|---|---|
| **Keyword Research** | `/keyword-research <domain>` | Deep-dive keyword session producing ~100 prioritised keywords with no cannibalization, split across five bottom-funnel content categories. |
| **SEO Content Audit** | `/seo-content-audit <url>` | Full content audit: identifies thin pages, cannibalization, coverage gaps, update priorities, and a ranked action list. |

---

### Publishing

| Skill | Invocation | Description |
|---|---|---|
| **Duda Publish** | `/duda-publish` | Publishes a finished article as a draft to a Duda site via MCP. Saves as draft only — never auto-publishes. |

---

## Installation

These are [Claude Code](https://claude.ai/code) custom skills. To use them:

1. Clone this repo into your Claude skills directory:
   ```bash
   git clone https://github.com/tifetola/claude-skills.git ~/.claude/skills
   ```

2. Skills are automatically detected by Claude Code from `~/.claude/skills/`.

3. Invoke any skill by typing `/skill-name` in a Claude Code session.

---

## Quick Start

**Run the full pipeline:**
```
/write-content best CRM for small business
```

**Run a single phase:**
```
/keyword-research saas-company.com
/seo-content-audit https://example.com/blog-post
/search-intent b2b podcast agencies
```

**Research then write:**
```
/search-intent best project management tools
/serp-intelligence best project management tools
/write-content best project management tools
```

---

## Quality Bar

Every piece produced by this pipeline is held to a single standard: publishable in Forbes, The Verge, or the New York Times without a senior editor requiring cuts or rewrites.

The pipeline enforces this through:
- An editorial QC loop that repeats until zero issues remain
- Fact-checking against live primary sources (no training-data assumptions)
- A writing style guide that bans filler phrases, vague claims, AI affectation, and mechanical transitions
- Conversion optimization that integrates CTAs naturally rather than bolting them on
