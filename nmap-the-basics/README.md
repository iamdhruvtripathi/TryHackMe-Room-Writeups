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


What is the last IP address that will be scanned when your scan target is `192.168.0.1/27`?

- Here, I used the `-sL` option with `nmap` when scanning the target `192.168.0.1/27`. This basically allows us to lists the targets without actually scanning them. The last IP address is listed at the bottom

  <img width="1197" height="526" alt="image" src="https://github.com/user-attachments/assets/51c1b273-5058-4f95-8d6b-dbf8502b28aa" />

- Answer: `192.168.0.31`

## Task 3

How many TCP ports are open on the target system at `10.64.138.29`?

- Here, I used the command below where I scanned the target system where I used `-sT` which performs a TCP connect scan and tries to complete the TCP three-way handshake with every target TCP port. We can see below there are 6 TCP ports open

  <img width="1511" height="263" alt="image" src="https://github.com/user-attachments/assets/954e70bd-7fc4-4170-b182-a867821bfeae" />

- Answer: `6`

Find the listening web server on `10.64.138.29` and access it with your browser. What is the flag that appears on its main page?

- We know from previous findings that TCP port `8008` is open and the service it is running is `http`. Therefore, it must be the web server and we can connect to it with our browser

  <img width="1263" height="221" alt="image" src="https://github.com/user-attachments/assets/34bf09d5-11b3-43c0-b7dc-912be941e627" />

- If we type in the correct URL with the target IP address and port number (`http://10.64.138.29:8008`), we get the flag

  <img width="1512" height="829" alt="image" src="https://github.com/user-attachments/assets/caf284e8-2f8c-4915-8da3-8e596e24597c" />

- Answer: `THM{SECRET_PAGE_38B9P6}`

## Task 4

What is the name and detected version of the web server running on `10.64.138.29`?

- I used the `-sV` option to show me the specific software version of the web service running on this target

  <img width="1310" height="228" alt="image" src="https://github.com/user-attachments/assets/1ace87e7-728a-4cc5-81b3-74439d1b514a" />

- Answer: `lighttpd 1.4.74`

## Task 5

What is the non-numeric equivalent of -T4?

- These options control the speed of your scan and there are 5 different speed options such as `T0 (paranoid)`, `T1 (sneaky)`, `T2 (polite)`, `T3 (normal)`, `T4 (aggressive)` and `T5 (insane)`

- Answer: `-T aggressive`

## Task 6

What option must you add to your nmap command to enable debugging?

- Answer: `-d`

## Task 7

What kind of scan will Nmap use if you run nmap MACHINE_IP with local user privileges?

- For this answer, if running with root privileges, nmap by defualt uses SYN scan but with local user privileges, it uses connect scan and that is because sending TCP SYN packets requires root privileges

- Answer: `connect scan`
## Skills Learned
- Used Nmap to perform host discovery and target enumeration
- Identified scan targets using CIDR notation and the `-sL` option
- Conducted TCP Connect scans with `-sT` to identify open ports
- Enumerated services and versions using `-sV`
- Accessed discovered web services through a browser to retrieve information
- Understood Nmap timing templates `(T0–T5)` and their purposes
- Enabled debugging with the `-d` option
- Learned the difference between SYN scans and Connect scans based on privilege level

## Conclusion
This room introduced the fundamentals of Nmap, including host discovery, port scanning, service enumeration, timing controls, and debugging. By completing the exercises, I gained hands-on experience identifying open ports, detecting running services, and understanding how scan behavior changes depending on user privileges
