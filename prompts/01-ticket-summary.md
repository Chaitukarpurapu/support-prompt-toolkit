# 01 - Ticket Summary Prompt

## Task
Turn a detailed support ticket into a short, actionable summary.

## Sample Input
Ticket: APP-1042
Priority: P2
Issue: Users cannot submit the contact form.
Impact: 18 submissions failed between 09:10 and 09:40.
Action: Support restarted the form service at 09:45.
Status: Monitoring; new submissions are succeeding.

## Prompt v1
Summarize this support ticket in simple English.
Ticket details: [Paste ticket details]

## Output v1
There was a problem with the contact form, which caused trouble for some users. The support team restarted a service, and things seem better now. The team will keep checking the application.

## What Went Wrong
The summary omits the ticket ID, priority, exact impact, and timeline.
It is too vague to support a useful Jira handover.

## Prompt v2 (Final)
**Role:** Act as an application support analyst.
**Context:** Prepare a Jira handover summary from the supplied ticket notes.
**Instructions:** Use only supplied facts; do not guess. Be neutral and concise, with one short sentence per bullet. Return exactly five bullets. Write “Not provided” for missing details.
**Required output format:**
- Ticket:
- Priority:
- Impact:
- Action Taken:
- Current Status:
**Few-shot examples:** Input: WEB-101, P3, menu misaligned, CSS updated, resolved. Output: Ticket WEB-101; Priority P3; Impact menu misaligned; Action Taken CSS updated; Current Status resolved.
Input: APP-202, P2, login fails, investigation ongoing. Output: Ticket APP-202; Priority P2; Impact login fails; Action Taken Not provided; Current Status investigating.
**Ticket to summarize:** [Paste ticket details]

## Output v2
- **Ticket:** APP-1042
- **Priority:** P2
- **Impact:** 18 contact form submissions failed between 09:10 and 09:40.
- **Action Taken:** Form service restarted at 09:45.
- **Current Status:** Monitoring; new submissions are succeeding.

## Tips
- Fixed labels make important ticket details easy to scan.
- A missing-information rule reduces accidental guesses.

