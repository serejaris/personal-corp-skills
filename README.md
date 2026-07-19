# Personal Corp Skills

[![en](https://img.shields.io/badge/lang-en-blue.svg)](README.md)
[![ru](https://img.shields.io/badge/lang-ru-green.svg)](README.ru.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Validate](https://github.com/serejaris/personal-corp-skills/actions/workflows/validate.yml/badge.svg)](https://github.com/serejaris/personal-corp-skills/actions/workflows/validate.yml)

> Public skills and plugin manifests for Claude Code and Codex: Personal Corp, product work, AI operations, and agent-assisted development.

By [Ris](https://t.me/ris_ai) — AI development & vibecoding

Русская версия: [README.ru.md](README.ru.md).

A collection of sanitized public skills, scripts, and workflows for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and Codex.

## Install

### Claude Code

Terminal:

```bash
claude plugin marketplace add serejaris/personal-corp-skills
claude plugin install personal-corp-skills@personal-corp-skills
claude plugin details personal-corp-skills
```

Claude Code Desktop or interactive `/plugin` flow:

1. Open **Plugins** or `/plugin`.
2. Add marketplace: `serejaris/personal-corp-skills`.
3. Install `personal-corp-skills`.

### Codex

This repo includes a Codex plugin manifest at [.codex-plugin/plugin.json](.codex-plugin/plugin.json).
Add the marketplace from GitHub, then install the plugin:

```bash
codex plugin marketplace add serejaris/personal-corp-skills
codex plugin add personal-corp-skills@personal-corp-skills
```

After installation, start a new Codex thread and try:

```text
Use Personal Corp skills to plan my week.
```

### Single Skill

Use this when you want one skill folder instead of the whole plugin:

> Install this skill: `https://github.com/serejaris/personal-corp-skills/tree/main/skills/cc-analytics`

Replace `cc-analytics` with any skill name from the table below.

## Skills

| Skill | What it does |
|-------|-------------|
| [art-director](./skills/art-director/) | Iterative visual style search with prompts, process logs, assets, and decision graphs |
| [product-data-audit](./skills/product-data-audit/) | Deep product/business audit → interactive HTML report with 12 sections |
| [cc-analytics](./skills/cc-analytics/) | HTML reports of Claude Code usage statistics |
| [ceo-council](./skills/ceo-council/) | Parallel sub-agents as C-level experts for strategic analysis |
| [claude-md-writer](./skills/claude-md-writer/) | Create and refactor CLAUDE.md files following best practices |
| [corp-new](./skills/corp-new/) | Add a private corp-* department repo and HQ entry after approval |
| [safe-public-release](./skills/safe-public-release/) | Provenance, licensing, security allowlist, approval, and fresh-clone verification for public artifacts |
| [design-minimal](./skills/design-minimal/) | Standalone minimal HTML pages for dashboards, briefs, handouts, and reports |
| [gh-issues](./skills/gh-issues/) | Manage GitHub Issues via CLI with session context |
| [meeting-copilot](./skills/meeting-copilot/) | Live meeting dashboard: prepare, update from transcript chunks, close with decisions and follow-ups |
| [readme-generator](./skills/readme-generator/) | Human-focused README files with proper structure |
| [manager](./skills/manager/) | Bidirectional bridge between the current session and GitHub Issues |
| [idea](./skills/idea/) | Capture one voiced idea into a provenance-tracked folder, dedup against an index, optional GitHub Project mirror |
| [pm-prioritize](./skills/pm-prioritize/) | Rank backlogs with RICE, ICE, MoSCoW, or Kano and produce a decision log |
| [pm-prd](./skills/pm-prd/) | Structured PRD generation with product-type templates and quality checklist |
| [pm-user-stories](./skills/pm-user-stories/) | Break Epics into INVEST-validated User Stories with Story Map output |
| [pm-competitive](./skills/pm-competitive/) | Multi-dimensional competitor analysis with SWOT and differentiation strategy |
| [pm-feedback](./skills/pm-feedback/) | Classify user feedback, cluster themes, and rank actionable pain points |
| [pm-brainstorm](./skills/pm-brainstorm/) | Structured product ideation with SCAMPER and Impact/Effort screening |
| [pm-metrics](./skills/pm-metrics/) | Product metrics review — trends, funnel/retention diagnostics, OKR alignment |
| [pm-roadmap](./skills/pm-roadmap/) | Update Now/Next/Later roadmap with delay attribution and scope-cut framework |
| [html-draft](./skills/html-draft/) | One self-contained HTML diagram in flat engineering blueprint style — architecture, flows, spec sheets |
| [parallel-design-variants](./skills/parallel-design-variants/) | Parallel design bake-off: N divergent directions via subagents, gallery, vote, then mix the winners |
| [fable-ruki-agenty](./skills/fable-ruki-agenty/) | Manually-invoked orchestration mode: Fable writes self-sufficient specs into GitHub issue bodies and dispatches ready tasks to Sonnet subagents; never writes code itself |
| [grill-me](./skills/grill-me/) | Relentless one-question-at-a-time interview about a plan until shared understanding; every fork becomes an explicit decision with a recommendation |
| [to-prd](./skills/to-prd/) | Synthesize the conversation into `PRD.md` in the project folder — no interview; testing seams; follows grill-me |
| [to-issues](./skills/to-issues/) | Split a PRD/spec into `tasks/NN-slug.md` — vertical tracer-bullet slices with acceptance criteria and dependencies |
| [tg-bot-ops](./skills/tg-bot-ops/) | Reusable operations playbook for Telegram bots and Telegram-to-agent gateways |

### Design and Media Skills

| Skill | Use When |
|-------|----------|
| [art-director](./skills/art-director/) | Iterative art direction, visual style search, generation branches, and decision graphs |
| [design-minimal](./skills/design-minimal/) | Reading-first standalone HTML pages: dashboards, briefs, handouts, operating maps, reports |
| [html-draft](./skills/html-draft/) | Technical diagrams in flat engineering blueprint style: architecture, system flows, spec sheets |
| [parallel-design-variants](./skills/parallel-design-variants/) | Several genuinely different design directions to choose from — redesign, hero, landing, thumbnail; live bake-off with voting |

### Product Management Skills

| Skill | Use When |
|-------|----------|
| [pm-feedback](./skills/pm-feedback/) | Reviews, NPS exports, or support tickets need theme clustering and pain ranking |
| [pm-competitive](./skills/pm-competitive/) | Entering a category, fundraising prep, or differentiation before a PRD |
| [pm-brainstorm](./skills/pm-brainstorm/) | Structured ideation before quarterly planning or a new product bet |
| [pm-prioritize](./skills/pm-prioritize/) | Backlog is too large — rank with RICE, ICE, MoSCoW, or Kano |
| [pm-prd](./skills/pm-prd/) | Top requirements need a delivery-ready requirements document |
| [pm-user-stories](./skills/pm-user-stories/) | PRD or Epic is ready to split into sprint-sized User Stories |
| [pm-metrics](./skills/pm-metrics/) | Weekly/monthly metrics review, A/B reads, or OKR pacing checks |
| [pm-roadmap](./skills/pm-roadmap/) | Sprint close or stakeholder review needs an updated Now/Next/Later roadmap |

```mermaid
graph LR
    pmFeedback[pm-feedback] --> pmPrioritize[pm-prioritize]
    pmCompetitive[pm-competitive] --> pmPrioritize
    pmBrainstorm[pm-brainstorm] --> pmPrioritize
    pmPrioritize --> pmPrd[pm-prd]
    pmPrd --> pmUserStories[pm-user-stories]
    pmMetrics[pm-metrics] --> pmRoadmap[pm-roadmap]
    pmRoadmap --> pmPrioritize
```

### Telegram

| Skill | Use When |
|-------|----------|
| [tg-bot-ops](./skills/tg-bot-ops/) | Telegram bot and Telegram-to-agent gateway incidents, webhook/polling diagnostics, safe restart plans, Bot API smoke tests, forum topic delivery |

#### Personal Corp Framework

A system for running a business as one person with AI agents. GitHub becomes your operating system.

```mermaid
graph LR
    A[project-init] -->|creates config| B[task-routing]
    B -->|creates issues| C[weekly-planning]
    C -->|prioritizes| D[weekly-retro]
    D -->|feeds back| C
    style A fill:#10b981,color:#fff
    style B fill:#8b5cf6,color:#fff
    style C fill:#3b82f6,color:#fff
    style D fill:#f59e0b,color:#fff
```

| Skill | What it does |
|-------|-------------|
| [project-init](./skills/project-init/) | Guided interview → GitHub Project + labels + CLAUDE.md config |
| [corp-new](./skills/corp-new/) | Register a private corp-* department repo and HQ entry after approval |
| [safe-public-release](./skills/safe-public-release/) | Turn private/vendor/runtime artifacts into approved, sanitized, publicly verified packages |
| [task-routing](./skills/task-routing/) | Route issues to the correct repo using routing config |
| [weekly-planning](./skills/weekly-planning/) | Retro findings + backlog → prioritized outcomes with Eisenhower matrix |
| [weekly-retro](./skills/weekly-retro/) | Structured retrospective: gather data, interview founder, capture findings |
| [manager](./skills/manager/) | Sync session work into GitHub Issues and query cross-repo task state |
| [pm-prioritize](./skills/pm-prioritize/) | Rank requirements and backlogs before planning |

## Other

### [Statusline](./statusline/)
Custom statusline showing costs, context usage, and git branch with color-coded indicators.

## Archived Skills

Archived skills are preserved for reference and are not part of the active
plugin skill set.

| Skill | Notes |
|-------|-------|
| [paperclip-api](./archive/skills/paperclip-api/) | Historical Paperclip API helper; kept for reference |

## Manual Installation

Skills are plain folders. Copy the whole skill directory so optional references
and examples are preserved:

```bash
cp -r skills/<name> ~/.claude/skills/
```

## Author

- Telegram: [@ris_ai](https://t.me/ris_ai) — AI development & vibecoding
- YouTube: [@serejaris](https://www.youtube.com/@serejaris)
- [vibecoding.phd](https://vibecoding.phd)

## License

MIT

## Security

Please report secrets, private data exposure, or exploitable behavior privately.
See [SECURITY.md](SECURITY.md).
