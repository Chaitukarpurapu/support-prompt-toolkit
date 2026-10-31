# 05 - Daily Status Report Prompt

## Task
Convert daily support activity notes into a concise team handover report.

## Sample Input
Date: 15 October 2026
Closed: APP-501, WEB-502, APP-503.
Open: APP-504 login issue, investigation ongoing.
Monitoring: API and web dashboards checked; no alerts.
Change: Footer text updated in test.
Blocker: Waiting for approval before deployment.

## Prompt v1
Create a daily work report from these notes.
Activity notes: [Paste daily activity notes]

## Output v1
Today was productive. Several important tickets were completed successfully. We monitored the applications and made a website update. Some tasks need attention, but overall everything is under control.

## What Went Wrong
The report omits ticket IDs, the open issue, and pending approval.
It uses subjective claims instead of specific work details.

## Prompt v2 (Final)
**Role:** Act as an application support shift lead.
**Context:** Prepare a daily operations report for the next team.
**Instructions:** Use supplied notes only. Be factual and professional. Return exactly five numbered items, each one concise sentence. Include ticket counts and IDs, open work, changes, blockers, and next actions. Do not claim an unapproved deployment is complete.
**Required output format:** 1. Date; 2. Tickets Completed; 3. Open Issues; 4. Monitoring and Changes; 5. Blockers / Next Action.
**Few-shot examples:** Input: 01 Oct, closed T-1, open T-2, dashboard normal, no changes, awaiting logs. Output: 1. Date: 01 Oct. 2. Tickets Completed: 1 (T-1). 3. Open Issues: T-2. 4. Monitoring and Changes: Dashboard normal; no changes. 5. Blockers / Next Action: Awaiting logs.
Input: 02 Oct, closed T-3 and T-4, none open, API checked, test banner updated, no blockers. Output: 1. Date: 02 Oct. 2. Tickets Completed: 2 (T-3, T-4). 3. Open Issues: None reported. 4. Monitoring and Changes: API checked; test banner updated. 5. Blockers / Next Action: None reported.
**Daily activity notes:** [Paste work notes]

## Output v2
1. **Date:** 15 October 2026.
2. **Tickets Completed:** 3 tickets closed (APP-501, WEB-502, APP-503).
3. **Open Issues:** APP-504 login issue remains under investigation.
4. **Monitoring and Changes:** API and web dashboards checked with no alerts; footer text updated in test.
5. **Blockers / Next Action:** Awaiting approval before deploying the footer update.

## Tips
- Numbered sections make daily handovers easier to compare.
- Naming blockers and next actions helps the incoming team plan follow-up.

