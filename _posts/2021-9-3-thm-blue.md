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
  nmap -sV -vv --script vuln machine-ip<br>
</details>

<details>
<summary>How many ports are open with a port number under 1000?</summary>
  After you execute that above command you'll find __3__ open ports (under 1000)<br>
</details>

<details>
<summary>What is this machine vulnerable to? (Answer in the form of: ms??-???, ex: ms08-067)</summary>
  Under nmap results you will discover that it is vulnerable to two scripts.<br>
  But keeping eternal blue in mind we will go further with the one having SMB exploit (__ms17-010__).<br>
</details>

---

### Gain Access

<details>
<summary>Find the exploitation code we will run against the machine. What is the full path of the code? (Ex: exploit/........)</summary>  
  Start metasploit and search for ms17-010. You will get the full path of the exploit which is exploit/windows/smb/ms17_010_eternalblue<br>
</details>

<details>
<summary>Show options and set the one required value. What is the name of this value? (All caps for submission)</summary>
  After performing show options check for required field values (RHOSTS)<br>
</details>

---

### Escalate

<details>
<summary>If you haven't already, background the previously gained shell (CTRL + Z). Research online how to convert a shell to meterpreter shell in metasploit. What is the name of the post module we will use? (Exact path, similar to the exploit we previously selected)</summary>  
<br>post/multi/manage/shell_to_meterpreter
</details>

<details>
<summary>Select this (use MODULE_PATH). Show options, what option are we required to change?</summary>
<br>session
</details>

---

### Cracking

<details>
  <summary>Within our elevated meterpreter shell, run the command 'hashdump'. This will dump all of the passwords on the machine as long as we have the correct privileges to do so. What is the name of the non-default user?</summary>
  <br><img src="../images/thm-blue/getsys.png" alt="hashdump"><br>
  <br>Jon
</details>

<details>
  <summary>Copy this password hash to a file and research how to crack it. What is the cracked password?</summary>
  <br><img src="../images/thm-blue/crack.png" alt="crack-pwd"><br>
  <br>alqfna22
</details>

---

### Find flags!

<details>
  <summary>Flag1? This flag can be found at the system root.</summary>
  <br><img src="../images/thm-blue/flag1.png" alt="Flag 1"><br>
  <br>flag{access_the_machine}
</details>

<details>
  <summary>Flag2? This flag can be found at the location where passwords are stored within Windows.</summary><!--Storage path C:\Windows\System32\Config-->
  <br><img src="../images/thm-blue/flag2.png" alt="Flag 2"><br>
  <br>flag{sam_database_elevated_access}
</details>

<details>
  <summary>flag3? This flag can be found in an excellent location to loot. After all, Administrators usually have pretty interesting things saved.</summary>
  <br><img src="../images/thm-blue/flag3.png" alt="Flag 3"><br>
  <br>flag{admin_documents_can_be_valuable}
</details>

---

`You can connect me through the below platforms for my further updates`