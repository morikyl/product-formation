# Product Formation Skill

This folder is the installable Skill package.

## What It Does

Product Formation runs a guided interview that turns a fuzzy product idea — for a startup, app, AI tool, SaaS, internal tool, or creative side project — into a clear, code-generation-ready brief.

It adapts depth to the use case:

- **Business / startup**: rigorous evidence-driven PM mode. Probes target user, current workaround, demand evidence, premise, MVP wedge, AI/technical feasibility, business model, metrics, and risks.
- **Personal / creative**: patient teaching coach mode. Skips evidence/risk probing, teaches PM concepts (persona, MVP) as it goes, and stays encouraging.

Both paths end with the same screen-level UI and interaction brief, ready to hand to a code-generating AI. The business path additionally produces a PRD-style strategy doc above the brief.

## Files

```text
SKILL.md
README.md
```

## How It Works

1. **Route first.** The Skill opens with one question: business/startup, personal/creative, or unsure?
2. **Branch interview.** It runs the matching question sequence, one question per turn, waiting for each answer before moving on.
3. **Shared finale.** Once the core feature is locked, both paths walk through one screen: visible elements, then every interaction, including empty/error/success states.
4. **Delivery.** Only when the user signals "done" — or the Skill has covered the path's steps and the user confirms nothing else to add — does it produce the brief. For first-time users, it offers them the chance to write the brief themselves first and compare against a "pro version."

## Try It

Send the Skill a fuzzy idea:

```text
I want to build an app that helps me track decisions I've made and how they turned out.
```

Expected behavior:

- asks one routing question first (business vs. personal vs. unsure)
- runs the matching interview branch one question at a time
- ends with a screen-level UI + interaction brief
- offers to let the user write the brief themselves first, then provides a pro version

## Installation

### Claude Code (one command)

Clone the Skill into your user-level Skills directory:

```bash
mkdir -p ~/.claude/skills && git clone https://github.com/morikyl/product-formation.git ~/.claude/skills/product-formation
```

Then start a new Claude Code session so the Skill metadata is discovered.

To update:

```bash
git -C ~/.claude/skills/product-formation pull
```

To uninstall:

```bash
rm -rf ~/.claude/skills/product-formation
```

### Manual install (other Skill-aware harnesses)

Copy this folder into your local Skills directory. The installed structure should look like:

```text
skills/
  product-formation/
    SKILL.md
    README.md
```

Then start a new assistant session so the Skill metadata can be discovered.
