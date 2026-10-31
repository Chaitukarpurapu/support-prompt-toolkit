# 03 - Customer Reply Prompt

## Task
Draft a polite customer email using verified ticket information.

## Sample Input
Customer: Customer A
Ticket: SUP-330
Issue: Unable to download a monthly report.
Status: Support reproduced the issue; investigation is ongoing.
Workaround: None confirmed.
Next update: Tomorrow by 15:00.

## Prompt v1
Write an email to the customer about their issue.
Ticket details: [Paste customer ticket details]

## Output v1
Subject: Your Problem

Hi Customer A,

We know you cannot download the report. Our technical team is working hard to fix everything as quickly as possible. Please try again later; it should hopefully be resolved soon.

Thanks,
Support

## What Went Wrong
The reply implies a fix is expected without evidence.
It omits the ticket reference and next update time.

## Prompt v2 (Final)
**Role:** Act as a customer support communication specialist.
**Context:** Write a reply about an open application support ticket.
**Instructions:** Use verified facts only. Be empathetic and professional. Keep the body under 90 words. Do not promise a fix or invent a workaround. Include the ticket ID and next update when supplied; otherwise say an update will follow when available.
**Required output format:** Subject: [Ticket ID] - [Brief issue], then greeting, acknowledgment and progress, next update or action, and sign-off from Application Support Team.
**Few-shot examples:** Input: Sam, SUP-10, password reset fails, investigating, update 16:00. Output: Subject: SUP-10 - Password Reset Issue. Hi Sam, We are investigating the password reset issue and will provide an update by 16:00. Regards, Application Support Team.
Input: Mia, SUP-11, page not loading, resolved. Output: Subject: SUP-11 - Page Loading Issue. Hi Mia, The page loading issue is resolved. Please let us know if it continues. Regards, Application Support Team.
**Customer details:** [Paste ticket information]

## Output v2
Subject: SUP-330 - Monthly Report Download Issue

Hi Customer A,

Thank you for reporting the monthly report download issue. Our support team reproduced it and is investigating. There is no confirmed workaround at this stage.

We will provide the next update by 15:00 tomorrow.

Regards,
Application Support Team

## Tips
- Tone and length limits help keep customer replies clear and considerate.
- Fact-only instructions prevent unsupported fixes or promises.

