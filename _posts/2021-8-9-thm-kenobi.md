---
layout: post
title: THM Kenobi
tags: thm
---

In this writeup I will be solving Kenobi.

### CTF Theme

The main objective of this room is to first find enumerate the SMB shares, manipulating ProFtpd server and escalating privileges through SUID binary.

### Enumerate

Run nmap scan

---

```sh
root@v1llur1 :~ # nmap ip -vvv
PORT     STATE SERVICE     
21/tcp   open  ftp         
22/tcp   open  ssh         
80/tcp   open  http        
111/tcp  open  rpcbind     
139/tcp  open  netbios-ssn 
445/tcp  open  netbios-ssn 
2049/tcp open  nfs_acl     
```

<details>
<summary>How many ports are open</summary>  
  7<br>
</details>

---

Enumerating SMB ports

```sh
root@v1llur1 :~ # nmap -p 445 —script=smb-enum-shares.nse,smb-enum-users.nse <ip>
```
<details>
<summary>Using the nmap command above, how many shares have been found?</summary>  
  3<br>
</details>

---

Access the shares.

```sh
root@v1llur1 :~ # smbclient //<ip>/anonymous
```

<details>
<summary>Once you're connected, list the files on the share. What is the file can you see?</summary>  
  I found that one file called log.txt <br>
</details>

---

Go through the **log.txt** file.

<details>
<summary>What port is FTP running on?</summary>  
  21<br>
</details>

---

Enumerate RPC

```sh
# nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount IP
```

<details>
<summary>What mount can we see?</summary>  
  /var<br>
</details>

---

### Gaining Access

```sh
# nc IP 21
```

<details>
<summary>What is the version?</summary>  
  1.3.5<br>
</details>

---

```sh
# searchsploit proftpd version
```

<details>
<summary>How many exploits are there for the ProFTPd running?</summary>  
  4<br>
</details>

---

```sh
kenobi@kenobi :~ $ cat flag.txt
d0b0f3f53b6caa532a83915e19224899
```

<details>
<summary>What is Kenobi's user flag (/home/kenobi/user.txt)?</summary>  
  d0b0f3f53b6caa532a83915e19224899<br>
</details>

---

Escalation

Find SUID files

```sh
kenobi@kenobi :~ $ find / -perm -u=s -type f 2>/dev/null
```

<details>
<summary>What file looks particularly out of the ordinary? </summary>  
  /usr/bin/menu<br>
</details>

---

```sh
kenobi@kenobi :~ $ /usr/bin/menu
```

<details>
<summary>Run the binary, how many options appear?</summary>  
  3<br>
</details>

---

```sh
# cat /root/root.txt
177b3cd8562289f37382721c28381f02
```

<details>
<summary>What is the root flag (/root/root.txt)?</summary>  
  177b3cd8562289f37382721c28381f02<br>
</details>

---

`You can connect me through the below platforms for my further updates`
