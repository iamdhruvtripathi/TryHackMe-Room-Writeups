<p align="center">
  <img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Gobuster: The Basics
|  Room Name | Gobuster: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [Gobuster: The Basics](https://tryhackme.com/room/gobusterthebasics) |

# Room Information
```Type: Walkthrough
Difficulty: Easy
Tags: -
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
This room focuses on an introduction to Gobuster, an offensive security tool used for enumeration.
```
## Task 1
### I'm ready to learn about Gobuster!

- Answer: `No answer needed`

## Task 2

### I assigned the `10.67.140.183` as the first `nameserver` in the `/etc/resolv-dnsmasq` file and restarted the Dnsmasq service.

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/b40306ce-7fd4-49ce-8615-0bbf7dde0b47" />
</p>

- Answer: `No answer needed`

## Task 3
### What flag do we use to specify the target URL?
- Answer: `u`

### What command do we use for the subdomain enumeration mode?

- If we do `gobuster --help | grep subdomain`, we get the answer

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/7f3f0caf-687a-4cd2-93e7-fbfb179109ce" />
</p>

- Answer: `dns`

## Task 4
### Which flag do we have to add to our command to skip the TLS verification? Enter the long flag notation.

- Answer: `--no-tls-validation`

### Enumerate the directories of `www.offensivetools.thm`. Which directory catches your attention?

- This one was a bit tricky because I tried this first and it did not work even though the URL was correct

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/cf86b2b8-53d3-4969-9424-2f4830309836" />
</p>

- After doing some research, I found out you needed to type the machine IP address instead for it to work. We can see it worked

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/1f91cd40-a501-4d65-90a6-ccbed0a2152b" />
</p>

- Answer: `secret`

### Continue enumerating the directory found in question 2. You will find an interesting file there with a .js extension. What is the flag found in this file?

- We enumerate that directory that we found and it looks like we found two more

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/cf562ebe-3f2e-4c00-8f8c-d6291c490833" />
</p>

- Then, I enumerated the `/content` directory with the addition of the `-x` option that specifies the file extension we are looking for and looks like we found ourselves the flag

- Note: I had to restart my VM so the IP address changed to `10.64.160.231` but that didn't affect anything

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/7facf8bc-35a7-4e12-9979-04694701a688" />
</p>

- Now, to actually get the flag, we need to use the `curl` command

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/020e69e6-dc45-4266-949a-885b24de6112" />
</p>

- Answer: `THM{ReconWasASuccess}`

## Task 5

### Apart from the dns keyword and the -w flag, which shorthand flag is required for the command to work?

- The full command would be `gobuster dns -d example.thm -w /path/to/wordlist`

- Answer: `-d`

### Use the commands learned in this task, how many subdomains are configured for the offensivetools.thm domain?

- For this one I also had the same problem of not being able to resolve the domain name they gave us and so I needed to add the option `--resolver 10.64.160.231` for it to work

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/b6fc2cb1-3200-4d25-a1b0-ee8c41be52fe" />
</p>

- Answer: `4`

## Task 6

### Use the commands learned in this task to answer the following question: How many vhosts on the offensivetools.thm domain reply with a status code 200?

- Using the command `gobuster vhost -u "http://10.64.160.231" --domain offensivetools.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain --exclude-length 250-320` where we try to brute force how many `vhosts` there are on the domain `offensivetools.thm` and `--append-domain` makes sure to append to domain name to every entry from the word list and `exclude-length` filters out false positives

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/b3eff631-ede8-4a33-8352-ca27c586d35f" />
</p>

- Answer: `4`

## Skills Learned

* Learned the basic syntax and usage of Gobuster for web enumeration
* Identified and used common Gobuster flags such as `-u`, `-w`, and `-d`
* Performed directory and file enumeration against a target web server
* Used wordlists to discover hidden directories and resources
* Enumerated nested directories to uncover additional content within a web application
* Used the `-x` option to search for files with specific extensions during enumeration
* Conducted DNS subdomain enumeration using Gobuster's `dns` mode
* Configured a custom DNS resolver with the `--resolver` option when domain resolution issues occurred
* Performed virtual host (vhost) enumeration using Gobuster's `vhost` mode
* Used the `--append-domain` option to automate vhost discovery
* Applied response length filtering with `--exclude-length` to reduce false positives during enumeration

## Conclusion

This room provided a practical introduction to Gobuster and its role in reconnaissance and enumeration. Through hands-on exercises, I learned how to discover hidden directories, files, subdomains, and virtual hosts using different Gobuster modes and options. I also gained experience troubleshooting DNS resolution problems, using custom resolvers, filtering false positives, and retrieving discovered resources for further analysis. Overall, the room established a strong foundation in web enumeration techniques and demonstrated how Gobuster can be used to uncover valuable information during security assessments
