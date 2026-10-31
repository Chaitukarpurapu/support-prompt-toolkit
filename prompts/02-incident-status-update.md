# 02 - Incident Status Update Prompt

## Task
Create a factual status update for an active IT incident.

## Sample Input
Incident: INC-208
Service: Staff Portal
Severity: SEV2
Start: 11:20
Issue: Dashboard pages load slowly.
Impact: About 35 internal users.
Action: Support is checking server load.
Status: Investigating
Next update: 12:15

## Prompt v1
Write an incident status update using this information.
Incident details: [Paste incident information]

## Output v1
The Staff Portal has a serious performance issue. The team is working hard to fix it, and we expect the service to return to normal soon. Thank you for your patience.

## What Went Wrong
The response promises a recovery soon without evidence.
It misses the incident ID, start time, impact, and next update.

## Prompt v2 (Final)
**Role:** Act as a production incident communications analyst.
**Context:** Share a progress update during an active incident.
**Instructions:** Use verified input only. Keep a calm, neutral tone and each value under 20 words. Do not speculate about cause or recovery time. Use “Not confirmed” when a fact is missing.
**Required output format:** Markdown table with columns Field and Details; include exactly these rows: Incident, Service, Severity, Started, Impact, Current Action, Status, Next Update.
**Few-shot examples:** Input: INC-100, API, SEV3, 08:00, delayed requests, monitoring, recovered, 09:00. Output: Incident=INC-100; Service=API; Severity=SEV3; Started=08:00; Impact=delayed requests; Current Action=monitoring; Status=recovered; Next Update=09:00.
Input: INC-101, Portal, SEV2, 10:00, login errors, logs under review, investigating, no update time. Output: Incident=INC-101; Service=Portal; Severity=SEV2; Started=10:00; Impact=login errors; Current Action=logs under review; Status=investigating; Next Update=Not confirmed.
**Incident details:** [Paste incident information]

## Output v2
| Field | Details |
|---|---|
| Incident | INC-208 |
| Service | Staff Portal |
| Severity | SEV2 |
| Started | 11:20 |
| Impact | About 35 internal users report slow dashboard pages. |
| Current Action | Support is checking server load. |
| Status | Investigating |
| Next Update | 12:15 |

## Tips
- A fixed table keeps updates consistent across incidents.
- A rule against speculation prevents unsupported recovery promises.

