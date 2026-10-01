# Output and state contracts

These recommended portable contracts generalize the existing personal workflow. They are not claims of a currently implemented database/API. Use private storage for operational records.

## Run

`run_id`, mode/function, started/ended timestamps with timezone, profile/policy revision, coverage by source, artifact manifest, durable-save status, delivery status, checks performed, failures, next action. Separate completed artifacts from completed notification. Distinguish `prepared`, `attempted`, `confirmed`, `uncertain`, `failed`, and `not_authorized` delivery.

## Job

Stable source/job ID, normalized company+role key, original company/title, track, posted date, location/commute cluster, source/link, compensation range/unit/currency/provenance, base/total distinction, tier, filter result with reason, evidence of fit, constraints, warning flags, application status with evidence, tailored artifact revision.

Do not globally drop a known target merely because its row already exists. Keep `on_shortlist`, `started`, `ready_for_review`, `submitted_user_reported`, `submitted_receipt_verified`, `unknown_outcome`, and `closed` distinct. Normalize carefully; token overlap is a duplicate candidate, not conclusive identity.

## Invitation and interview

Interview record ID; company/role key; source channel/message IDs; invitation classification; received time; proposed interaction date/time/timezone; confirmation status; interviewer; format; venue/link; response deadline; history; preparation revision; conflict/travel checks; user notification status. Unknown dates are allowed. Re-engagement updates the record and preserves history.

## Reply

Thread ID, inbound provider message ID, timestamp, live/dead status, classification, previously notified event IDs, notification intent/receipt, and read/persistence outcome. Never invent IDs or suppress an event solely to make state look current. First-run baseline policy must be explicit.

## Housing

Source listing ID, address or masked anchor, listing URL/date, rent and base/net distinction, unit type, fees/utilities, verification time/status, stated qualification rules, estimated commute cost and basis, job-corridor fit, income scenario, uncertainty, resurfacing count, and exclusion reason when applicable. Keep unverified masked leads out of confirmed groups.

## Artifact manifest

Artifact type, role/interview ID, private path, source-profile revision, generation time, final-text check, visual check, hash where available, delivery/copy status, superseded-by/retirement marker. A source-file edit does not automatically update PDFs, uploaded profiles, or remote copies.

## Profile builder

Platform, profile revision, source evidence per field, drafted copy, current-versus-proposed discrepancies, default-resume filename/revision, approved scope, edit attempt, saved-state verification, unsupported fields, and remaining user steps. Keep private identifiers out of public reports.

## Career evaluation

Evaluation ID/date, profile/policy revision, role/offer IDs, direct/adjacent/stretch evidence, actual requirement gaps, career relevance, verified/unknown growth path, posted-versus-offer compensation, commute/housing scenario, observed-response data limits, recommendation, and user decision.

## Change and decision logs

Append ID, author/timezone, scope, user correction or proposal, source evidence, affected files, ownership, actual checks/results, status, and next action. Requested ownership is not accepted ownership. Historical entries remain historical even when later corrections resolve them.
