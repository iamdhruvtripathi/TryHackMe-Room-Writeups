<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Nmap: The Basics
|  Room Name |  Nmap: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Date | 06-08-2026 |
| Link | [Nmap: The Basics](https://tryhackme.com/room/nmap) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn how to use Nmap to discover live hosts, find open ports, and detect service versions.
```
## Task 1

It’s time to find out who is listening on the network.

- Answer: `No answer needed`

## Task 2


What is the last IP address that will be scanned when your scan target is 192.168.0.1/27?

- Here, I used the `-sL` option with `nmap` when scanning the target `192.168.0.1/27`. This basically allows us to lists the targets without actually scanning them. The last IP address is listed at the bottom

  <img width="1197" height="526" alt="image" src="https://github.com/user-attachments/assets/51c1b273-5058-4f95-8d6b-dbf8502b28aa" />

- Answer: `192.168.0.31`

## Task 3

How many TCP ports are open on the target system at `10.64.138.29`?

- Here, I used the command below where I scanned the target system where I used `-sT` which performs a TCP connect scan and tries to complete the TCP three-way handshake with every target TCP port. We can see below there are 6 TCP ports open

  <img width="1511" height="263" alt="image" src="https://github.com/user-attachments/assets/954e70bd-7fc4-4170-b182-a867821bfeae" />

- Answer: `6`

## Task 4
## Task 5
## Task 6
## Skills Learned
## Conclusion
