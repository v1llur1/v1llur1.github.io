---
layout: post
title: THM Blue
tags: thm
---
In this writeup I will be solving [Blue.](https://tryhackme.com/room/blue)

### CTF Theme

The main objective of this room is to get access to the Windows machine which has multiple vulnerabilites.\
But this room is mainly focussed on ms17-010 exploit popularly known as eternal blue which deals with bug in SMB server of Windows machine.

---

### Recon

<details>
<summary>Scan the machine</summary>
nmap -sV -vv --script vuln machine-ip
</details>

<details>
<summary>How many ports are open with a port number under 1000?</summary>
After you execute that above command you'll find `3` open ports (under 1000)
</details>

<details>
<summary>What is this machine vulnerable to? (Answer in the form of: ms??-???, ex: ms08-067)</summary>
Under nmap results you will discover that it is vulnerable to two scripts.
  
But keeping eternal blue in mind we will go further with the one having SMB exploit (ms17-010).
</details>

---

###

```sh
$ You can connect me through the below platforms for my further updates
```
