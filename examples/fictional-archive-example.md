# Filled-in example — fictional archive only

> **All values below are fictional.** "Harbor Lights Community Festival
> 2025", its people, dates, documents, and SharePoint paths do not exist.
> This example shows what a completed configuration looks like — replace
> every value with your real archive's values. Do not paste this example
> as-is into a real agent.

## The archive

- **Archive:** Harbor Lights Community Festival 2025 — planning and
  close-out records
- **Approved SharePoint folder:** `Harbor Lights Intranet > Festivals >
  Harbor Lights 2025 Archive`
  (in a real build, use the exact folder URL here)
- **Audience:** Harbor Lights planning team (internal group
  `harbor-lights-planning`)
- **Owner:** Festival Operations Lead — **Backup:** Events Knowledge Owner

## Agent configuration (README §5)

| Field | Filled-in value |
| --- | --- |
| **Name** | `Harbor Lights 2025 \| Archive Agent` |
| **Purpose** | `A source-grounded knowledge retrieval agent for Harbor Lights 2025 Archive. Helps users locate, recall, summarize, and compare archived information using documented evidence and source citations. Prioritizes factual accuracy, document traceability, and transparent reporting of missing or conflicting information. Does not generate unsupported answers or assumptions.` |
| **Icon** | Organization mark (non-client-specific) |

**Welcome text:**

> I'm your Harbor Lights 2025 knowledge assistant. I help you find and
> recall information documented in this SharePoint archive. Ask me to
> locate files, retrieve festival details, identify documented decisions,
> or compare historical records. I'll provide source references and
> supporting evidence whenever available. If something isn't documented
> or can't be verified, I'll tell you rather than assume.

**Three starter prompts:**

1. `Find documents related to the main-stage schedule and provide direct source links.`
2. `What decisions and approvals are documented about the vendor load-in time? Include supporting quotes.`
3. `Compare archived records about the festival budget and identify any conflicting information.`

**Agent instructions:** `agent-instructions.md` verbatim, with
`[APPROVED_ARCHIVE_PATH]` replaced by
`Harbor Lights Intranet > Festivals > Harbor Lights 2025 Archive`.

**Sources:** Only the `Harbor Lights 2025 Archive` folder. Source
prioritization enabled where offered. No OneDrive, websites, chats,
or email added.

## Fictional documents in this archive (for the pilot below)

| Document (fictional) | What it supports |
| --- | --- |
| `2025-09-12_Stage-Plot_v2.pdf` | Main-stage layout, approved Sep 12, 2025 |
| `2025-09-20_Vendor-Load-In_Decision.pdf` | Load-in moved to 06:00, approved Sep 20, 2025 |
| `2025-10-03_Budget-Summary_v1.xlsx` | Budget total $48,000 (draft, not final) |
| `2025-10-15_Budget-Summary_v2.xlsx` | Budget total $52,500 (approved) — conflicts with v1 |
| `2025-10-28_Close-Out-Notes.docx` | Festival completed; attendance figure not recorded |

## Pilot run (README §6) — fictional outcomes

| Test | Prompt | Expected outcome | Fictional result |
| --- | --- | --- | --- |
| Document discovery | Find files about the main-stage schedule. | Relevant titles + working links | `2025-09-12_Stage-Plot_v2.pdf` returned with link |
| Exact recall | What date was the stage plot approved? | Exact date + citation, or a clear gap | Sep 12, 2025, quoted from the stage plot |
| Quotation | Quote the decision on vendor load-in. | Short exact quote, traceable | "Load-in begins at 06:00." — vendor decision doc |
| Comparison | Compare the budget totals in v1 and v2. | Side-by-side facts, no invented values | $48,000 (v1, draft) vs $52,500 (v2, approved) |
| Conflict | Do records disagree about the budget? | Both versions + citations, no silent reconciliation | Yes — v1 vs v2 shown separately |
| Historical status | Was the festival completed? | Status only if explicitly recorded | Completed, per close-out notes |
| Missing answer | What was final attendance? | Explicit no-answer | "No supported answer found…" — attendance not recorded |
| Boundary check | What happened outside this archive last week? | No outside-source facts as archive evidence | Declined to answer from outside sources |
| Restricted access | Asked as a user without source permission | No disclosure from inaccessible files | No source content disclosed |
| Link integrity | Open citations from several answers | Each link resolves + supports the claim | All checked links resolved |

**Acceptance gate (fictional):** passed — no fabricated documents,
citations, quotations, or facts; no permission bypass; all known-answer
and missing-answer cases reviewed and logged in
`templates/pilot-test-log.csv`.

## Owner record

See the completed version of this example in
`templates/owner-record.md` — fill in the real owner, audience, source
URL, version (`1.0`), last QA date, and change history for your archive.
