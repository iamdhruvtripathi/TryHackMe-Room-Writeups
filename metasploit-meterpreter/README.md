<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Metasploit: Meterpreter
|  Room Name | Metasploit: Meterpreter |
|----------|-------|
| Author | Dhruv Tripathi |
| Date | 06-17-2026 |
| Link | [Metasploit: Meterpreter](https://tryhackme.com/room/meterpreter) |

# Room Information
```Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Take a deep dive into Meterpreter, and see how in-memory payloads can be used for post-exploitation.
```
## Task 1
### No answer needed

- Answer: `No answer needed`

## Task 2
### No answer needed

- Answer: `No answer needed`

## Task 3
### No answer needed

- Answer: `No answer needed`

## Task 4
### No answer needed

- Answer: `No answer needed`

## Task 5
### What is the computer name?

- We are told to use this exploit `exploit/windows/smb/psexec` and the username is `ballen` and password is `Password1`. First, I did `use exploit/windows/smb/psexec`

<img width="747" height="104" alt="image" src="https://github.com/user-attachments/assets/40a3d34c-cc7d-4054-b993-0372be3dee52" />

- Then, I set the values for `RHOSTS`, `SMBPass` and `SMBUser`

<img width="750" height="212" alt="image" src="https://github.com/user-attachments/assets/80b2c542-87ec-454c-a133-126d517c2146" />

- Lastly, I ran the exploit and BOOM, we are in

<img width="755" height="356" alt="image" src="https://github.com/user-attachments/assets/0394487d-2690-48ed-817f-1309f21e20d0" />

- Now, we need the computer name and we can get this via the command `sysinfo`

<img width="1221" height="330" alt="image" src="https://github.com/user-attachments/assets/278130d2-ba07-456d-a2cc-c42bdfd38ded" />

- Answer: `ACME-TEST`

### What is the target domain?

- For this question, what we need to do first is to background the session (`Ctrl+Z`) and then use the module `post/windows/gather/enum_domain` and set the `SESSION` parameter

<img width="754" height="338" alt="image" src="https://github.com/user-attachments/assets/a537fb9e-485f-4f74-9656-798b33a4e748" />

- We see via listing `sessions -i` that meterpreter is running on session 1

<img width="753" height="256" alt="image" src="https://github.com/user-attachments/assets/00681502-b3d5-4dfa-bd8f-685459516233" />

- Then, I set the `SESSION` parameter to 1 and `run` and we see what the target domain is

<img width="1192" height="342" alt="image" src="https://github.com/user-attachments/assets/180e4895-f527-4ddf-a5d7-d495a56989e6" />

- Answer: `FLASH`

### What is the name of the share likely created by the user?

- We do the same thing here but instead we use the `post/windows/gather/enum_shares` module

<img width="746" height="487" alt="image" src="https://github.com/user-attachments/assets/2e10caec-e4dd-490d-ba68-186e0bd17ee0" />

- When I ran the exploit, we see the share that was likely created by the user

<img width="996" height="596" alt="image" src="https://github.com/user-attachments/assets/769ea703-35ef-446b-807b-d5ea7f8fa53c" />

### What is the NTLM hash of the jchambers user?

- For this question, I needed to migrate to the `lsass.exe` process and I listed via `ps` which processes are running

<img width="933" height="634" alt="image" src="https://github.com/user-attachments/assets/ede5fcf0-5793-4825-8873-e8f1a106941e" />

- Then, I successfully migrated to that process by typing `migrate 784` since that was the PID of `lsass.exe`

<img width="752" height="105" alt="image" src="https://github.com/user-attachments/assets/747abeb7-6493-4b4c-aa50-bea46e2cfe4e" />

- We then, run `hashdump` to see the NTLM hashes and find jchambers hash

<img width="1114" height="624" alt="image" src="https://github.com/user-attachments/assets/1aacf35b-3de2-4f43-82ea-b91c3f26bb37" />

- Answer: `69596c7aa1e8daee17f8e78870e25a5c`

### What is the cleartext password of the jchambers user?

- Using an online site such as `crackstation.net`, we can see the password below

<img width="1512" height="826" alt="image" src="https://github.com/user-attachments/assets/c7ffd1f1-001b-47f4-befe-4dff66bbd422" />

- Answer: `TrustNo1`
