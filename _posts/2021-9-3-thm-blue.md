---
layout: post
title: Blue [TryHackMe]
tags: thm
---
In this writeup I will be solving [Blue.](https://tryhackme.com/room/blue)

### CTF Theme

The main objective of this room is to get access to the Windows machine which has multiple vulnerabilites.\
But this room is mainly focussed on ms17-010 exploit popularly known as eternal blue which deals with bug in SMB server of Windows machine.

---

<details>
<summary>Recon</summary>

##### Scan the machine
  
nmap -sV -vv --script vuln machine-ip

##### How many ports are open with a port number under 1000?

After you execute that above command you'll find `3` open ports (under 1000)

##### What is this machine vulnerable to? (Answer in the form of: ms??-???, ex: ms08-067)

Under nmap results you will discover that it is vulnerable to two scripts.\
But keeping eternal blue in mind we will go further with the one having SMB exploit.\
`ms17-010`

</details>

---

`You can connect me through the below platforms for my further updates`
