<p align="center">
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

### Where is the "secrets.txt"  file located? (Full path of the file)

- We can use metepreter's search function and I typed `search -f secrets.txt` to find the file

<img width="751" height="259" alt="image" src="https://github.com/user-attachments/assets/7309593e-d2bc-45e6-8451-379153b155ba" />

- Answer: `c:\Program Files (x86)\Windows Multimedia Platform\secrets.txt`

### What is the Twitter password revealed in the "secrets.txt" file?

- I used the `cat` command to see the contents of the file

<img width="1181" height="101" alt="image" src="https://github.com/user-attachments/assets/4b99b927-af4a-45f3-9efd-7d9c9d308cc3" />

- Answer: `KDSvbsw3849!`

### Where is the "realsecret.txt" file located? (Full path of the file)

- We do the same thing here as the last question

<img width="750" height="212" alt="image" src="https://github.com/user-attachments/assets/67b31b1b-d34d-4bd8-a1a8-3bc614d43e47" />

Answer: `c:\inetpub\wwwroot\realsecret.txt`

### What is the real secret?

- I used the `cat` command once again

<img width="1220" height="79" alt="image" src="https://github.com/user-attachments/assets/f2a41e36-2435-49b5-a802-c41b2972c33b" />

- Answer: `The Flash is the fastest man alive`

##  Skills Learned

* Gained initial access to a Windows host using Metasploit's `psexec` exploit module
* Established and interacted with Meterpreter sessions for post-exploitation activities
* Collected host information using Meterpreter commands such as `sysinfo`
* Enumerated Active Directory domain information using Metasploit post-exploitation modules
* Identified and analyzed SMB shares through automated enumeration modules
* Managed Meterpreter sessions and leveraged Metasploit's session handling capabilities
* Enumerated running processes and migrated Meterpreter into privileged processes
* Extracted NTLM password hashes from memory using `hashdump`
* Performed password recovery from NTLM hashes using external cracking resources
* Searched for and located sensitive files on compromised systems using Meterpreter's file search functionality
* Retrieved and examined file contents directly through Meterpreter
* Gained practical experience with common Windows post-exploitation and credential-access techniques

## Conclusion

This room provided a hands-on introduction to Meterpreter and its role in post-exploitation. Through a Meterpreter session, I gathered system and domain information, enumerated network resources, migrated processes, extracted credentials, and located sensitive files on the target machine. Overall, the room demonstrated how Meterpreter's in-memory payloads and extensive post-exploitation features enable efficient system enumeration, credential harvesting, and data discovery during security assessments
