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

- We can see the select alert name and that I assigned myself to it

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/3bb84106-3e98-4997-a999-cc8432c145f5" />
</p>

- Answer: `Potential Data Exfiltration`

## Task 5
### Which flag did you receive after you correctly triaged the first-priority alert?

- First, we sort by severity and try to resolve the highest priority ticket as seen below. First, I had to assign myself the alert and change the `Status` to `In Progress`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/5571895c-42c8-4643-8e94-e2be9ba365dd" />
</p>

- Now, my thought process is that this is most likely a false positive even though it is flagged as a `Potential Data Exfiltration` because I do not see any suspicious IP addresses (`Source IP`), networks (`Source Network`), or domains (`Destination`). To me, this seems like a normal data transfer, although it is gigabytes of data, is not malicious. We can set the `Verdict` and `Status` accordingly as well as leave a `Comment` and we can see we earn the flag below

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/f6cb9f37-4c9f-42bb-a3c7-fdf29448cddd" />
</p>

- Answer: `THM{how_could_this_user_fall_for_it?}`

### Which flag did you receive after you correctly triaged the second-priority alert?

- I did the same thing and assigned myself and set the `Status` to `In Progress`. This one was a bit more obvious. We can see that the file is `cat2025.mp4.exe` which is clearly an executable trying to masquerade as a normal `.mp4` file and so I know this is a `True Positive` and we can set the values as we did for the last alert

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/32fb493f-e8f0-4d2a-9016-a6da03566a51" />
</p>

- We entered the correct values and I got the flag

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/d17669d3-d476-4a6f-a763-47a3f21f375e" />
</p>

### Which flag did you receive after you correctly triaged the third-priority alert?

- The last alert states this was a `Download from Github Repository`. If we look at the `Accessed URL` and `Source Network`, those do not seem like being matched to any known malicious URLs or the network being associated with any known malicious activity. Therefore, this is a `False Positive`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/f965e2f8-2230-4dbd-9bf1-2ac96541a885" />
</p>

- I set the correct values and we get the flag

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/d36206cb-aacc-4f1c-b64e-1f5f63caf019" />
</p>

- Answer: `THM{should_we_allow_github_for_devs?}`

## Skills Learned
- Prioritized SOC alerts based on severity and potential impact
- Navigated a SOC dashboard to review alert details, statuses, verdicts, and assigned analysts
- Applied a structured Level 1 SOC triage workflow by assigning alerts, updating investigation status, and documenting findings
- Distinguished between true positives and false positives using contextual evidence such as IP addresses, domains, networks, URLs, and file characteristics
- Identified a double-extension file (`.mp4.exe`) as a common malware masquerading technique
- Evaluated potential data exfiltration alerts by analyzing transfer context and indicators of compromise
- Assessed GitHub download alerts using environmental context to determine whether activity was legitimate or suspicious
- Recorded investigation outcomes by updating verdicts, statuses, and analyst comments

## Summary
This room introduced the fundamentals of SOC Level 1 alert triage through a hands-on walkthrough of a SOC dashboard. It covered how to prioritize alerts based on severity, manage alert assignments and statuses, and investigate security events using available telemetry. Throughout the exercises, alerts were analyzed to determine whether they represented true positive security incidents or false positive activity, reinforcing a systematic and evidence based approach to efficient SOC triage
