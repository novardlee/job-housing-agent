# Job & Housing Agent

One personal assistant workflow for finding suitable jobs, preparing accurate applications and interviews, tracking employer replies, and finding housing that fits the resulting income and commute.

It finds jobs that fit your real experience, helps write an honest resume for each one, catches interview invitations, prepares you fully, and compares housing near the job. Start with the [five-minute quick start](docs/QUICKSTART.md).

You need an AI assistant with private file access; email, browser, and scheduling access are optional. No host or live integration is certified by this public package yet.

This project grew out of a working personal workflow developed by its owner with an AI assistant. The owner reports it has worked so far. Existing local materials include job and apartment workbooks, daily queues, a job launcher, tailored resumes, interview preparation, correction records, and dated operational scripts.

**This public edition consolidates the workflow and instructions.** It includes one canonical agent prompt, categorized corrections, setup templates, output contracts, and evaluation cases. It excludes the owner's private records and dated scripts containing personal facts. It is an agent instruction package for a tool-enabled host, not a standalone application or universal auto-apply bot.

## What it does

- Searches field-relevant jobs, experience-building jobs, and genuine recruiter leads.
- Separates pay ranking from pay filtering and flags uncertain compensation.
- Tailors a truthful resume for each role and prepares a durable application queue.
- Helps stage supported applications for the user's final review and submission.
- Includes an explicit [invitation watcher](docs/INVITATION_FUNCTION.md) covering email, Indeed messages, and ZipRecruiter messages.
- Distinguishes new interview invitations from replies on existing employer threads.
- Prepares full interview scripts and travel plans without inventing personal facts.
- Matches housing to job corridors, income, transport, and housing deadlines.
- Retains corrections so later runs do not repeat earlier assistant mistakes.
- Includes [career evaluation](docs/CAREER_EVALUATION.md) and an [Indeed/ZipRecruiter profile builder](docs/PROFILE_BUILDER.md).

No job offer, rental approval, or funding outcome is guaranteed. Source records show recurring gaps as well as useful outputs; see [Evidence](docs/EVIDENCE.md).

## Recorded personal case study

The owner's saved records from June–September 2026 show **15 distinct role-specific interview opportunities and two offer outcomes** under a conservative definition. A broader total of 18 records includes two additional platform intro-call invitations and one related-role discussion; it is not an interview count. Opportunities include recruiter screens; **these are not attendance counts**.

See [results and counting method](docs/RESULTS.md) and the [aggregate record](examples/results.aggregate.json). The detailed ledger stays private. This review checked local logs, not live employer messages or original letters. The user participated throughout; agent-only causation and outcomes for other users have not been established.

## Install as a skill

A ready-to-install, reviewed skill version of this workflow (`SKILL.md` plus reference files and templates) is available as a paid download. The skill starts with a conversational intake, defaults to draft-only permissions, and never submits applications or messages employers on its own.

- **GitHub Sponsors:** [$25 one-time tier](https://github.com/sponsors/novardlee). You get an invite to the private skill repository within 24 hours.
- **Agensi marketplace:** [$39.99 on Agensi](https://www.agensi.io/skills/job-housing-agent-honest-job-search-interview-prep), installs through the Agensi agent connection.

Everything in this repository stays free for non-commercial use under CC BY-NC 4.0. You can also load `agent/SYSTEM_PROMPT.md` and `docs/` by hand.

## See the workflow

[Follow the fictional demonstration](docs/DEMO.md): a job queue, truthful resume guidance, an interview invitation, full preparation, and a housing comparison. It works as a draft exercise without inbox credentials. It is an example of intended outputs, not a live integration test.

[Paid setup and customization](docs/SETUP_OFFER.md) is the proposed first service. Pricing and booking are not active yet. Keep personal information out of public issues.

## Start here

1. Follow the [quick start](docs/QUICKSTART.md); the assistant can ask questions and build your profile.
2. Confirm your draft facts and preferences in private storage. The example JSON files show format; you do not need to fill them manually.
3. Load [the canonical prompt](agent/SYSTEM_PROMPT.md) in your chosen tool-enabled assistant and give it authorized access to the configured workspace.
4. Run `job_scan` in draft mode. Review its sources, exclusions, tailored documents, and queue.
5. Connect email, browser, file-generation, or scheduling capabilities only as needed. Confirm each permission separately in your host. Local task files are not active schedules.

There is no `pip install`, server start command, or bundled scheduler. Existing personal scripts are not portable releases. The setup guide explains what the host must supply.

## Repository structure

```text
job-housing-agent/
  README.md
  AGENTS.md
  CHANGELOG.md
  CONTRIBUTING.md
  SECURITY.md
  .gitignore
  LICENSE
  agent/SYSTEM_PROMPT.md
  config/profile.example.json
  config/policy.example.json
  docs/AGENT_SPEC.md
  docs/CORRECTIONS.md
  docs/EVIDENCE.md
  docs/SETUP.md
  docs/QUICKSTART.md
  docs/OUTPUT_CONTRACTS.md
  docs/INVITATION_FUNCTION.md
  docs/FUNDING.md
  docs/DEMO.md
  docs/SETUP_OFFER.md
  docs/PUBLICATION_PLAN.md
  docs/RESULTS.md
  docs/CAREER_EVALUATION.md
  docs/PROFILE_BUILDER.md
  templates/CHANGE_LOG.md
  templates/DECISION_LOG.md
  templates/INTERVIEW_EMAIL.txt
  examples/job.synthetic.json
  examples/results.aggregate.json
  tests/ACCEPTANCE.md
  .github/ISSUE_TEMPLATE/correction.md
  .github/pull_request_template.md
```

Recommended private workspace: `private/profile.json`, `private/policy.json`, `private/state/`, `private/artifacts/`, `private/logs/`. Keep that workspace out of the public repository.

## Sharing and supporting the project

You can support the project through [GitHub Sponsors](https://github.com/sponsors/novardlee). [Funding brief](docs/FUNDING.md) gives an honest project description and proposed next milestones.

## License

Copyright © 2026 Novard Lee. Licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE). You may use, share, and adapt this material for non-commercial purposes with credit. Commercial use, including selling setup or hosted services built on it, needs the owner's written permission; ask by email at novardlee@gmail.com or through the owner's [GitHub profile](https://github.com/novardlee).
