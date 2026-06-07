<img width="624" height="75" alt="image" src="https://github.com/user-attachments/assets/fbb5b4c0-99aa-4c61-af50-5a7c083c090a" /><p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Tcpdump: The Basics
|  Room Name |  Tcpdump: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Date | 06-06-2026 |
| Link | [Tcpdump: The Basics](https://tryhackme.com/room/tcpdump) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn how to use Tcpdump to save, filter, and display packets.
```
## Task 1
What is the name of the library that is associated with tcpdump?
- Answer: `libpcap`

## Task 2
What option can you add to your command to display addresses only in numeric format?
- Answer: `-n`

Note: The use of `-n` means that tcpdump does not resolve the IP addresses to readable domain names
## Task 3

How many packets in traffic.pcap use the ICMP protocol?

- To solve this task, I typed the following command
```bash
tcpdump -r traffic.pcap icmp -n | wc
```
- This command tells `tcpdump`, the network packet analyzer, to read packets from `traffic.pcap` which use the `icmp` protocol and `-n` means to not resolve the IP addresses to hostnames and then this is piped to `wc` which counts the number of lines in the file for this specific command

<img width="624" height="75" alt="image" src="https://github.com/user-attachments/assets/579e262a-6e4d-49dc-8f81-608b58b549a4" />

- Answer: `26`

## Task 4
## Task 5
## Skills Learned
## Conclusion
