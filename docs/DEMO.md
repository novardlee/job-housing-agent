# A five-minute demonstration

This fictional walkthrough shows what the agent is designed to produce. It is a worked example, not an executed inbox scan, real application, or verified business result. It uses no credentials or paid services.

## 1. Give the agent a verified profile

Example candidate: Alex Example has inventory and receiving experience, including reconciling stock counts against records, spreadsheet skills, a logistics diploma, and no customs certification. Alex uses public transport and wants field-relevant work. The profile is fictional.

Example policy: field-relevant roles are ranked without a hard salary cutoff; experience-first roles need a posted top of at least $25/hour. Final applications remain Alex's decision. Notifications are drafts until authorized.

## 2. Run `job_scan`

| Fictional listing | Result | Reason |
|---|---|---|
| Inventory Coordinator, Example Distribution, $48,000–$58,000/year | Include in field-relevant queue | Matches verified inventory experience; no invented field-track floor |
| Receiving Associate, Example Warehouse, $22–$27/hour | Include in experience-first queue | Posted top clears the example floor; bottom is flagged |
| Stock Clerk, Example Supply, from $21/hour | Include as unknown ceiling if otherwise eligible | Minimum alone does not prove maximum is below the floor |

Sample queue entry:

> Inventory Coordinator · Example Distribution · Example transit corridor
>
> Fit: receiving, inventory reconciliation, spreadsheet records.
>
> Pay: synthetic $48,000–$58,000 annual range.
>
> Resume: tailor from Alex's verified inventory evidence; do not add a customs credential.
>
> Application: not started. Next action: user reviews tailored draft and actual posting.

## 3. Run the invitation function

Fictional Indeed message:

> “Hi Alex, we'd like a 20-minute call about the Inventory Coordinator role. Are you available Tuesday morning?”

Expected classification: **genuine interview invitation**. A request for availability counts even without a confirmed time.

- Channel: Indeed messages.
- Role record: Inventory Coordinator / Example Distribution.
- Time: proposed Tuesday morning; exact date, time, and timezone unresolved.
- Next action: prepare the interview and draft suggested availability for Alex's review.
- Employer response: not sent; no booking or submission.

Compare “You might like these jobs” → noise, and “Please apply for our role” → lead, not interview invitation. A later human reply in an active thread is handled by reply watch; a new proposed interview routes back to the invitation function.

## 4. Prepare the interview

Sample introduction based only on fictional facts:

> “My background is in receiving and inventory work. I keep stock records accurate, reconcile discrepancies, and use spreadsheets to support the operation. I'm interested in this role because it combines that practical experience with more responsibility for inventory coordination.”

The full output includes at-a-glance details, confirmed travel options, truthful fit mapping, likely questions and answers, questions to ask, closing, thank-you draft, and checklist. Unknown company facts and transport times stay unresolved until verified. The complete preparation belongs in the user-facing message body.

## 5. Connect the housing decision

Compare fictional homes along the relevant transit corridor. Record base rent, stated qualification rules, utilities, estimated travel cost, and verification status. A masked listing with a locatable anchor goes in its own unverified section. No income qualification or travel time is invented.

The output is a decision aid: housing should follow the real job location and approved budget, rather than a generic cheapest-rent list.

## What to show a prospective customer

Optional additional draft modes: ask `profile_build` for separate platform headlines/summaries from Alex's fictional facts, then `career_evaluate` to compare a direct inventory role with an adjacent purchasing role. Neither mode changes a real profile or guarantees a career outcome. See [career evaluation](CAREER_EVALUATION.md) and [profile builder](PROFILE_BUILDER.md).

The corrected profile → ranked queue → correct resume → invitation detection → complete preparation → job-linked housing comparison. Show how the agent handles unknowns and user review, not only the happy path.

To reproduce this demonstration in an assistant host, load `agent/SYSTEM_PROMPT.md`, provide the fictional facts above, keep all external actions disabled, and ask for each mode's drafts. Exact generated wording may vary. This package does not claim that external integrations have been tested by this demonstration.
