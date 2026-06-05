<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Wireshark: The Basics
|  Room Name |  Wireshark: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Date | 06-05-2026 |
| Link | [Wireshark: The Basics](https://tryhackme.com/room/wiresharkthebasics) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn the basics of Wireshark and how to analyse protocols and PCAPs.
```
## Task 1
Which file is used to simulate the screenshots?
- Answer: `http1.pcapng`

Which file is used to answer the questions?
- Answer: `Exercise.pcapng`

## Task 2

Use the "Exercise.pcapng" file to answer the questions.
Read the "capture file comments". What is the flag?

- To solve this challenge, I first needed to open the `Exercise.pcapng` file within Wireshark

<img width="1012" height="574" alt="image" src="https://github.com/user-attachments/assets/2410c709-1eef-4726-b3c6-4f284dcaf455" />

- Then, I went to `Statistics` at the top and clicked `Capture File Properties` from the dropdown

<img width="1512" height="865" alt="image" src="https://github.com/user-attachments/assets/cae7977e-5a58-413c-8b56-dc06aa18721d" />

- I then scrolled down on the `Capture File Comments` pane and found the flag

<img width="902" height="513" alt="image" src="https://github.com/user-attachments/assets/5cf1c35b-4496-45f6-8f1f-b7d408baf124" />

- Answer: `TryHackMe_Wireshark_Demo`

What is the total number of packets?

- We can see at the bottom the total number of packets

<img width="1333" height="667" alt="image" src="https://github.com/user-attachments/assets/d8a60693-73b0-4195-bed3-15c6f0e812d9" />

- Answer: `58620`

What is the SHA256 hash value of the capture file?

- If we click on `Statistics` again and select `Capture File Properties`, we can see the SHA256 hash

<img width="1250" height="654" alt="image" src="https://github.com/user-attachments/assets/7210eb0d-9f3b-42eb-9711-0f016cbeee83" />

Answer: `f446de335565fb0b0ee5e5a3266703c778b2f3dfad7efeaeccb2da5641a6d6eb`

## Task 3
## Task 4
## Task 5
## Task 6
