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
<summary>What is the first ingredient Rick needs?</summary><br>
- After deploying and exploring the web application I found one <b>USERNAME</b> in the source code as <b>R1ckRul3s</b> <br>
- Now, I have enumerated the pages and discovered several pages like <b>login,</b>  <b>robots</b>.<br>
- In <b>/robots.txt</b> page I found one string <b>Wubbalubbadubdub</b>.<br>
- I used the gathered info as login data at <b>/login.php</b>.<br>
- Command panel was shown after successful login.<br>
- After listing contents on the web server through command panel (as www-data), I found few interesting files. One of the file was <b>Sup3rs3cretPick13Ingred.txt</b><br>
- Finally, I found the first flag at <b>Sup3rs3cretPick13Ingred.txt</b> file which is <code>mr. meeseek hair</code>
</details>

---

<details>
<summary>What is the second ingredient Rick needs?</summary><br>
- I looked around other file paths for the second ingredient.<br>
- After exploring I found two users on the machine <b>rick</b> and <b>ubuntu</b><br> at <b>/home</b> directory.<br>
- I looked in rick's directory and discovered a file called <b>second ingredients</b><br>
- Commands like <i>cat</i>, <i>more</i> were not executing in the command panel. I have used <i>less</i> command to print out the contents of <b>second ingredients</b> file.<br>
- I have executed <pre><b>less '/home/rick/second ingredients'</pre></b> and got the second flag <code>1 jerry tear</code>
</details>

---

<details>
<summary>What is the final ingredient Rick needs?</summary><br>
- Its time to get the third ingredient.<br>
- After exploring I found two users on the machine <b>rick</b> and <b>ubuntu</b><br> at <b>/home</b><br>
- I checked for sudo privileges 
<pre>$ sudo -l
Matching Defaults entries for www-data on &lt;my-machine-ip&gt;:
</t> env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin<br>
User www-data may run the following commands on &lt;my-machine-ip&gt;:
</t> (ALL) NOPASSWD: ALL
</pre>
ROOT 😉<br>
- I looked up for the files in <b>/root</b> directory and discovered a file called <b>3rd.txt</b><br>
- I have executed <pre><b>sudo less '/root/3rd.txt'</pre></b> and got the final flag <code>fleeb juice</code>
</details>

---

`You can connect me through the below platforms for my further updates`





