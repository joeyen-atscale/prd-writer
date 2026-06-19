# prd-writer

A Claude Code skill for anyone who has an idea and wants to turn it into something buildable.

You don't need to know how to code. You don't need to know what a "PRD" is. You just need to
have something you wish existed — a tool, an app, a script, a dashboard — and this skill will
help you describe it clearly enough that `/pybuilder` can build it for you.

## What it helps with

- **Journalling & reflection** — mood trackers, daily prompts, memory recall
- **Home life & automation** — chore rotations, grocery lists, morning routines, plant reminders
- **Photography** — auto-organizing by location, best-shot pickers, client delivery trackers
- **Music** — practice logs, setlist managers, chord idea pads
- **Art & design** — commission trackers, project galleries, color palette tools
- **Child monitoring** — screen time, homework reminders, reading progress
- **Elderly care** — medication reminders, daily check-ins, activity logs for caregivers
- **LinkedIn & networking** — follow-up trackers, post engagement logs, networking goals
- **Sales & freelance** — prospect pipelines, follow-up reminders, win/loss journals
- **Health & fitness** — workout logs, sleep journals, water intake trackers
- **Anything else** — if you have an idea, describe it and this skill will help you shape it

## How it works

Invoke `/prd-writer` in Claude Code and describe your idea in plain language — a sentence,
a ramble, anything. The skill asks a small number of focused questions, then produces a short
spec (a Personal Project PRD) that `/pybuilder` can build from.

The whole process takes about ten minutes.

## Install

```bash
curl -fsSL https://raw.githubusercontent.com/joeyen-atscale/prd-writer/main/install.sh | bash
```

Or from a local checkout:

```bash
git clone https://github.com/joeyen-atscale/prd-writer.git
cd prd-writer
bash install.sh
```

## Prerequisites

- **git**
- **[Claude Code](https://claude.ai/code)**

No Python, no build step. The skill is pure Markdown.

## What comes next

Once you have a spec, use [/pybuilder](https://github.com/joeyen-atscale/pybuilder) to build
it. Installing pybuilder also installs `/prd-writer`, so if you're planning to build — install
pybuilder instead and you get both in one step.
