<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# John the Ripper: The Basics
|  Room Name |  John the Ripper: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
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
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt. 
```

- Note that `--format=` specifies to `john` to use the standalone hash instead because John supports many formats that use MD5 internally such as `MD5-Crypt`, `phpBB hashes`, etc. and can look very similar to `md5` and so we need to specifically state that we are using the plain MD5 digests

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

### What do we need to set the --format flag to in order to crack this hash?

- We can use the following command to figure which which format flag we need
```bash
john --list=formats | grep ntlm
```
  <img width="1159" height="85" alt="image" src="https://github.com/user-attachments/assets/fca99348-c495-41b7-aed8-ff1f3e74b3ed" />

- Answer: `nt`

### What is the cracked value of this password?

- I used the following command to crack the hash
```bash
john --format=nt --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt 
```
<img width="1512" height="258" alt="image" src="https://github.com/user-attachments/assets/3a757ab2-9a47-40db-aa91-bee48ee5b462" />

- Answer: `mushroom`

## Task 6

### What is the root password?

- This is a two step process because first we need to combine both `/etc/passwd` and `/etc/shadow` into one file with the command below and save it to a file. This is because `john` can be very particular about the format of the data and so we need to use `unshadow` for this task
```bash
unshadow local_passwd local_shadow > unshadow.txt
```
- Then, we feed that file into John to crack the root password
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt unshadow.txt
```
<img width="1512" height="824" alt="image" src="https://github.com/user-attachments/assets/b1658e45-0507-4385-8f9e-fed18341d85f" />

- Answer: `1234`

## Task 7

### What is Joker’s password?

- First thing we need to do is change the `hash07.txt` file to prepend the name `joker` in front of the hash. This is because `john` needs the data in a specific format for it to actually create the wordlist. This is based on the username `joker` where it mangles the word creating passwords from the username such as: `j0ker`, `Joker`, `joker123`, etc. Also, using the hash identifier website, we identify the hash type as `md5`

  <img width="1512" height="76" alt="image" src="https://github.com/user-attachments/assets/8ae44318-f63b-4b88-b49f-9685f6863a0d" />

- Then we feed `john` the file
```bash
john --single --format=raw-md5 hash07.txt 
```

  <img width="1512" height="244" alt="image" src="https://github.com/user-attachments/assets/96e056c3-86fa-4616-b521-6fb15b5f9cd5" />

- Answer: `Jok3r`

## Task 8

### What do custom rules allow us to exploit?

- Answer: `password complexity predictability`

### What rule would we use to add all capital letters to the end of the word?

- `Az` takes the characters (such as `123`) and appends it to the word (`cat` would become `cat123`). `[A-Z]` includes only uppercase characters and must be enclosed with `" "`

- Answer: `Az"[A-Z]"`

### What flag would we use to call a custom rule called THMRules?

- Answer: `--rule=THMRules`

## Task 9

### What is the password for the secure.zip file?

- For this, we use the command below to get the hash
```bash
zip2john secure.zip > zip_hash.txt
```
  <img width="1512" height="211" alt="image" src="https://github.com/user-attachments/assets/b18223e2-27b4-44f9-a949-2153e602a865" />

- Then, we feed that hash format (file) into `john` so it can crack the hash

  <img width="1512" height="227" alt="image" src="https://github.com/user-attachments/assets/f7a01133-e555-4300-8193-aa6753d48a3a" />

- Answer: `pass123`

### What is the contents of the flag inside the zip file?

- We use the password that we cracked to see the content inside the zip file

  <img width="1512" height="146" alt="image" src="https://github.com/user-attachments/assets/966cecde-ae20-4d01-a5df-a7ec4e223cfc" />

- Answer: `THM{w3ll_d0n3_h4sh_r0y4l}`
## Task 10

### What is the password for the secure.rar file?

- We type a very similar command similar to the last task
```bash
rar2john secure.rar > rar_hash.txt
```
  <img width="1512" height="312" alt="image" src="https://github.com/user-attachments/assets/be9d6001-4ae6-4289-bfe1-891a5cd0a90c" />

- Then, we feed that hash format (file) into `john` so it can crack the hash
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt 
```
<img width="1512" height="291" alt="image" src="https://github.com/user-attachments/assets/fab7fc5d-d181-490e-b9c8-a64d91ad973b" />

- Answer: `password`

### What are the contents of the flag inside the rar file?

- We use the password that we cracked to see the content inside the rar file

  <img width="1512" height="336" alt="image" src="https://github.com/user-attachments/assets/6178fa3f-d713-445e-a2b6-f9c210181c8f" />

## Task 11

### What is the SSH private key password?

- First, we need to get the hash of this private key
```bash
/opt/john/ssh2john.py id_rsa > id_rsa_hash.txt
```

  <img width="1512" height="427" alt="image" src="https://github.com/user-attachments/assets/7de47d5c-758d-4ea4-aa45-72eab4663d95" />

- Then, we feed john the file
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt 
```

  <img width="1512" height="263" alt="image" src="https://github.com/user-attachments/assets/27aa8b6d-3100-4e86-a8b5-a1e8dbf4cc5b" />

- Answer: `mango`

## Skills Learned

* Used John the Ripper to crack passwords across multiple hash formats
* Identified hash types and selected the correct `--format` values for cracking
* Cracked `MD5`, `SHA1`, `SHA256`, `Whirlpool`, and `NTLM` hashes using the RockYou wordlist
* Enumerated supported formats with `john --list=formats`
* Combined `/etc/passwd` and `/etc/shadow` using `unshadow` to crack Linux account passwords
* Used Single Crack Mode to generate username-based password candidates
* Created and applied custom rules to exploit predictable password complexity patterns
* Extracted and cracked hashes from password-protected ZIP and RAR archives using `zip2john` and `rar2john`
* Converted encrypted SSH private keys into crackable hashes with `ssh2john.py`
* Gained practical experience with common password auditing and cracking workflows

## Conclusion

This room introduced the core functionality of John the Ripper and its role in password auditing. Through hands-on exercises, I identified and cracked multiple hash types, recovered passwords from Linux authentication files, encrypted archives, and SSH private keys, and explored features such as Single Crack Mode and custom rules. Overall, the room provided a solid foundation in password-cracking techniques while reinforcing the importance of secure password practices
