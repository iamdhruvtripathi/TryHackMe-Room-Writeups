<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Wireshark: The Basics
|  Room Name |  Wireshark: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
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

- To solve this task, I first needed to open the `Exercise.pcapng` file within Wireshark

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

Use the "Exercise.pcapng" file to answer the questions. View packet number 38. Which markup language is used under the HTTP protocol?

- For this task, I clicked on `Go` at the top and selected `Go to packet` and typed in 38 and clicked on the button `Go to packet`

<img width="1062" height="527" alt="image" src="https://github.com/user-attachments/assets/0b1fe8d8-c6ca-4eb0-aab6-cda794428c68" />

- If we click on packet 38, we can see it uses this markup language

<img width="1161" height="658" alt="image" src="https://github.com/user-attachments/assets/07396e4e-e291-4582-91f2-28684dc44434" />

Answer: `eXtensible Markup Language`

What is the arrival date of the packet? (Answer format: Month/Day/Year)

- If we click where it says `Frame 38` at the top, we can see the arrival date

<img width="1122" height="560" alt="image" src="https://github.com/user-attachments/assets/7239125f-66f7-4564-9c42-b444f6ba91e6" />

- Answer: `05/13/2004`

What is the TTL value?

- If we click where it says `Internet Protocol Version 4`, we can see the TTL value

<img width="1189" height="608" alt="image" src="https://github.com/user-attachments/assets/d2b5893a-b6a4-45b6-982d-d4a23b0a566e" />

- Answer: `47`

What is the TCP payload size?

- I scrolled down a little bit and clicked on where it said `Tranmission Control Protocol` and we can see the TCP Payload size

<img width="1206" height="621" alt="image" src="https://github.com/user-attachments/assets/e54a34c6-75e1-47ee-a853-8c3a21455491" />

- Answer: `424`

What is the e-tag value?
(For example: 82ecb-6321-9e904585)

- We can find the e-tag by clicking where it says `HyperText Transfer Protocol`

<img width="1271" height="637" alt="image" src="https://github.com/user-attachments/assets/06867cd1-bde0-4c04-8c74-39a688f4744f" />

Answer: `9a01a-4696-7e354b00`

## Task 4

Use the "Exercise.pcapng" file to answer the questions. Search the "r4w" string in packet details. What is the name of artist 1?

- I first selected `Edit` at the top and clicked on `Find packet` from the dropdown. Then, I kept the default settings of `Packet detail`, `Narrow & Wide`, and `String` and typed in `r4w`

<img width="1085" height="585" alt="image" src="https://github.com/user-attachments/assets/6945598d-ab0a-4c26-bce0-1db5ee7a17cc" />

- When I clicked `Find`, it led me to packet `33790` and we can see the full artist name

<img width="1195" height="431" alt="image" src="https://github.com/user-attachments/assets/86022e52-83f7-4e27-979f-268a14488cc0" />

Answer: `r4w8173`

Go to packet 12 and read the packet comments. What is the answer?
Note: use md5sum <filename> terminal command to get MD5 hash

- From what we have learnt before, if we go find packet 12, right click and then click on `Packet comment`, we see the following

<img width="1512" height="816" alt="image" src="https://github.com/user-attachments/assets/654db987-623f-4108-920e-fe24a876c5c2" />

Note: You will see `This_is_Not_a_Flag_This_is_Not_a_Flag_This_is_Not_a_Flag_This_is_Not_a_Flag_This_is_Not_a_Flag_This_is_Not_a_Flag at` first, but you need to scroll down

- I followed the instructions and saved it as following

<img width="1512" height="861" alt="image" src="https://github.com/user-attachments/assets/834dd993-e85d-4bc2-bc59-956a0647a0d2" />

- Then, I opened up terminal and typed the following to get the answer

<img width="658" height="235" alt="image" src="https://github.com/user-attachments/assets/14e674fc-d6c1-4c7a-9cc2-28ed226b3f7a" />

- Answer: `911cd574a42865a956ccde2d04495ebf`

There is a ".txt" file inside the capture file. Find the file and read it; what is the alien's name?

- From what we have learnt before, we need to find the packet containing `.txt` and we type as follows

<img width="1512" height="860" alt="image" src="https://github.com/user-attachments/assets/7e400911-5749-4675-9fbc-16beb86c01c8" />

- We see that `note.txt` is here in packet 1652 and so we just need to export the packet bytes

<img width="1182" height="672" alt="image" src="https://github.com/user-attachments/assets/f76e45b2-c543-4524-bd0b-0db6af8c2fae" />

- I clicked on `File -> Export Objects -> HTTP` to extract the file and used the filter to save `note.txt` specifically

<img width="1512" height="860" alt="image" src="https://github.com/user-attachments/assets/316ca852-feef-4cbf-a4b5-0e3d431f6c7f" />

- The alien's name is
  
<img width="1361" height="758" alt="image" src="https://github.com/user-attachments/assets/4281b107-eac3-4457-80b6-e93030023d5e" />

- Answer: `PACKETMASTER`

Look at the expert info section. What is the number of warnings?

- For this one, you need to click on the red circle in the bottom left corner and then it shows you the number of warnings at the top in the `count` section

<img width="1146" height="632" alt="image" src="https://github.com/user-attachments/assets/36a4da10-0b11-4de4-bb3d-c40a08bba1c1" />

- Answer: `1636`

## Task 5

Use the "Exercise.pcapng" file to answer the questions.
Go to packet number 4. Right-click on the "Hypertext Transfer Protocol" and apply it as a filter.
Now, look at the filter pane. What is the filter query?

- I went to packet number 4 and right clicked and used the option `Apply as filter`

<img width="1363" height="694" alt="image" src="https://github.com/user-attachments/assets/4763e99d-7956-46c9-a1e5-01a6906704b5" />

- Answer: `http`

What is the number of displayed packets?

- We can see at the bottom right the number of displayed packets

<img width="1006" height="512" alt="image" src="https://github.com/user-attachments/assets/5512fcb6-1dc8-4a66-8767-a6330f009198" />

- Answer: `1089`

Go to packet number 33790, follow the HTTP stream, and look carefully at the responses.
Looking at the web server's response, what is the total number of artists?

- I went to packet 33790 and right clicked and selected `Follow` and `HTTP stream` which led me here

<img width="1512" height="838" alt="image" src="https://github.com/user-attachments/assets/67c41b4f-cc3d-4240-b242-97ff4377b0bf" />

- I typed in `artists` to filter for the artists and we can see there are exactly 3 artists here

<img width="1145" height="450" alt="image" src="https://github.com/user-attachments/assets/20364c10-43df-4807-bec6-36339d8e3ab5" />

- Answer: `3`

What is the name of the second artist?

- We can see the artists name here

<img width="1273" height="498" alt="image" src="https://github.com/user-attachments/assets/531d6e38-8ee1-4c61-b568-9bad2ecf848e" />

- Answer: `Blad3`

## Skills Learned

* Navigated and analyzed PCAP/PCAPNG files in Wireshark
* Viewed capture file properties, comments, and hashes
* Inspected HTTP, TCP, and IPv4 packet details
* Located specific packets and searched packet contents
* Analyzed timestamps, TTL values, payload sizes, and HTTP headers
* Applied display filters and followed HTTP streams
* Extracted files and HTTP objects from packet captures
* Used packet comments and Expert Information for analysis
* Performed basic network traffic and protocol analysis

## Conclusion

This room introduced the fundamentals of Wireshark and packet analysis. Through hands-on exercises, I learned how to inspect network traffic, apply filters, follow protocol streams, and extract useful information from packet captures. These skills provide a strong foundation for network troubleshooting, digital forensics, and cybersecurity investigations
