# Art Director Skill

![Skill illustration](assets/illustration.png)

Iterative visual style search for media assets with branch prompts, process logs, rendered decision graphs, feedback loops, and final direction selection.

## Problem

Visual exploration often gets lost in chat: variants are generated, reviewers comment, and the next pass forgets which direction was selected, rejected, or carried forward.

## Solution

The skill turns a style brief into option clusters, rendered previews, selection notes, next-iteration branches, and a reproducible process log.

## What it creates

- Prompt files for each branch
- Process logs with safe feedback summaries
- Style-system notes
- Asset folders for generated or collected variants
- HTML preview pages with a decision graph
- Selection records with carry-forward and drop rules
- A starter HTML template at `assets/style-search-map-template.html`

## When to use

- Visual direction research
- Image-generation style exploration
- Cover, poster, carousel, comic, or video-look experiments
- HTML preview pages with a direction graph
- Review feedback that must become the next branch set
- Final style selection with carry-forward and drop rules

## Output shape

A typical run lives under `art-direction/<project>/`:

```text
art-direction/<project>/
  prompts/vNN/YYYY-MM-DD-vNN-<slug>-prompts.md
  process/vNN/YYYY-MM-DD-vNN-<slug>-log.md
  styles/YYYY-MM-DD-<style-system>.md
  assets/vNN-<slug>/
  vNN-<slug>.html
```

The preview starts with an iteration-cluster graph: idea, checkpoints, option leaves, selected nodes, rejected nodes, outputs, and next branches.

## First run

In an empty media workspace:

```bash
mkdir -p art-direction/<project>/{prompts/v01,process/v01,styles,assets/v01-style-search}
cp skills/art-director/assets/style-search-map-template.html art-direction/<project>/v01-style-search.html
python3 -m http.server 8080
```

Open `http://127.0.0.1:8080/art-direction/<project>/v01-style-search.html` and replace the sample cluster data with the current brief.

## Workflow

1. Read existing project files.
2. Identify the active style question.
3. Build an iteration cluster before generating variants.
4. Write branch prompts with difference axes and reject criteria.
5. Generate or collect assets through the host repo's approved path.
6. Render the decision graph and preview cards.
7. Turn feedback into the next branch set.
8. Record the selected direction and the next action.

## Decision graph contract

The graph should show the method, not only the images: root idea, iteration checkpoints, option leaves, selected nodes, rejected nodes, outputs, safe feedback summaries, carry-forward rules, dropped motifs, and next branches.

## Safety and source boundaries

The public skill is generic. Host repos should keep private chats, screenshots, auth material, billing records, customer records, infrastructure details, non-public repository links, and unsafe source material out of prompts and public previews.

## Validation

Run the checks in [SKILL.md](SKILL.md) for the current pass. At minimum, verify that the HTML preview exists, graph terms are present, prompt and process files exist, and `git diff --check` passes.

## Installation

```bash
cp -r skills/art-director ~/.claude/skills/
```

The skill is then available in Claude Code.

## How to invoke

Tell the agent:

> "Use art-director to explore three visual directions for this media campaign."

Or:

> "Run art-director on this preview and turn my feedback into the next style branches."

## See also

- [SKILL.md](SKILL.md) - full skill specification
- [README.ru.md](README.ru.md) - Russian version
