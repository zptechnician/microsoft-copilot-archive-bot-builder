# README start-here snippet — add at the top of README.md

Insert the block below directly under the title
(`# Archive Agent Builder How-To`), before `## 1. Executive Summary`.
It does not change any existing README content.

```markdown
## Start here — give this repo to an agent

Copy and paste this prompt to any agent / LLM, with this repo attached:

> Read AGENTS.md in this repo first, then README.md.
> Build me a Microsoft 365 Copilot Archive Agent over my approved
> SharePoint archive. Ask me for the three things you need before you
> start: (1) the exact approved SharePoint folder URL, (2) the intended
> audience / security group, and (3) the archive owner and backup.
> Then produce: the agent name, purpose, welcome text, and three starter
> prompts (follow examples/fictional-archive-example.md, with my real
> values instead of the fictional ones); the agent instructions from
> agent-instructions.md verbatim, with only [APPROVED_ARCHIVE_PATH]
> replaced; a completed templates/owner-record.md; and a pilot test plan
> in templates/pilot-test-log.csv following README §6.
> Never invent dates, owners, approvals, budgets, document titles, links,
> or quotations. If the archive does not support a claim, say so.
> Do not publish or share the agent until the pilot gates in README §6
> are met.
```
