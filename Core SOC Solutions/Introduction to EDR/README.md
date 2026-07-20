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
