---
published: true
---
<h1>Scanning</h1>

<img src="https://i.ibb.co/dbW2t85/Screenshot-from-2021-02-13-17-25-59.png" alt="Screenshot-from-2021-02-13-17-25-59" border="0"> 

<p>We found port 22 for ssh and port 8000,8080 for HTTP where port 8000</p>

<p>Let`s add jewel.htb in our hosts </p>

<img src="https://i.ibb.co/5v1Xjw8/Screenshot-from-2021-02-13-17-54-04.png" alt="Screenshot-from-2021-02-13-17-54-04" border="0">

<h2>Port 8000</h2>
<img src="https://i.ibb.co/kxyH5Kj/Screenshot-from-2021-02-13-18-01-04.png" alt="Screenshot-from-2021-02-13-18-01-04" border="0">

<h2>port 8080</h2>
<img src="https://i.ibb.co/37D1z6D/Screenshot-from-2021-02-13-18-01-35.png" alt="Screenshot-from-2021-02-13-18-01-35" border="0">

<p>Let`s enumerate the BLOG!</p>
<img src="https://i.ibb.co/FmT1Ppz/Bill.png" alt="Bill" border="0">
<img src="https://i.ibb.co/s9vmvfL/Jennifer.png" alt="Jennifer" border="0">
<p>We found 2 user Bill,Jennifer </p>

<p>Let`s enumerate the REPO </p>
<img src="https://i.ibb.co/0fNWrZK/Screenshot-from-2021-02-13-18-15-14.png" alt="Screenshot-from-2021-02-13-18-15-14" border="0">

<p>After some enumerating i found SQL file "bd.sql" and i got some hashes</p>
<img src="https://i.ibb.co/3swY3Lz/PASSWORD.png" alt="PASSWORD" border="0">

<p>I could break Bill hash "spongebob" but couldn`t login, let`s countinue enumeration</p>
<img src="https://i.ibb.co/JKpyJ9q/Screenshot-from-2021-02-13-18-27-25.png" alt="Screenshot-from-2021-02-13-18-27-25" border="0">
<p>It`s using ruby '2.5.5' , let`s search for an exploit</p>
<p>I found a CVE</p><a href="https://github.com/masahiro331/CVE-2020-8165">CVE-2020-8165</a> 
