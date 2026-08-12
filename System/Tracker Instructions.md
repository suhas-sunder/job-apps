# Tracker Instructions

This repository is the durable source of truth for Suhas's job applications.

## Required workflow before making changes

1. Read this file.
2. Read `System/Status Definitions.md`.
3. Read `System/Update Log.md` for recent history.
4. Check `Applications/` for an existing note before creating a new application.
5. Read `Dashboard.md` before updating counts or active pipeline rows.

## Application records

- One Markdown note per distinct job application.
- Use the structure in `Templates/Application.md`.
- Store notes under `Applications/`.
- File naming convention: `Company - Role.md`.
- If two applications have the same company and role, add location or application date to distinguish them.
- Do not create duplicates. Match by company, role, location, application/reference ID, and date when available.
- Preserve useful historical information even after an application closes.

## Status handling

- Use only canonical statuses from `System/Status Definitions.md` unless the taxonomy is deliberately revised.
- `status` in YAML is the current status.
- Record meaningful status changes in the application's Timeline section.
- Do not label an application `Rejected` merely because there has been no response. Use `Closed / No Response` under the aging rule instead.
- Do not infer an application was submitted from a job alert, saved-job email, candidate-account login/reset, or similar account activity alone.
- A direct user confirmation from an employer candidate portal, such as Workday showing the role as applied/submitted, is valid application evidence even if no confirmation email exists.
- If evidence is ambiguous, record it in Notes only when useful and leave the existing status unchanged.

### Aging rule for silent applications

- During tracker reconciliation, measure inactivity from the most recent confirmed employer/application-stage activity.
- If an application has had **30 calendar days with no employer activity**, move it to `Closed / No Response` unless there is concrete evidence that the process is still active.
- This is an operational tracking assumption, not evidence that the employer explicitly rejected the candidate.
- If later employer contact arrives, reopen the application and move it to the appropriate confirmed stage.

## Email-derived updates

When email access is available:

- Treat application confirmations, recruiter correspondence, interview invitations, assessments, offers, rejection notices, and explicit closure messages as evidence.
- Prefer explicit statements in the email over inference.
- Match incoming messages to an existing application before creating a new record.
- Record dates from the actual message or event, not merely the date the tracker is being updated.
- Avoid storing unnecessary personal or confidential email content. Summarize only what is useful to the job search.
- Ignore job-alert/newsletter messages unless they contain explicit evidence that Suhas actually submitted an application.
- When a review window is specified, do not import applications or status history from before that window unless later in-window correspondence is necessary to represent the current status of an application.

## Dashboard

After changing application records:

- Recalculate status counts from the application notes.
- Keep `Active Applications` focused on applications that still require monitoring or action.
- Keep terminal outcomes in a separate section when useful for quick scanning.
- Keep `Follow-Ups / Action Items` specific and actionable.
- Update the `Last reviewed` date when the dashboard has been reconciled against the application records.

### Pipeline visualization

Every requested tracker reconciliation should also regenerate the `Pipeline Flow` Mermaid diagram in `Dashboard.md`.

- Use a left-to-right Mermaid flowchart so it renders directly in Obsidian without requiring a community plugin.
- Derive counts from the application notes and their confirmed timelines, never from memory alone.
- Show only evidence-backed applications.
- Prefer meaningful stage transitions when enough history exists, for example `Applied -> Recruiter Screen -> Interview -> Offer` with rejection/withdrawal branches.
- If earlier transition history is not known, use `Confirmed Applications` as the root and branch to the current confirmed statuses rather than inventing intermediate steps.
- Label edges or nodes with counts so the chart remains useful at a glance.
- Reconcile the diagram with the numerical status table before committing changes; they must agree.
- Keep the diagram compact as the tracker grows. Do not display zero-count branches unless they materially improve readability.

## Update log

Add an entry to `System/Update Log.md` for material changes, including:

- new applications
- status changes
- interviews or assessments scheduled
- offers or rejections
- withdrawals or closures
- substantial corrections or deduplication
- changes to tracker structure or rules

Routine typo fixes do not need an entry.

## Safety and scope

- This repo is for job-search tracking.
- Do not modify unrelated repositories as part of this workflow.
- Do not send emails, withdraw applications, accept offers, schedule interviews, or otherwise act externally unless Suhas explicitly asks for that specific action.
- When uncertain, preserve existing data rather than overwriting it with a guess.
