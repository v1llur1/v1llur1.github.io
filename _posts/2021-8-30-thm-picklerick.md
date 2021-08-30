---
layout: post
title: THM Pickle Rick
tags: thm
---
In this writeup I will be solving the CTF of [Pickle Rick room](https://tryhackme.com/room/picklerick).

### CTF Theme

This Rick and Morty themed challenge requires you to exploit a webserver to find 3 ingredients a.k.a flags that will help Rick make his potion to transform himself back into a human from a pickle.

> ✔️ Deploy the virtual machine on this task and explore the web application.

---

<details>
<summary>What is the first ingredient Rick needs? </summary>
<br>

• After deploying and exploring the web application I found one **USERNAME** in the source code as **R1ckRul3s**
• Now, I have enumerated the pages and discovered several pages like **login,**  **robots**.
• In **/robots.txt** page I found one string **Wubbalubbadubdub**.
• I used the gathered info as login data at **/login.php**.
• Command panel was shown after successful login.
• After listing contents on the web server through command panel (as www-data), I found few interesting files. One of the file was **Sup3rs3cretPick13Ingred.txt**
• Finally, I found the first flag at **Sup3rs3cretPick13Ingred.txt** file which is `mr. meeseek hair`

</details>

---

<details>
<summary>What is the second ingredient Rick needs? </summary>
<br>

• I looked around other file paths for the second ingredient.
• After exploring I found two users on the machine **rick** and **ubuntu** at **/home** directory.
• I looked in rick's directory and discovered a file called **second ingredients**
• Commands like *cat*, *more* were not executing in the command panel. I have used *less* command to print out the contents of **second ingredients** file.
• I have executed ``` less '/home/rick/second ingredients' ``` and got the second flag `1 jerry tear`
</details>

---

<details>
<summary>What is the final ingredient Rick needs? </summary>
<br>

• Its time to get the third ingredient.
• After exploring I found two users on the machine **rick** and **ubuntu** at **/home** directory.
• I checked for sudo privileges

```
$ sudo -l
Matching Defaults entries for www-data on <my-machine-ip>:
  env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User www-data may run the following commands on <my-machine-ip>:
  (ALL) NOPASSWD: ALL
```
> ✔️ ROOT 😉

• I looked up for the files in **/root** directory and discovered a file called **3rd.txt**
• I have executed ```sudo less '/root/3rd.txt'``` and got the final flag `fleeb juice`
</details>
---
`You can connect me through the below platforms for my further updates`
