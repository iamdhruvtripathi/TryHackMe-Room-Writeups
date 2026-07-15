<p align="center">
<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# SOC L1 Alert Triage
|  Room Name | SOC L1 Alert Triage |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [SOC L1 Alert Triage](https://tryhackme.com/room/socl1alerttriage) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: - 
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn more about SOC alerts and build a systematic approach to efficiently triaging them.
```
## Task 1
### I am ready to start!

- Answer: `No answer needed`

## Task 2
### What is the number of alerts you see in the SOC dashboard (opens in new tab)?

- We can see that there are 5 alerts

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/3007f106-6129-4c38-ba2e-a96fcbdea4d4" />
</p>

- Answer: `5`

### What is the name of the most recent alert you see?

- Sorting by most recent gives us the answer

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/d6aeac41-2070-4c4b-a012-caa97cc1b464" />
</p>

- Answer: `Double-Extension File Creation`

## Task 3

### What was the verdict for the "Unusual VPN Login Location" alert?

- We can see the verdict marked in red

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/a04608d1-dec2-43b7-901c-ddbae20d30fa" />
</p>

- Answer: `False Positive`

### What user was mentioned in the "Unusual VPN Login Location" alert?

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/c1d1e68d-b854-452f-aa55-3a347ef6bf92" />
</p>

- Answer: `M.Clark`

## Task 4
### Should you first prioritise medium over low severity alerts? (Yea/Nay)

- We should always prioritize more urgent alerts over less urgent ones

- Answer: `Yea`

### Should you first take the newest alerts and then the older ones? (Yea/Nay)

- The idea with this one that with the older alerts, the malicious actor has progressed further compared to a malicious actor that is just starting making the older one more urgent

- Answer: `Nay`

### Assign yourself to the first-priority alert and change its status to In Progress. The name of your selected alert will be the answer to the question.

- I picked the most critical alert which was `Potential Data Exfiltration`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/59d96cb5-f3ed-4146-909e-265ac8edc283" />
</p>

- Answer: `Potential Data Exfiltration`
