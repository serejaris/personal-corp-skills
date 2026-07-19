# Safe Public Release Skill

Prepare private, vendor-provided, runtime-generated, or mixed artifacts for a public repository or registry without leaking secrets, private state, user data, or material that cannot be redistributed.

## Problem

A request such as “publish these skills” often points at a working directory that mixes reusable source with caches, logs, credentials, absolute private paths, vendor assets, generated files, and unclear licenses. Creating a public repository first makes the risky decision before the evidence exists.

## Solution

`safe-public-release` applies an allowlist-first release pipeline:

1. create an internal owner issue tree;
2. inventory every candidate artifact and companion file;
3. prove provenance and redistribution rights;
4. classify security/privacy risks;
5. build a clean staging tree from an explicit allowlist;
6. show an approval dry run before any outward mutation;
7. publish only the approved artifact set;
8. verify a fresh public clone, install/discovery command, and repeated scans;
9. assign a maintenance owner and capture new lessons.

## Use It For

- agent skills and plugin bundles;
- prompts, templates, playbooks, starter kits;
- reusable code extracted from private projects;
- course or workshop assets selected for public release;
- benchmark fixtures and datasets;
- vendor/runtime exports with uncertain provenance;
- demo repositories for community or developer programmes.

## Safety Model

- Public publication always requires explicit approval after the dry run.
- Unknown provenance or license blocks the artifact.
- Attribution never substitutes for redistribution permission.
- The package is built from an explicit allowlist, not copied wholesale and cleaned later.
- Credentials, runtime state, histories, user data, private paths, and unreviewed vendor assets are excluded.
- `PUBLISHED` is not done; the release must pass fresh public clone/install/discovery verification.

## Included Templates

- [release-manifest.example.yaml](references/release-manifest.example.yaml) — artifact provenance, licensing, allowlist, scan, and verification record.
- [release-checklist.md](references/release-checklist.md) — dry-run and publication checklist.

## Example Prompts

```text
Use safe-public-release to prepare these agent skills for a public GitHub repository. Build the inventory and allowlist, but stop before creating or pushing the public repo.
```

```text
Review this private template repository for public release. Show me which files are allowed, blocked, or need licensing clarification, then present the approval dry run.
```

```text
Publish the approved package from the existing release manifest, then verify it from a fresh public clone. Stop if the target or artifact set differs from the approval.
```

## Installation

```bash
cp -r skills/safe-public-release ~/.claude/skills/
```

## See Also

- [SKILL.md](SKILL.md) — complete workflow and hard gates
- [release manifest template](references/release-manifest.example.yaml)
- [release checklist](references/release-checklist.md)
- [corp-new](../corp-new/) — create a private `corp-*` department after a separate approval
- [manager](../manager/) — maintain the cross-repository owner issue tree
