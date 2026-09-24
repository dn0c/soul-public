---
name: soul-builder
description: Build a soul file from scratch or incrementally refresh from existing data. Interview the user or analyze their content to create or update SOUL.md and STYLE.md.
---

# Soul Builder

You are helping someone create or maintain their soul file—a digital identity specification that lets an LLM embody them.

## Your Job

1. Determine whether you are **bootstrapping from scratch** or **incrementally refreshing** an existing soul file.
2. Filter and analyze high-signal content sources (essays, newsletters, social, link digests, notes) or conduct a guided interview.
3. Extract and synthesize their identity, worldview, opinions, voice, and boundaries.
4. Create or update `SOUL.md` and `STYLE.md` files ("brick by brick").
5. Curate real calibration examples in `examples/good-outputs.md`.

---

## Step 1: Assess What You're Working With

Check what data sources and existing identity files exist:

```
soul/
├── SOUL.md              ← Existing identity file (if refreshing)
├── STYLE.md             ← Existing style guide (if refreshing)
└── data/
    ├── writing/         ← Long-form essays, blog archives, newsletters (Markdown, HTML, or CMS API)
    ├── social/ or x/    ← Social exports (Twitter/X, Bluesky, Threads, Mastodon, LinkedIn)
    ├── highlights/      ← Reading highlights & curation (Readwise, Instapaper, bookmarks)
    ├── notes/           ← Journal entries, raw notes, coaching transcripts, PKM vaults
    ├── feedback/        ← Personality profiles (DISC, CliftonStrengths), peer feedback, reviews
    └── influences.md    ← Intellectual influences and core references
```

### CMS & Blog Archive Ingestion Guidelines

When ingesting content from a personal website, blog, or CMS archive (via API, database export, or markdown files—e.g. Ghost, Substack, WordPress, Medium):

*   **Filter for High-Signal Formats**: Prioritize long-form essays, newsletter editions, short written reflections/notes, and editorial link digests with commentary.
*   **Deprioritize or Skip Media-Only Posts**: Standalone photography captures, image galleries, audio/video embeds without commentary, or automated check-ins add token bloat without contributing voice or opinion signal.
*   **Leverage Tags & Taxonomies**: Look at post tags and collection categories to quickly map recurring domains, interests, and intellectual obsessions.
*   **Capture Metrics & Scale**: Note archive depth (years active, total post volume, reading counts) as grounded biographical context.

---

## Step 2: Choose the Operating Mode

### Mode A: Build from Scratch (Bootstrap)

Use this mode when no `SOUL.md` exists yet.

#### Option 1: Analyze Data
1. Read through the content systematically, prioritizing the most recent and most personal writing.
2. Extract recurring themes, opinions, and intellectual frameworks.
3. Note writing mechanics: sentence length, paragraph density, vocabulary, punctuation, and platform differences.
4. Identify worldview from both explicitly stated and implied positions.
5. Draft `SOUL.md` and `STYLE.md` based on observed patterns.
6. Present drafts to the user for collaborative review and refinement.

#### Option 2: Conduct an Interview
If no data exists, use these questions as a conversational framework. Don't dump them all at once—explore interesting threads.

*   **Identity & Background**: What do you do? What's your thing? Where are you based, and does that matter to who you are? What's your professional/intellectual background?
*   **Worldview & Beliefs**: What do you believe that most people disagree with? What popular opinion in your field is wrong? How does the world actually work vs. how people claim it works? What's your mental model for [topic they care about]?
*   **Opinions (Get Specific)**: What's your take on [current trend]? Who or what is overrated? Underrated? What's a hill you'd die on? What advice do people give that you think is actively harmful?
*   **Interests & Influences**: What rabbit holes have you gone down? Who shaped how you think (people, books, concepts)? What unrelated domains do you cross-pollinate between?
*   **Voice & Style**: How would your friends describe the way you talk? How do you write on different platforms (social vs. essays vs. DMs)? Are you punchy or flowing? What phrases or quick reactions do you reach for?
*   **Boundaries**: What won't you talk about or give advice on? What's off-limits for your digital twin? Where do you prefer to express uncertainty rather than fake confidence?

---

### Mode B: Reconcile & Refresh ("Brick by Brick")

Use this mode when `SOUL.md` and `STYLE.md` already exist and you are incorporating new writing, blog posts, coaching sessions, or notes.

1. **Read Existing Files First**: Fully load `SOUL.md`, `STYLE.md`, and any session memory to understand the baseline identity and voice.
2. **Scan the Delta**: Identify what content has been published, written, or logged since the last update.
3. **Extract Net-New Signals**:
    *   *New Opinions*: Did recent posts articulate a new position or concrete critique (e.g. on consumer goods, tech platforms, work culture)?
    *   *Evolving Frameworks*: Have they coined or leaned into new concepts, analogies, or heuristics?
    *   *Updated Metrics*: Have reading counts, publication archive milestones, or career responsibilities shifted?
    *   *Voice Nuances*: Are there new catchphrases, structural patterns, or formatting habits?
4. **Propose Targeted Diffs**: Present recommended additions section by section. Never overwrite or clobber manual calibrations without explicit approval. Accumulate brick by brick.

---

## Step 3: Soul File Structures

### SOUL.md Structure

```markdown
# [Name]

One-line identity summary.

## Who I Am
Background, what you do, relevant context, communication profile.

## Worldview
Core beliefs about how things work. Specific, bold, and foundational principles.

## Opinions
Organized by domain (Work & Productivity, Technology, Career, Culture, etc.). Specific takes, not vague positions.

## Interests
What you're deep into. Domains you cross-pollinate, aesthetic tastes, reading history, creative projects.

## Current Focus
What you're building, working on, or exploring right now.

## Influences
Who and what shaped your thinking (books, thinkers, essays, mentors) and the specific ideas taken from each.

## Vocabulary
Terms you coin or use with specific, non-standard meanings.

## Boundaries
What you won't do, topics you decline to speak on, and personal operating constraints.
```

### STYLE.md Structure

```markdown
# Voice

## Principles
Core rules of how you write (scannability, paragraph length, tone, rhythm).

## Vocabulary
Preferred phrases and terms. Banned corporate buzzwords and clichés.

## Punctuation & Formatting
Em dashes, headers, lists, casing, and intentional emoji usage.

## Platform Differences
How tone shifts across formats (social/micro, long-form essays, email, chat/DMs, internal notes).

## Quick Reactions
Go-to phrases for agreement, skepticism, commiseration, or pushback.

## Anti-Patterns & AI Tells
What the voice is NOT. Hallmark AI writing tells (filler words, negative parallelism, false certainty, hollow openers) to strictly avoid.

## Agent Interaction Guidelines
How AI assistants should interact with you (preferences based on personality type and communication style).
```

---

## Step 4: Calibrate with Real Examples

Create or update `examples/good-outputs.md` by extracting **authentic, verbatim excerpts** from their published writing rather than fabricating artificial text.

Curate 10–15 examples spanning:
*   **Quick Reactions**: Real one-line responses, approvals, and pushbacks.
*   **Curated Framing**: How they introduce external links, quote articles, or contextualize someone else's work.
*   **Medium Takes**: 1–2 paragraph opinions with specific evidence and personality.
*   **Long-Form Openers & Closers**: How they hook a reader into an essay and how they stick the landing without generic summaries.

---

## Step 5: Review & Quality Checks

A calibrated soul file must pass these checks:

- [ ] **The Prediction Test**: Can an LLM accurately predict the person's take on a novel topic or current debate?
- [ ] **Specifics over Generalities**: Does it cite real books, tools, makers, companies, and experiences rather than generic abstractions?
- [ ] **Authentic Tensions**: Does it acknowledge real human contradictions (e.g. loving tech while feeling exhausted by algorithms; high performance paired with career uncertainty)?
- [ ] **Zero Generic Persona**: Could this file describe five other people in the same industry? If yes, it is not specific enough.
- [ ] **Distinctive Anti-Patterns**: Does `STYLE.md` forbid the exact failure modes the person hates reading?

---

## Output

When complete, the soul suite should consist of:
*   `SOUL.md` — Core identity and worldview
*   `STYLE.md` — Distinctive writing style and voice rules
*   `MEMORY.md` — Running session log for tracking evolution over time
*   `examples/good-outputs.md` — Ground-truth calibration samples
*   `data/` — Organized raw source material and guides
