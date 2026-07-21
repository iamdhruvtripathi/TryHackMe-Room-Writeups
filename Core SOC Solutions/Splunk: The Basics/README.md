<p align="center">
<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Splunk: The Basics
|  Room Name | Splunk: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [Splunk: The Basics](https://tryhackme.com/room/splunk101) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: - 
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Understand how SOC analysts use Splunk for log investigations.
```
## Task 1

### Continue with the next task.

- Answer: `No answer needed`

## Task 2

### Connect with the lab.

- Answer: `No answer needed`

## Task 3

### Which component is used to collect and send data over the Splunk instance?

- The Splunk Forwarder is lightweight agent installed on endpoints that collects data and sends it to the Splunk instance

- Answer: `Forwarder`

## Task 4

### In the Add Data tab, which option is used to collect data from files and ports?

- I clicked on the `Add Data` quick link
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/78a792c7-6184-416b-9c35-4c3a0b15189c" />
</p>

- We see the option listed below
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/d34074a1-9be2-49c5-9f1a-ef82ea55f592" />
</p>

- Answer: `Monitor`

## Task 5

### Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file?

- We can see below how many events there are
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/507f7bfe-9649-4205-954d-ef6441feee36" />
</p>

- Answer: `2862`

### How many log events are captured by the user Maleena?

- Using the below query, we get the answer
```
index="vpn_logs"
| search UserName="Maleena" 
| stats count
```
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/e5f72ce7-e724-4868-9261-b61e9ca601ce" />
</p>

- Answer: `60`

### What is the username associated with IP 107.14.182.38?

- Using the below query, we get the answer
```
index="vpn_logs"
| search Source_ip="107.14.182.38"
| stats values(UserName) as UserName count
```
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/77bbbb85-5e01-49e1-9960-ace504105208" />
</p>

- Answer: `20`

### What is the number of events that originated from all countries except France?

- Using the query below, we get the answer
```
index="vpn_logs"
| search Source_Country!="France"
| stats count
```
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/689f7759-6285-4d45-98b7-1c4dbefe074d" />
</p>

- Answer: `2814`

### How many VPN events were associated with the IP 107.3.206.58?

- Using the query below, we get the answer
```
index="vpn_logs"
| search Source_ip="107.3.206.58"
| stats count
```
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/95d4ca85-2a31-4eb1-b2b3-2ceaf2b2b1e4" />
</p>

- Answer: `14`

## Skills Learned

* Understood Splunk's core architecture, including the role of Forwarders in collecting and forwarding log data
* Imported log files into Splunk and created a custom index for organizing data
* Navigated the Splunk interface to ingest and search log data efficiently
* Used basic Search Processing Language (SPL) commands to filter, search, and analyze events
* Queried logs based on usernames, IP addresses, and countries to identify specific activity
* Applied the `stats` command to count events and summarize search results during log investigations
* Gained practical experience performing fundamental SOC-style log analysis using VPN authentication logs

## Conclusion

This room introduced the fundamentals of using Splunk for security monitoring and log analysis. I learned how to ingest data, organize it within an index, and use SPL queries to investigate VPN logs by filtering on users, IP addresses, and geographic locations. These foundational skills demonstrate how security analysts leverage Splunk to efficiently search large datasets, identify relevant events, and support incident investigations
