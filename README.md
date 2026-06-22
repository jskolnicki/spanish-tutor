# Spanish Tutor via Claude Code

A personal Spanish tutor that lives in a folder and learns how you learn. No app, no subscription, no server — just Claude Code, a handful of Markdown files, and a session system that gets sharper every day you use it.

## What makes this different

Most language apps treat every user the same. This one doesn't.

Before your first real session, the tutor runs a diagnostic to find where you actually are — not where a beginner's track assumes you are. It measures your speed, identifies your weak spots, and calibrates the entire curriculum to your starting point. From that session forward, it remembers everything: what you've mastered, what you keep missing, how fast you're retrieving words, and what you still haven't seen.

Every session, the tutor:
- Reviews what's due based on spaced repetition — not a fixed schedule, but your performance
- Focuses extra reps on your actual weak spots, not generic drills
- Introduces new material only once you've consolidated what came before
- Tracks your speed over time, because fluency is about automaticity, not just accuracy

Miss something or hesitate? It resets to daily review until it's solid. Nail something fast? It backs off and gives you space. The system self-adjusts continuously — there's no manual difficulty setting because there doesn't need to be.

## The curriculum

26 grammar sections organized into 4 arcs, sequenced for conversational fluency:

- **Arc 1** — Core mechanics: gender agreement, present tense, ser/estar, questions & connectors, object pronouns, present progressive
- **Arc 2** — The past: preterite, imperfect, the preterite/imperfect decision, reflexives, acabar de, past progressive
- **Arc 3** — Future & obligation: ir a, future tense, conditional, tener que, commands
- **Arc 4** — Perfect tenses & subjunctive: present/past perfect, present subjunctive, subjunctive in context, por/para, imperfect subjunctive, perfect subjunctive, advanced tenses, passive voice

With daily practice, most learners work through the full curriculum in 3–4 months. After that, the system shifts to maintenance — everything keeps cycling back on longer intervals so nothing fades.

You can also name grammar priorities in your profile (e.g. "I need subjunctive for reading") and the tutor will advance you toward those sections once the foundation is in place.

## Requirements

- [Claude Code](https://claude.ai/code) (CLI or desktop app)
- A Claude account (Pro or above recommended for daily use)

No Python, no Node, no database.

## Setup

**1. Clone the repo and open it in Claude Code**

```bash
git clone https://github.com/jskolnicki/spanish-tutor.git
cd spanish-tutor
claude .
```

Or open the folder via the Claude Code desktop app.

**2. Create your profile file**

```bash
cp profile.template.md profile.md
```

Fill in your current level, what you already know, and what you want to focus on. The diagnostic will calibrate from here — the more honest you are, the faster it places you correctly.

**3. Start your first session**

In a new Claude Code conversation in this folder, type:

> **Start**

The tutor runs a one-time diagnostic to find your grammar frontier and measure your speed baseline. Every session after that picks up exactly where you left off.

## Daily use

| Command | What it does |
|---------|-------------|
| `Start` | Begins or continues the session — works for fresh days and continuations |
| `Quick session` | ~7 min: due vocab + one speed drill only |
| `I want a new topic` | Push ahead to new grammar |
| `Let's just review today` | Review only, no new material |
| `Let's do a roleplay` | Conversation practice in context |
| `Save` / `End` / `Wrap up` | Save progress and log the session — all equivalent, safe anytime |

## How grading works

- **Correct AND fast → advances** (up to B5, reviewed every 16 days)
- **Wrong OR slow → resets to B1** (reviewed tomorrow)

Hesitation counts as slow. The goal is automatic retrieval — the kind of speed that holds up mid-conversation, not careful deliberate recall.

## What's in the repo

| File | Purpose |
|------|---------|
| `CLAUDE.md` | The tutor's full operating manual. Auto-loaded by Claude Code. |
| `curriculum.md` | 26-section grammar roadmap with frameworks and examples. |
| `instructions.md` | Quick-reference cheat sheet for session commands. |
| `profile.md` | **Your file** — learner model: strengths, weak areas, speed baselines, interests. Gitignored. |
| `progress.md` | **Your file** — grammar SRS ledger with box + due date per section. Gitignored. |
| `vocab.md` | **Your file** — vocabulary deck sorted by due date. Gitignored. |
| `errors.md` | **Your file** — recurring mistake log with frequency counts. Gitignored. |
| `log.md` | **Your file** — append-only session journal. Gitignored. |

Your personal files are gitignored — they contain your data, not the template.

## Forking for your own use

This repo is meant to be forked. The public repo is the template; your fork is where your personal files live.

1. Fork this repo on GitHub
2. `profile.md`, `progress.md`, `vocab.md`, `errors.md`, and `log.md` are gitignored and stay local (or track them privately in your fork)
3. Fill in `profile.md` with your level and interests
4. Pull upstream to get curriculum or system improvements

## Typing accents in the terminal

Accent marks are never required — missing one won't count against you. The tutor always shows the correct accented form in its responses.

If you want to type accents, use a backtick immediately after the vowel:

| You type | Reads as |
|----------|----------|
| `hablo`` | habló |
| `aqui`` | aquí |
| `este`` | esté |
| `tu`` | tú |

The tutor interprets this silently before grading.

## Latin American Spanish

This tutor teaches **Latin American Spanish only** — `ustedes` for second-person plural, never `vosotros`. To adapt it for Castilian Spanish, modify `CLAUDE.md`.
