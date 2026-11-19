# AGENTS.md — microsoft-copilot-archive-bot-builder

> Read this file first. It is the agent-facing entry point for this repo.
> The canonical name for what this repo builds is **Archive Agent**.
> Do not use "Archive Bot", "Copilot agent", or "SharePoint agent" for it —
> the README used those interchangeably; this repo now uses one name.

## What this repo is

A reusable Microsoft 365 Copilot + SharePoint playbook for turning one
approved SharePoint archive folder into a narrowly scoped, read-only
knowledge-retrieval agent. The agent finds, recalls, compares, and cites
existing records. It does not create facts, approve decisions, write back
to any system, or grant permissions.

## Read order

1. `README.md` — the full playbook (six-step method, evidence hierarchy,
   pilot matrix, three access layers, governance).
2. `agent-instructions.md` — the paste-ready instructions for the
   SharePoint Agent Builder "Agent instructions" field. Use it verbatim
   after replacing `[APPROVED_ARCHIVE_PATH]`.
3. `examples/fictional-archive-example.md` — one complete, filled-in
   example with fictional values. Use it to ground placeholders.
4. `templates/` — the owner record and pilot test log to actually fill in.

## Before you build anything, ask the user for these three things

1. **Archive URL** — the exact approved SharePoint site / library / folder.
2. **Audience** — the named internal audience or approved security group.
3. **Owner** — the archive owner and a backup, as roles (not just names).

If any of the three is missing, ask for it. Do not guess a folder, a
group, or an owner.

## What to produce

- Agent name: `[Team or Project] | Archive Agent`
- Purpose, welcome text, and three starter prompts from
  `examples/fictional-archive-example.md`, with the fictional values
  replaced by the user's real ones.
- Agent instructions: `agent-instructions.md` verbatim, with only
  `[APPROVED_ARCHIVE_PATH]` replaced by the exact folder path.
- A completed `templates/owner-record.md` and a pilot run logged in
  `templates/pilot-test-log.csv` (README §6: at least five known-answer
  questions, two missing-answer questions, one conflicting-record
  scenario if available).

## Hard rules — never break these

- Never invent dates, owners, approvals, budgets, vendors, document
  titles, links, or quotations. If the archive does not support a claim,
  say so: "No supported answer found in the configured archive sources
  for this query."
- Use only the approved SharePoint folder as factual evidence. No public
  internet, general AI knowledge, other SharePoint locations, OneDrive,
  Teams chats, or email as evidence.
- Source prioritization is a behavioral control, not a security boundary.
  Say that plainly; do not promise technical isolation.
- Sharing the agent does not grant access to its source documents, and
  removing agent access does not revoke direct access to source files.
  Check the three access layers in README §7 separately.
- Do not publish or broadly share until the pilot gates in README §6
  are met and logged.
- Do not store confidential source documents or secrets in this repo.
