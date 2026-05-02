# Hydra - Brute Force Attack

## Date
02/05/2026

## Platform
TryHackMe

## What is Hydra?
A password cracking tool that automatically tries thousands of 
username and password combinations against a login page until 
it finds the correct one. This is called a brute force attack.

## What is a Brute Force Attack?
When a tool repeatedly tries different passwords one by one 
until it finds the correct one that grants access.

## Tool Used
Hydra

## Command I Used
```bash
hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V
```

## Command Breakdown
- `-l admin` — the single username to try
- `-P passlist.txt` — a file containing a list of passwords to try
- `www.onlineshop.thm` — the target website
- `http-post-form` — tells Hydra the login uses a web form
- `/login` — the hidden page found using Gobuster
- `username=^USER^` — where Hydra inserts the username
- `password=^PASS^` — where Hydra inserts each password guess
- `F=incorrect` — if the page returns "incorrect", Hydra knows the attempt failed
- `-V` — shows every attempt in real time

## How This Connects to Gobuster
First I used Gobuster to find the hidden /login page.
Then I used Hydra to attempt to crack that login page.
This is the typical flow in penetration testing — 
enumerate first, then attack.

## What I Learned
- How Hydra works and what brute forcing means
- The difference between -l (single user) and -P (password list)
- How F= tells Hydra what a failed login looks like
- How web enumeration and brute forcing connect together

## Result
- 1 valid password was found and I was able to login.

## Next Steps
- Try different wordlists
- Learn about protecting against brute force attacks
