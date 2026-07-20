<p align="center">
<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Introduction to EDR
|  Room Name | Introduction to EDR |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [Introduction to EDR](https://tryhackme.com/room/introductiontoedrs) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: - 
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn the fundamentals of EDR and explore its features and working.
```
## Task 1

### I am all set!

- Answer: `No answer needed`

## Task 2

### Which feature of EDR provides a complete context for all the detections?

- An EDR can collect detailed data such as process, registry, file & folder modifications, user actions, and much more giving us great visibility on what is happening on that endpoint. Below is a process tree for example

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/65a00d01-f4a4-4fb3-8548-ea757773fb43" />
</p>

- Answer: `Visibility`

### Which process spawned sc.exe?

- We can see the process before `sc.exe` that spawned it

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/977c77e6-8c84-4de3-bcba-198834854fff" />
</p>

- Answer: `cmd.exe`

## Task 3
### In the given analogy, what presents an AV?

- In the given analogy, we see what it refers to. What this is saying is an attacker can sneak through basic security checks without getting detected through the initial entry point or if the AV doesn't find a matching signature, it lets the attacker through

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/107dbac5-f1d0-4e96-86a6-5ccab1680bb1" />
</p>

- Answer: `immigration check`

### Which legitimate process was hijacked by the attacker in the scenario?

- In the scenario breakdown, we can see the payload being injected into this specific process

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/4b488399-0bf5-46d7-a506-9c867494557d" />
</p>

- Answer: `svchost.exe`

### Which security solution might mark this activity as clean?

- We can see in this table that the `Antivirus` will mark it clean because it does not monitor memory injections unlike an EDR which does

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/bd4a7d12-e65b-4dac-a970-0d274b0255fa" />
</p>

- Answer: `Antivirus`

## Task 4

### Which component of the EDR is responsible for collecting telemetry from the endpoints?

- EDR agents sit on each endpoint and send information about all activities to the central EDR console

- Answer: `Agent`

### An EDR agent is also known as a?

- Answer: `sensor`

## Task 5

### Which telemetry data helps in detecting C2 communications?

- Network Connections telemetry data can help with any identified connections to a C2 server, unusual port usage, data exfiltration, or lateral movement within the network

- Answer: `Network Connections`

### Where are the configuration settings of a Windows system primarily stored?

- Answer: `registry`

## Task 6

### Which feature of the EDR helps you identify threats based on known malicious behaviours? 

- EDR flags any activity that matches any known IOC. An example is if a downloaded executable file has a hash that is matched in the threat intelligence feed which is then flagged by the EDR

- Answer: `IOC Matching`

## Task 7

### Which tool was launched by CMD.exe to download the payload on DESKTOP-HR01?

- I first selected the top most alert associated with `DESKTOP-HR01`
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/5cbd4c11-62ea-4acf-b73c-d4f0e5c7b92c" />
</p>

- We can see what tool was launched by `CMD.exe`
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/4c88b4e0-cfd9-45c4-afd0-fa3fb6249f38" />
</p>

- Answer: `CURL.exe`

### What is the absolute path to the downloaded malware on the DESKTOP-HR01 machine?

- If we click on `IOC/Indicators` at the top, we can see at what location the executable is located at

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/ff874d4d-b01e-4c25-83c5-6aab44e1961c" />
</p>

- Answer: `C:\Users\Public\install.exe`

### What is the absolute path to the suspicious syncsvc.exe on the WIN-ENG-LAPTOP03 machine?

- I clicked on the alert associated with `WIN-ENG-LAPTOP03`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/d2f54633-80b1-4bad-859f-2551fb580a8a" />
</p>

- On the `IOC/Indicators` tab, we see where the executable is located

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/725c758b-0791-4cf6-a3b4-bc36558cc719" />
</p>

- Answer: `C:\Users\haris.khan\AppData\Local\Temp\syncsvc.exe`

### On which URL was the exfiltration attempt being made on WIN-ENG-LAPTOP03?

- I clicked on the `Process Info` tab and the `syncsvc.exe` circle and we can see where the attacker attempted to exfiltrate the data to

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/8b321bbd-3daf-4149-8fad-165dd0c368da" />
</p>

- Answer: `https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dmp`

### What was UpdateAgent.exe labelled by Threat Intel on DESKTOP-DEV01?

- I clicked on the alert associated with `DESKTOP-DEV01`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/a98d9875-f48a-4587-b869-e710885eaf27" />
</p>

- If we click on the `Process Info` tab and then the `UpdateAgent.exe` circle, we see the `Threat Intel` information

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/39bd0556-c65d-4bb9-b0d5-a581514e74a8" />
</p>

- Answer: `Known internal IT utility tool`

## Skills Learned

* Understood the purpose of Endpoint Detection and Response (EDR) and how it differs from traditional antivirus solutions
* Learned how EDR provides endpoint visibility by collecting telemetry such as processes, file activity, registry changes, network connections, and user actions
* Explored process trees to trace process execution and identify parent-child relationships during investigations
* Identified how attackers abuse legitimate processes through techniques such as process injection and why EDR can detect these behaviors
* Gained an understanding of EDR architecture, including the role of agents (sensors) in collecting and forwarding endpoint telemetry
* Learned the importance of different telemetry sources, including network connections for detecting command-and-control (C2) activity and the Windows registry for monitoring configuration changes
* Explored IOC matching and threat intelligence to identify known malicious files, processes, and behaviors
* Practiced investigating EDR alerts by analyzing process information, indicators of compromise, executable paths, URLs, and threat intelligence labels
* Improved skills in tracing malicious activity from initial execution through payload download and attempted data exfiltration

## Conclusion

This room introduced the core concepts of Endpoint Detection and Response and demonstrated how EDR extends beyond the capabilities of traditional antivirus solutions by continuously monitoring endpoint activity and behavioral telemetry. Through hands-on investigation of simulated alerts, I learned how to analyze process trees, review indicators of compromise, identify suspicious file locations, examine network activity, and leverage threat intelligence to understand attacker behavior. Overall, the room provided a solid foundation in EDR fundamentals and reinforced the importance of endpoint visibility and behavioral analysis in modern threat detection and incident response
