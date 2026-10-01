# Setup for a tool-enabled assistant

This is a prompt and workflow package. Bring your own authorized assistant host. The original project used file access, document/workbook generation, browser sessions, email/cloud integrations, memory, and scheduling. This edition does not provision those services or assume they exist in another host.

## 1. Create a private workspace

For a guided first run, start with [QUICKSTART.md](QUICKSTART.md). The `profile_build` function asks plain questions and writes draft configuration for user confirmation; manual JSON editing is optional.

Copy example profile/policy files into private configuration outside the public repository, or under ignored `private/`. Fill all material unknowns from the user and verified records. Store credentials in the host's supported credential system, not profile files or prompts.

Create private change log, decision log, job records, interview roster, reply-event state, apartment records, and artifacts directory. Blank state is appropriate for a new user; an existing user's unreadable or missing state must be reconciled before suppressing or duplicating events.

## 2. Load one canonical prompt

Use `agent/SYSTEM_PROMPT.md` as the agent's core instruction file. Make the current profile, approved policy, corrections, and private logs available at the start of each run. Host-specific setup should reference this prompt rather than duplicate a stale profile into each mode.

Keep the complete package accessible, including mode contracts and example configuration. If only the prompt is available, limit work to intake and drafts from supplied facts until the required documents can be read. Never claim to have loaded an inaccessible document. Permission flags describe approved scope; they do not grant host access or override the user's final application-submission boundary. `profile_updates` and `resume_uploads` are separate scopes and default to false.

Map available tools to read/write files, research/browse listings, access authorized inbox channels, create documents, and optionally deliver user notifications. Tools from the original environment may have different names or be absent. Check supported current interfaces when implementing adapters; do not copy old UI automation recipes blindly.

## 3. Run a draft demonstration

Use `examples/job.synthetic.json` and user-provided profile evidence. Produce a candidate record, truthful tailored-copy draft, queue, and report. All external-write and notification permissions are disabled in the example policy. A configured user may authorize bounded staging or notifications later.

## 4. Enable individual functions

Research first; document creation second; invitation and reply reads third; user delivery and remote copy only with authority. Enable application preparation only for a workflow with a tested final-review boundary. No-review/one-click routes remain manual. Verify resume selection and every required personal answer before review.

Invitation watching is a distinct function: follow `INVITATION_FUNCTION.md` and include email and job-board message coverage. Reply watching handles live-thread replies. Both share event IDs for deduplication; neither sends employer replies by default.

Career evaluation follows `CAREER_EVALUATION.md`; profile drafting follows `PROFILE_BUILDER.md`. Start with drafts and source mappings. Platform profile updates/uploads remain separate authorized actions with read-back checks.

## 5. Schedule only when requested

Local instructions do not activate automations. Configure cadence, timezone, scope, stop conditions, permissions, and duplicate prevention in the host. Confirm actual trigger state and execution results. Do not reuse expired one-time follow-ups or assume original task times are current.

## Known decisions before public launch

Supported assistant hosts, public demonstration, maintained adapter strategy, contribution terms, and funding destination. The package contains no fabricated install command or guarantee of automated cross-platform application submission.
