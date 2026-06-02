# Corp New Skill

![Skill illustration](assets/illustration.png)

Create or verify a private `corp-*` department repository and register it in a local HQ Markdown file.

## Problem

Founder or company work often spreads across many functional departments: media, legal, sales, analytics, operations. Each department needs a clear owner repo, a private GitHub remote, and one HQ index row so agents know where the source of truth lives.

## Solution

`corp-new` turns a department name into a safe, repeatable setup:

- normalize a `corp-*` slug;
- inspect local, GitHub, and HQ state before making changes;
- create or clone the private GitHub repository;
- preserve dirty worktrees and committed history;
- register exactly one HQ row with local and GitHub links;
- verify visibility, default branch, remote, and HQ registration.

## What It May Change

With explicit approval, the skill may create a local folder, initialize git, create a private GitHub repository, clone an existing repository, commit a minimal README, push committed work, fetch from origin, and edit one HQ table row.

## Configuration

Provide these values in the prompt, project instructions, or environment:

| Value | Env var | Example |
|---|---|---|
| Department label | `DEPARTMENT_LABEL` | `Media` |
| Department domain | `DEPARTMENT_DOMAIN` | `media assets and publishing workflows` |
| GitHub owner or org | `GITHUB_OWNER` | `your-org` |
| Local repositories root | `CORP_REPOS_ROOT` | `~/Documents/GitHub` |
| HQ Markdown file | `HQ_FILE` | `~/Documents/ops/AGENTS.md` |
| Repository prefix | `REPO_PREFIX` | `corp-` |
| Optional slug override | `DEPARTMENT_SLUG` | `corp-media` |

The skill asks before making changes if the department label, department domain, GitHub owner, or HQ file is unknown. Repositories are private by design.

The HQ file should contain or accept a department table with columns equivalent to: department label, repository links, and short domain.

## Example Prompts

```text
Use corp-new to create a Media department. Owner is my-org, repos live in ~/Documents/GitHub, HQ file is ~/Documents/company/AGENTS.md, domain is "media assets and publishing workflows". Show the dry run and ask before creating the repo or editing HQ.
```

```text
Use corp-new to verify corp-analytics already exists locally and on GitHub, then register it in our HQ file.
```

```text
Use corp-new to clone my-org/corp-legal into my workspace and add the HQ department row.
```

## Safety Model

- Creates private repositories by default.
- Shows a dry-run summary before making changes.
- Preserves existing folders and dirty worktrees.
- Never force-pushes, resets, deletes, or discards user work.
- Does not edit archive/history folders.
- Keeps HQ as an index and links to the owner repo instead of copying department content.

## Installation

```bash
cp -r skills/corp-new ~/.claude/skills/
```

## See Also

- [SKILL.md](SKILL.md) — full workflow and validation gates
- [project-init](../project-init/) — initial GitHub operating-system setup
- [task-routing](../task-routing/) — route issues across existing repos
