# Meeting Copilot Skill

![Skill illustration](assets/illustration.png)

A Claude Code skill for running a live meeting with a local AI copilot dashboard.

## Problem

During calls, important questions, decisions, risks, and follow-ups are easy to lose. Raw transcripts help after the fact, but they do not guide the meeting while it is happening.

## Solution

The agent creates a local HTML dashboard before the meeting, updates it from transcript chunks during the call, and closes the session into a structured summary.

Core loop:
- **CREATE** — prepare briefing, questions, topic map, and follow-up sections
- **UPDATE** — turn transcript deltas into live dashboard changes
- **CLOSE** — extract decisions, action items, open questions, and a follow-up draft

## Installation

```bash
cp -r skills/meeting-copilot ~/.claude/skills/
```

## Example Prompts

```text
Create a meeting copilot for tomorrow's discovery call with Company X.
```

```text
Update the meeting copilot with this transcript chunk.
```

```text
Close the session and create a sanitized summary I can share publicly.
```

## Privacy

This skill is built for private workspaces. Raw transcripts, personal names, private links, CRM data, and internal paths must stay out of public exports unless the user explicitly asks for a sanitized release.

## See Also

- [SKILL.md](SKILL.md) — full skill definition
