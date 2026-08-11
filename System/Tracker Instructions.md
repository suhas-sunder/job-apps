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
- Do not infer a rejection merely because there has been no response.
- Do not infer an application was submitted from a job alert or saved-job email.
- If evidence is ambiguous, record it in Notes and leave the existing status unchanged.

## Email-derived updates

When email access is available:

- Treat application confirmations, recruiter correspondence, interview invitations, assessments, offers, rejection notices, and explicit closure messages as evidence.
- Prefer explicit statements in the email over inference.
- Match incoming messages to an existing application before creating a new record.
- Record dates from the actual message or event, not merely the date the tracker is being updated.
- Avoid storing unnecessary personal or confidential email content. Summarize only what is useful to the job search.

## Dashboard

After changing application records:

- Recalculate status counts from the application notes.
- Keep `Active Applications` focused on applications that still require monitoring or action.
- Keep `Follow-Ups / Action Items` specific and actionable.
- Update the `Last reviewed` date when the dashboard has been reconciled against the application records.

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
