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
## Task 6
## Task 7
