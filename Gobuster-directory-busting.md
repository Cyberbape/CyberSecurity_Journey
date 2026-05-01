# Gobuster - Directory Busting

## Date
01/05/2026

## Platform
TryHackMe

## What is Directory Busting?
A technique used to find hidden pages on a website that aren't 
linked anywhere. A tool tries thousands of common directory names 
and reports back which ones exist.

## Tool Used
Gobuster

## Command I Used
```bash
gobuster dir -u http://www.onlineshop.thm/ -w directory-list.txt
```

## Output
/login (Status: 200) [Size: 314]

## What the Output Means
- **/login** — a hidden page was found at this path
- **Status 200** — the server confirmed the page exists
- **Size 314** — the page is 314 bytes in size

## What I Found
A hidden login page at http://www.onlineshop.thm/login

## What I Learned
- How Gobuster works by trying wordlists against a target URL
- Status codes and what they mean (200 = exists, 404 = not found)
- How to filter out 404 results to keep output clean


