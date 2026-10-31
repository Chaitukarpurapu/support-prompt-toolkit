# Support Prompt Toolkit

Support Prompt Toolkit is a small library of reusable AI prompts for application support, website operations, and IT service teams. It shows how prompt design can help support engineers, production support analysts, and IT professionals prepare clearer ticket summaries, incident updates, customer replies, root cause notes, and daily reports. Each prompt includes a basic first attempt, an example of its weakness, and a refined version.

## Prompt Library

| Prompt name | Task | Best use case |
|---|---|---|
| [Ticket Summary](prompts/01-ticket-summary.md) | Summarize support tickets | Jira reviews and shift handovers |
| [Incident Status Update](prompts/02-incident-status-update.md) | Share incident progress | Active production incidents |
| [Customer Reply](prompts/03-customer-reply.md) | Draft a support email | Customer communication |
| [Root Cause Notes](prompts/04-root-cause-notes.md) | Structure investigation findings | Incident review records |
| [Daily Status Report](prompts/05-daily-status-report.md) | Summarize support work | Team updates and handovers |

## How to Use

1. Open a prompt file and review its sample input, v1, and refined v2.
2. Copy Prompt v2 into an AI assistant and replace the sample with approved support details.
3. Check every fact in the result and edit it before using it in a ticket, email, or report.

## What I Learned

- Define the role and task so the assistant knows what kind of work to do.
- Set a clear tone, length, and output format to make results easier to review.
- Compare outputs, find a specific weakness, and refine the prompt without adding unsupported facts.

## Prompt Refinement Method

Define the task → Write v1 → Review the output → Identify a weakness → Improve v2 → Compare results.

The v1 and v2 outputs are illustrative examples, not results from a controlled model evaluation. Human review is required before using AI-assisted support content.

## Data Safety

All applications, tickets, incidents, people, and messages in these examples are fictional and generic. No real customer data, company names, internal URLs, credentials, or confidential details are used.

