# Invitation watcher — explicit agent function

This function comes from the existing `interview-invite-watcher` workflow. It is preserved as a first-class function within the consolidated agent, not folded into employer-reply monitoring or ordinary job sourcing.

## Responsibility

Detect new genuine interview invitations and re-engagement; classify and deduplicate them; capture the proposed interaction; route them to interview preparation and the user's notification workflow. An invitation can be a request for availability even before any date/time is fixed.

## Channels

1. Authorized email inbox.
2. Indeed on-platform messages.
3. ZipRecruiter on-platform messages.

Classify by content, not channel. Platform invitations can arrive in email from a platform sender; an empty platform message inbox does not mean no platform invitations. Distinguish a recruiter screen, hiring-manager intro queue, and full employer interview instead of treating them as equivalent outcomes.

Check every configured channel. Record `checked_with_results`, `checked_empty`, `blocked`, `not_connected`, or `not_authorized` per channel. Do not report a full all-clear when one is unavailable. Allow hydration/retry within bounded attempts before declaring a page empty. Preserve open unsent drafts by using a separate safe tab/session.

## Classification

| Input | Classification and owner |
|---|---|
| Person proposes phone/video/on-site conversation about a specific role | Genuine invitation; invitation watcher |
| Person asks availability for a role | Genuine invitation; invitation watcher |
| Known employer returns with a new interview request | Re-engagement; update existing interview record |
| Person invites the user to apply but proposes no interaction | Warm lead; job_scan |
| New human response within an active interview thread | Reply event; reply_watch; route to invitation function if a new/changed interview is proposed |
| Offer, rejection, position filled, postponement, or cancellation on a known role | Status event; update record and notify once under configured authority; offers carry response deadlines; rebuild prep only when changed facts require it |
| Algorithmic job blast, application receipt, marketing, out-of-office | Noise; no invitation |
| Suspicious proposal with scam indicators | Flagged review item; do not create normal interview prep or share personal data |

## Data and duplicate handling

Capture channel, provider event/message ID, company, role, sender, received timestamp, proposed date/time/timezone, format, venue/link, response deadline, confirmation status, and evidence reference. Unknown fields stay unknown.

Use stable source event IDs plus a company/role interview record. A new message that re-engages a known employer is not suppressed simply because a prep file exists. Update the record and preserve prior dates/history. Cross-channel copies of one invitation produce one logical event and notification; preserve all source references.

Use an overlapping look-back window. A message arriving just after a completed sweep must be caught next run and deduplicated, not assumed covered by the earlier check.

## Handoff

On a validated event, `interview_prepare` checks schedule conflicts, current canonical profile, posting facts, and travel constraints, then prepares full scripts and correct documents. A delivery step notifies the user under existing configured authority. Sender-facing RSVP, booking, reply, acceptance, or decline remains the user's action unless separately authorized.

Record preparation and notification status separately. If preparation cannot finish, preserve the invitation and make its response deadline visible; do not lose the event behind a document failure. If delivery cannot be confirmed, record prepared/pending or uncertain status rather than delivered.

A zero-new-invitation run may notify when an unactioned response deadline or same-day event becomes actionable. Do not repeat an identical alert on an unchanged re-sweep. Record the run and coverage even when no notification is warranted.

## Cadence

The original local task describes twice-daily invitation checks; another snapshot names 09:00 and 18:00. Those are historical written intent, not independently verified live triggers. The reusable package creates no schedule. Configure actual cadence in the chosen host with the user's authorization.

## Acceptance

Catch a genuine request visible only in Indeed Messages; distinguish an apply invitation; process a returning employer's new invitation once; preserve a draft composer; report a skipped browser channel; deduplicate cross-channel copies; do not click scheduling or submission links automatically.
