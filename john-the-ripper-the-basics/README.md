<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# John the Ripper: The Basics
|  Room Name |  John the Ripper: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Date | 06-12-2026 |
| Link | [John the Ripper](https://tryhackme.com/room/johntheripperbasics) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn how to use John the Ripper, a powerful and adaptable hash-cracking tool.
```
## Task 1
### Let’s begin!

- Answer: `No answer needed`

## Task 2

### What is the most popular extended version of John the Ripper?

- Answer: `Jumbo John`

## Task 3

### Which website’s breach was the rockyou.txt wordlist created from?

- Answer: `rockyou.com`

## Task 4

### What type of hash is hash1.txt?

- We first need take note of this hash and use an online tool such as [Hash Type Identifer](https://hashes.com/en/tools/hash_identifier) to figure out the hash type

<img width="1216" height="667" alt="image" src="https://github.com/user-attachments/assets/b53ec193-f5d8-49cf-ae2d-e094fd7db851" />

- If we paste that hash value, we get a possible guess

<img width="1160" height="657" alt="image" src="https://github.com/user-attachments/assets/ea3da115-99f3-4365-9d4a-00d43db985e4" />

- Answer: `MD5`

### What is the cracked value of hash1.txt?

- I used the command
```bash
`john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt`. 
```

- Note that `--format=` specifies to `john` to use the standalone hash instead because John support many formats that use MD5 internally such as `MD5-Crypt`, `phpBB hashes`, etc. and can look very similar to `md5` and so we need to specifically state that we are using the plain MD5 digests

  <img width="1512" height="216" alt="image" src="https://github.com/user-attachments/assets/6cbd35ce-a1ac-4ffa-90d3-d4599dd022f1" />

- Answer: `biscuit`

### What type of hash is hash2.txt?

- We do the same thing here we did for the first question
<img width="1142" height="622" alt="image" src="https://github.com/user-attachments/assets/92895f7b-96f0-472a-8036-3d72a485ba1f" />

- If we paste that hash value, we get a possible guess

<img width="1512" height="861" alt="image" src="https://github.com/user-attachments/assets/79c46ad7-e18d-4132-a7db-c7864b88a8e2" />

- Answer: `SHA1`

### What is the cracked value of hash2.txt?

- Note that I used the same command from question 2 but switched from `md5` to `sha1` when specifying the format

  <img width="1512" height="237" alt="image" src="https://github.com/user-attachments/assets/7d040fae-93aa-4cae-b67b-a4d8b8d8eb4c" />

- Answer: `kangeroo`

 ### What type of hash is hash3.txt?

- If we use the same tools again as we did for the previous questions, we get the answer to be

- Answer: `SHA256`

### What is the cracked value of hash3.txt?

- The command used was
```bash
john --format=raw-sha256 --wordlist=/usr/share/wordlists/rockyou.txt hash3.txt 
```

- Answer: `microphone`

### What type of hash is hash4.txt?

- Answer: `Whirlpool`

### What is the cracked value of hash4.txt?

- The command used was
```bash
john --format=whirlpool --wordlist=/usr/share/wordlists/rockyou.txt hash4.txt
```
- Note that we do not need to use the `raw-` because `john` already recognizes the format without it

- Answer: `colossal`
## Task 5
## Task 6
## Task 7
## Task 8
## Task 9
## Task 10
## Task 11
