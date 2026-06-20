# prd-writer

A Claude Code skill that turns "I wish something existed that did this" into a spec another tool can build from.

## Why it exists

The gap between an idea and a working app is rarely coding ability. It's the ability to describe what you want clearly enough that something can be built from it. You know the itch — the spreadsheet you keep redoing by hand, the reminder you keep forgetting, the tool you've searched for and can't find. What's missing is the translation from that feeling into a plan.

That's the whole job of this skill. You describe the idea in plain language; it asks a few focused questions; it hands back a short spec you can read, recognize as your own idea, and pass to a builder. No code, no jargon, no filling in a form.

It's aimed at people building for themselves and the people around them — hobbyists, makers, artists, musicians, parents, caregivers, freelancers. For enterprise or B2B product specs, that's a different skill (`/atscale-prd-writer`).

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

Either way, the installer symlinks the skill into `~/.claude/skills/prd-writer`. The skill is pure Markdown, so there's no Python and no build step — you need only `git` and [Claude Code](https://claude.ai/code).

## First run

Open Claude Code and type:

```
/prd-writer
```

Then describe your idea however it comes out — a sentence, a paragraph, a ramble. The skill works backward from there, asking a small set of questions: what's the itch, who uses it, the three things it must do, what "done" looks like, and what it deliberately won't do yet. It takes about ten minutes.

What you get back is a **Personal Project PRD** — a short, plain-English document with these parts:

- **The idea**, in one sentence
- **The person it's for** — named and specific, not "a user"
- **The problem it replaces** — what you do by hand today
- **The three things it must do** in v1
- **What good looks like** — how your day changes
- **Where it lives** — terminal command, web page, desktop app, dashboard
- **The honest boundary** — what v1 explicitly does *not* do

## How it works

The skill leans on two ideas that make personal projects actually ship.

The first is that the hard part is scoping, not features. A v1 that does three things well gets built and used; one that tries to do thirty gets abandoned. So the questions push toward the core, and the template forces an explicit boundary — the sentence "in v1, it does NOT do X" is what keeps a weekend project from becoming a dead repo.

The second is that the *feel* of the thing is real design information. A parent's medication reminder should feel reassuring; an artist's commission tracker should feel calm and organized. The skill asks for that on purpose, because it changes the build.

## Where it fits

`prd-writer` produces the input; [`/pybuilder`](https://github.com/joeyen-atscale/pybuilder) does the building. Hand it the PRD and it runs the full loop — scaffold, iterate, prove, gate — into working Python. The two share a format on purpose: no translation step between them.

Installing pybuilder also installs `prd-writer`. If you already know you want to build, install pybuilder and you get both.

If it's your first build, start with `--target cli` whatever your eventual goal — a command-line tool is the shortest path to something real you can use, and you can put a web or phone interface on top of it later.

## Status

Released, version 1.0.0. The skill is a single Markdown file; everything it does is in `skill/SKILL.md`, which is also worth reading directly if you want to see the questions and the full template before you run it.
