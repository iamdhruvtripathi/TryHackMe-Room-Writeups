<p align="center">
<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# REMnux: Getting Started
|  Room Name | REMnux: Getting Started |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [REMnux: Getting Started](https://tryhackme.com/room/remnuxgettingstarted) |

# Room Information
```bash Type: Walkthrough
Difficulty: Easy
Tags: - 
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Learn how you can use the tools inside the REMnux VM.
```
## Task 1

### Proceed with the next tasks to learn more!

- Answer: `No answer needed`

## Task 2

### I'm excited to learn more about the tools inside the REMnux VM!

- Answer: `No answer needed`

## Task 3

### What Python tool analyzes OLE2 files, commonly called Structured Storage or Compound File Binary Format?

- Answer: `oledump.py`

Note: This is a Python tool that analyzes `OLE2` files called Structured Storage or Compound File Binary Format. `OLE` stands for Object Linking and Embedding

### What tool parameter we used in this task allows you to select a particular data stream of the file we are using it with?

- Answer: `-s`

### During our analysis, we were able to decode a PowerShell script. What command is commonly used for downloading files from the internet?

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/7dd09e26-62e3-4b5b-9b77-154d577e67bc" />
</p>

- Answer: `Invoke-WebRequest`

### What file was being downloaded using the PowerShell script?

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/919c74e6-171d-420b-b416-30796e408be4" />
</p>

- Answer: `Doc-3737122pdf.exe`

### During our analysis of the PowerShell script, we noted that a file would be downloaded. Where will the file being downloaded be stored?

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/09b448a3-579a-416b-a2f1-e06a2aa6748e" />
</p>

- Answer: `$TempFile`

### Using the tool, scan another file named possible_malicious.docx located in the `/home/ubuntu/Desktop/tasks/agenttesla/` directory. How many data streams were presented for this file?

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/34c41e07-0edf-4222-b626-d1f7cdea5c80" />
</p>

- Answer: `16`

### Using the tool, scan another file named possible_malicious.docx located in the `/home/ubuntu/Desktop/tasks/agenttesla/` directory. At what data stream number does the tool indicate a macro present?

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/a8802c3b-6eb4-45a3-8ac9-897cadb7190a" />
</p>

- Answer: `8`
