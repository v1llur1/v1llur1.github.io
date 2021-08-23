---
layout: post
title: THM Web Fundamentals
tags: thm
---
In this writeup I will be solving the mini CTF from [Web Fundamentals room](https://tryhackme.com/room/webfundamentals).

### Note To The Blog Readers

I hope you've completed the previous tasks. This writeup is only going to be about the mini CTF i.e., Task-5.\
Also, flags have been blurred because of THM's writeup policy. I hope you'll respect that.

Also, one more thing I wanna tell you people is that the flags have been blurred officially.\
But still you can find the flags from this blog. Favor from my side to you people !

### Mini CTF 

!! My machine IP from below may differ with yours.

There's a web server running on http://MACHINE_IP:8081. Connect to it and get the flags!

- GET request. Make a GET request to the web server with path /ctf/get
- POST request. Make a POST request with the body "flag_please" to /ctf/post
- Get a cookie. Make a GET request to /ctf/getcookie and check the cookie the server gives you
- Set a cookie. Set a cookie with name "flagpls" and value "flagpls" in your devtools (or with curl!) and make a GET request to /ctf/sendcookie

---

<details>
<summary>What's the GET flag?\
_HINT:You can perform a GET request with curl, or your web browser_</summary>
<br>
![Flag 1](images/thm-web-fundamentals/flag1.jpeg)
<!---
dGhtezE2MjUyMGJlYzkyNWJkNzk3OWU5YWU2NWE3MjVmOTlmfQ==
--->
</details>

---

<details>
<summary>What's the POST flag?\
_HINT:cURL is probably the easiest way to do this, use -X POST and --data < whatever you want to send >_</summary>
<br>
![Flag 2](images/thm-web-fundamentals/flag2.jpeg)
<!---
dGhtezM1MTdjOTAyZTIyZGVmOWM2ZTA5Yjk5YTkwNDBiYTA5fQ==
--->
</details>

---

<details>
<summary>What's the "Get a cookie" flag?\
_HINT:The web server will give you a cookie, check them in Firefox dev tools after viewing the page_</summary>
<br>
![Flag 3](images/thm-web-fundamentals/flag3.jpeg)
<!---
dGhtezkxYjFhYzI2MDZmMzZiOTM1ZjQ2NTU1ODIxM2Q3ZWJkfQ==
--->
</details>

---

<details>
<summary>What's the "Set a cookie" flag?\
_HINT:Using Firefox dev tools, you can add a cookie. The Name and value should both be "flagpls". If you set the cookie in Firefox, it will only apply in Firefox._</summary>
<br>
![Flag 4](images/thm-web-fundamentals/flag4.jpeg)
<!---
dGhte2MxMGI1Y2I3NTQ2ZjM1OWQxOWM3NDdkYjJkMGY0N2IzfQ==
--->
</details>

---

`You can connect me through the below platforms for my further updates`