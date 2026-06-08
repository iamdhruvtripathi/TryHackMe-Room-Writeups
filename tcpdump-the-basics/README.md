<p align="center">
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

  <img width="1274" height="155" alt="image" src="https://github.com/user-attachments/assets/120ec8bf-a78c-45aa-9542-5d406784f412" />

- Answer: `26`

What is the IP address of the host that asked for the MAC address of 192.168.124.137?

- This one was a bit tricky because we needed to remember what we learned previously. We know this uses `arp` because `arp` is the protocol that is used when a client asks for a MAC address given an IP address and so we filtered by the `arp` protocol

  <img width="1273" height="176" alt="image" src="https://github.com/user-attachments/assets/97ac9aef-59e6-4c08-baf3-165b5b4cf446" />

- Answer: `192.168.124.148`

What hostname (subdomain) appears in the first DNS query?
- This one also required a bit of thinking because we know that DNS uses port 53 and so we filtered by that specific port. Essentially, we are reading the `traffic.pcap` file and filtering by the port number 53 to get only those specific packets

  <img width="1395" height="368" alt="image" src="https://github.com/user-attachments/assets/5284a193-f720-4ea4-8626-be0db2c50159" />
- Answer: `mirrors.rockylinux.org`

## Task 4

How many packets have only the TCP Reset (RST) flag set?

- Here, I used the command below to see where only the `tcp-rst` flag was set and piped it to `wc` to count the number of lines it showed
- To give more of a explanation, `tcp[tcpflags]` is a shorthand way of saying to go directly to the byte containing the TCP flags (which is Byte 13). A a byte is made up of 8 bits and remembering which bit is turned on (1) or off (0) gets a bit annoying and so we are able to use this shorthand to say give the packets where the `tcp-rst` flag is set. In binary, it would be bit 2 that is turned on (1) that indicates the flag is set. An example is `00000100`

  <img width="1306" height="126" alt="image" src="https://github.com/user-attachments/assets/acc34aa3-0a14-4335-b56e-94fd99275408" />

- Answer: `57`

What is the IP address of the host that sent packets larger than 15000 bytes?

- I used the command below to get the answer. Essentially, we can use `greater 15000` to filter out the packets that we want. This gives us only packets larger than 15000 bytes. For conciseness, I only output the first 5 packets

  <img width="1241" height="185" alt="image" src="https://github.com/user-attachments/assets/3b3139f0-d70b-4c9b-bcd4-bbddaedddda0" />

- Answer: `185.117.80.53`

## Task 5

What is the MAC address of the host that sent an ARP request?
- Here, I used the `-e` filter to include MAC addresses in my search and then used `arp` as the filter to search only for the ARP protocol which gave us the answer

  <img width="1398" height="85" alt="image" src="https://github.com/user-attachments/assets/a06738f1-e6f5-4c1e-a7d9-c0e3bc5702d3" />

- Answer: `52:54:00:7c:d3:5b`

## Skills Learned
- Used tcpdump to read and analyze packet capture (`.pcap`) files
- Applied protocol based filters for ICMP, ARP, DNS, and TCP traffic
- Used common tcpdump options such as `-r`, `-n`, and `-e`
- Identified hosts, IP addresses, MAC addresses, and DNS queries from network traffic
- Filtered packets using TCP flags and packet size conditions
- Leveraged command-line tools such as `wc` to quickly quantify filtered results
- Gained a better understanding of network protocols including ARP, ICMP, DNS, and TCP

## Conclusion
This room provided a practical introduction to tcpdump and its packet filtering capabilities. By analyzing a packet capture file, I learned how to identify specific protocols, inspect network communications, and extract useful information such as IP addresses, MAC addresses, DNS requests, TCP flags, and packet sizes. Overall, the room strengthened my understanding of network traffic analysis and demonstrated how tcpdump can be used for troubleshooting and basic network investigations
