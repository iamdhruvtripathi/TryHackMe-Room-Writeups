<p align="center">
<img src="https://assets.tryhackme.com/img/logo/tryhackme_logo_full.svg" width="150" alt="TryHackMe Logo">
</p>

# Elastic Stack: The Basics
|  Room Name | Elastic Stack: The Basics |
|----------|-------|
| Author | Dhruv Tripathi |
| Link | [Elastic Stack: The Basics](https://tryhackme.com/room/investigatingwithelk101) |

# Room Information
```bash Type: Walkthrough
Difficulty: Medium
Tags: - 
Meta Tags: Walkthrough, Walk-through, Write-up, Writeup
Subscription type: Premium
Description:
Understand how SOC analysts use the Elastic Stack (ELK) for log investigations.
```
## Task 1

### I am all set!

- Answer: `No answer needed`

## Task 2

### Logstash is used to visualize the data. (yay / nay)

- Logstash is used for parsing, normalizing and filtering data not to visualize the data. That is Kibana's job

- Answer: `nay`

### Elasticstash supports all data formats apart from JSON. (yay / nay)

- Elasticstash has full-text search and analytics engine for JSON-formatted documents

- Answer: `nay`

## Task 3

### Move to the next task!

- Answer: `No answer needed`

## Task 4

### Select the index vpn_connections and filter from 31st December 2021 to 2nd Feb 2022. How many hits are returned?

- We can set the date on the top right and see how many hits there are
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/a01d9957-4b1e-42b0-8147-3f3227f50bbf" />
</p>

- Answer: `2861`

### Which IP address has the maximum number of connections?

- Looking down at the field `Source_ip` and hovering over it, we can see the top IP address with the percentage at `3.2%`

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/264b621f-53fa-49bf-ac67-46ac1d58be3e" />
</p>

- Answer: `238.163.231.224`

### Which user is responsible for the overall maximum traffic?

- Similar to the previous question, if we look at the field `UserName`, we can see the top person with `4.0%` traffic

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/6624c8c8-180b-4b83-ad8a-215398cd5430" />
</p>

- Answer: `James`

### Apply Filter on UserName Emanda; which SourceIP has max hits?

- We can apply the filter by clicking on the `+` icon next to her name and we see the result of how many hits she has
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/320bd454-3767-4cfe-9885-7f49c703d236" />
</p>

- Then, I hovered over the `Source_ip` field to see which IP address has the max hits
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/b6420806-e8db-4816-a7dc-6108c8e38df8" />
</p>

- Answer: `107.14.1.247`

### On 11th Jan, which IP caused the spike observed in the time chart?

- I clicked on this big spike in the time interval area

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/63ba9f41-23d0-4b9a-8e63-b25da27bb5ea" />
</p>

- I hovered over the `Source_ip` field and we can see the top IP address with percentage at `98.9%`
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/a7d346a8-90e3-4aea-865e-4b57ceee883d" />
</p>

- Answer: `172.201.60.191`

- Also note that I did click on `January 10th` when I hovered over the green box but as you can see in the top right where the date range is, technically it is from `January 10th` at `12:00:00` to `January 11th` at `00:00:00` which I would assume to be 12 AM the next day. This was my assumption as there was no other spike on `January 11th` in the time interval (where the green boxes are)

### How many connections were observed from IP 238.163.231.224, excluding the New York state?

- Using the `+ Add filter` option, we can select the filters. The filters I selected were `Source_ip` is `238.163.231.224` and that the `source_state` is not `New York` giving us the amount of hits we needed

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/adbc20d8-f1b3-470d-8771-2f4d3104b951" />
</p>

- Answer: `48`

### Create a table with the fields IP, UserName, Source_Country and save.

- You can add the specific fields you want by hovering over the fields and clicking the blue `+` icon that appears which creates our table for us
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/d32581b6-913a-40e8-ae6d-42d89136bd27" />
</p>

- We can then click `Save` after filling out the information
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/0cdc5e20-d532-4b99-a813-4cf1ff6964c4" />
</p>

- Answer: `No answer needed`

## Task 5

### Create a search query to filter the logs where Source_Country is the United States and show logs from User James or Albert. How many records were returned?

- We can type a KQL query in the search bar to get the number of records back

<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/88670a9e-41d1-4025-94bb-0c0c2d42b7aa" />
</p>

### A user Johny Brown was terminated on the 1st of January, 2022. Create a search query to determine how many times a VPN connection was observed after his termination.

- This query was simple as we only had a single record for this person
<p align="center">
<img width="90%" height="90%" alt="image" src="https://github.com/user-attachments/assets/6dbe9634-8d3e-414d-84c2-40cf9845f70f" />
</p>

- Answer: `1`

## Task 6
## Task 7
