# 04 - Root Cause Notes Prompt

## Task
Turn technical incident notes into structured investigation documentation.

## Sample Input
Incident: INC-410
Issue: Order history page returned HTTP 500 errors.
Start and end: 14:05-14:28
Impact: 24 failed page requests.
Evidence: Logs showed connection pool exhaustion.
Action: Application service restarted.
Result: Page requests succeeded after restart.
Root cause: Not yet confirmed.

## Prompt v1
Explain the root cause of this incident.
Incident notes: [Paste incident notes]

## Output v1
The incident was caused by a database connection pool failure. Restarting the application permanently resolved the issue. The application is stable now, and the issue should not happen again.

## What Went Wrong
The response treats a log observation as a confirmed root cause.
It makes unsupported claims about permanent recovery and recurrence.

## Prompt v2 (Final)
**Role:** Act as a technical incident analysis specialist.
**Context:** Prepare concise notes for an incident review record.
**Instructions:** Use supplied facts only and separate evidence from conclusions. Do not confirm a cause unless the input confirms it. Return valid JSON only, using exactly the seven keys below. Use null for a missing or unconfirmed cause.
**Required output format:** {"incident_id":"","issue":"","duration":"","impact":"","evidence":"","action_taken":"","confirmed_root_cause":null}
**Few-shot examples:** Input: INC-1, timeout, 10:00-10:10, 5 errors, logs show delays, restarted, cause unconfirmed. Output: {"incident_id":"INC-1","issue":"Timeout","duration":"10:00-10:10","impact":"5 errors","evidence":"Logs show delays","action_taken":"Restarted","confirmed_root_cause":null}
Input: INC-2, API errors, 12:00-12:05, 8 requests failed, deployment logs confirm invalid config, config corrected, confirmed cause invalid config. Output: {"incident_id":"INC-2","issue":"API errors","duration":"12:00-12:05","impact":"8 failed requests","evidence":"Deployment logs confirm invalid config","action_taken":"Config corrected","confirmed_root_cause":"Invalid configuration"}
**Incident notes:** [Paste technical notes]

## Output v2
{
  "incident_id": "INC-410",
  "issue": "Order history page returned HTTP 500 errors",
  "duration": "14:05-14:28",
  "impact": "24 failed page requests",
  "evidence": "Logs showed connection pool exhaustion",
  "action_taken": "Application service restarted; requests succeeded afterward",
  "confirmed_root_cause": null
}

## Tips
- JSON gives incident notes a predictable structure.
- A null cause keeps evidence separate from an unconfirmed conclusion.

