<p align="center">
<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# SOC L1 Alert Reporting
|  Room Name | SOC L1 Alert Reporting |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [SOC L1 Alert Reporting](https://tryhackme.com/room/socl1alertreporting) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: - 
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn how to properly report, escalate, and communicate about high-risk SOC alerts.
```
## Task 1
### I am ready to start!

- Answer: `No answer needed`

## Task 2
### What is the process of passing suspicious alerts to an L2 analyst for review?

- Answer: `Alert Escalation`

### What is the process of formally describing alert details and findings?

- Answer: `Alert Reporting`

## Task 3
### According to the SOC dashboard (opens in new tab), which user email leaked the sensitive document?

- If we look through the alerts, we can find one where this person attempts to share sensitive information outside the company by reading the alert information. We can then see the email of the user

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/e482ac76-609e-4294-a421-3f96d867346c" />
</p>

- Answer: `m.boslan@tryhackme.thm`

### Looking at the new alerts, who is the "sender" of the suspicious, likely phishing email?

- This is another alert and we can see the sender is someone we normally discard as not malicious

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/56db7060-a666-43f1-81a0-9967ba012476" />
</p>

- Answer: `support@microsoft.com`

### Open the phishing alert, read its details, and try to understand the activity. Using the Five Ws template, what flag did you receive after writing a good report? Note: Assign yourself, move the alert to In Progress, and fill in the Analyst Comment.

- I assigned myself to the alert and changed the `Status` to `In Progress`
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/e6469909-0c5e-4c53-9cd1-e6ebbfe6d5d5" />
</p>

- Now, it seems like this is a fake email that seems like it comes from Microsoft but actually doesn't. We can note that this fails both SPF and DKIM which means this was not sent from an authorized server for the domain `microsoft.com`, that the email did not actually come from `microsoft.com` and that is may have been possibly modified during transit. Furthermore, considering the urgency in the email strongly suggests this is a phishing email such as `urgent notice` or `download the email` as well as having a suspicious `.rar` attachment. We can write all of this information into a report

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/e9df6429-4c19-447d-aa33-dc19e605b72c" />
</p>

- After submitting, we get the flag

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/48246d6b-33a2-485f-a7a0-c79d77c78910" />
</p>

- Also, I remembered the close the ticket and mark it as a `True Positive`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/f429e2a9-ba3a-4e10-9132-201c41bfd62c" />
</p>

- Answer: `THM{nice_attempt_faking_microsoft_support`

## Task 4
