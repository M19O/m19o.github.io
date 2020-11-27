---
published: true
---
<img src="https://i.ibb.co/2tgV0yX/sneakymailer.png" alt="sneakymailer" border="0">

<h1>Recon</h1>
<h2>NMAP</h2>
<pre>roott@kali:~$ sudo nmap 10.10.10.197 -sV -sC -p- -A 
Starting Nmap 7.80 ( https://nmap.org ) at 2020-11-27 05:55 EST
Stats: 0:17:15 elapsed; 0 hosts completed (1 up), 1 undergoing Script Scan
NSE Timing: About 98.61% done; ETC: 06:12 (0:00:00 remaining)
Nmap scan report for sneakycorp.htb (10.10.10.197)
Host is up (0.98s latency).
Not shown: 65528 closed ports
PORT     STATE SERVICE    VERSION
21/tcp   open  ftp        vsftpd 3.0.3
22/tcp   open  ssh        OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 57:c9:00:35:36:56:e6:6f:f6:de:86:40:b2:ee:3e:fd (RSA)
|   256 d8:21:23:28:1d:b8:30:46:e2:67:2d:59:65:f0:0a:05 (ECDSA)
|_  256 5e:4f:23:4e:d4:90:8e:e9:5e:89:74:b3:19:0c:fc:1a (ED25519)
25/tcp   open  smtp       Postfix smtpd
|_smtp-commands: debian, PIPELINING, SIZE 10240000, VRFY, ETRN, STARTTLS, ENHANCEDSTATUSCODES, 8BITMIME, DSN, SMTPUTF8, CHUNKING, 
| ssl-cert: Subject: commonName=debian
| Subject Alternative Name: DNS:debian
| Not valid before: 2020-05-14T17:12:20
|_Not valid after:  2030-05-12T17:12:20
|_ssl-date: TLS randomness does not represent time
80/tcp   open  http       nginx 1.14.2
|_http-server-header: nginx/1.14.2
|_http-title: Employee - Dashboard
143/tcp  open  imap       Courier Imapd (released 2018)
|_imap-capabilities: STARTTLS THREAD=ORDEREDSUBJECT THREAD=REFERENCES QUOTA ACL CAPABILITY completed UTF8=ACCEPTA0001 IMAP4rev1 SORT ACL2=UNION NAMESPACE ENABLE CHILDREN UIDPLUS IDLE OK
| ssl-cert: Subject: commonName=localhost/organizationName=Courier Mail Server/stateOrProvinceName=NY/countryName=US
| Subject Alternative Name: email:postmaster@example.com
| Not valid before: 2020-05-14T17:14:21
|_Not valid after:  2021-05-14T17:14:21
|_ssl-date: TLS randomness does not represent time
993/tcp  open  ssl/imaps?
|_imap-capabilities: THREAD=ORDEREDSUBJECT THREAD=REFERENCES QUOTA ACL CAPABILITY completed UTF8=ACCEPTA0001 IMAP4rev1 AUTH=PLAIN SORT ACL2=UNION NAMESPACE ENABLE CHILDREN UIDPLUS IDLE OK
| ssl-cert: Subject: commonName=localhost/organizationName=Courier Mail Server/stateOrProvinceName=NY/countryName=US
| Subject Alternative Name: email:postmaster@example.com
| Not valid before: 2020-05-14T17:14:21
|_Not valid after:  2021-05-14T17:14:21
|_ssl-date: TLS randomness does not represent time
8080/tcp open  http       nginx 1.14.2
|_http-open-proxy: Proxy might be redirecting requests
|_http-server-header: nginx/1.14.2
|_http-title: Welcome to nginx!
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.80%E=4%D=11/27%OT=21%CT=1%CU=40029%PV=Y%DS=2%DC=T%G=Y%TM=5FC0DF
OS:4C%P=x86_64-pc-linux-gnu)SEQ(SP=102%GCD=1%ISR=108%TI=Z%CI=Z%II=I%TS=C)OP
OS:S(O1=M54BST11NW7%O2=M54BST11NW7%O3=M54BNNT11NW7%O4=M54BST11NW7%O5=M54BST
OS:11NW7%O6=M54BST11)WIN(W1=FE88%W2=FE88%W3=FE88%W4=FE88%W5=FE88%W6=FE88)EC
OS:N(R=Y%DF=Y%T=40%W=FAF0%O=M54BNNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=
OS:AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(
OS:R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%
OS:F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N
OS:%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%C
OS:D=S)

Network Distance: 2 hops
Service Info: Host:  debian; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 1025/tcp)
HOP RTT       ADDRESS
1   219.86 ms 10.10.16.1
2   136.11 ms sneakycorp.htb (10.10.10.197)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 1080.13 sec</pre>
<blockquote>
<p>That`s a big scan result.</p>
<p>At the end of the scan you can see the domain so we need to add it. add <code class="language-plaintext highlighter-rouge">sneakycorp.htb</code> to /etc/hosts file </p>
</blockquote>  

<h1>Port 80<h2>
<blockquote>  
<p>Let`s see what we can find.</p>
</blockquote>  
<img src="https://i.ibb.co/xjXWFGz/3.png" alt="3" border="0">   
<blockquote>
<p>It`s a pypi server</p>
<p>Let`s check team and see what we can find</p>
</blockquote>  
<img src="https://i.ibb.co/3BbXmVJ/4.png" alt="4" border="0">
<blockquote>  
<p>All e-mails of employees including <code class="language-plaintext highlighter-rouge">ceo</code> </p>
<p>Now we need to extract e-mails for the webpage, I used online email extractor tool.</p> 
<p><a href="https://email-checker.net/extract" target="_blank">https://email-checker.net/extract</a></p>
</blockquote> 

<blockquote>
<p>crtl+a to select all and copy them.</p>  
</blockquote>  
<img src="https://i.ibb.co/hZv0F0Z/5.png" alt="5" border="0">
<blockquote>Paste them and click on extract email</blockquote>  
<img src="https://i.ibb.co/bXdKgKg/6.png" alt="6" border="0">
<blockquote>Result</blockquote> 
<img src="https://i.ibb.co/RSBHtZX/7.png" alt="7" border="0">
  
<blockquote>  
<p>Now save it all in a fill name it <code class="language-plaintext highlighter-rouge">emails</code></p>
</blockquote>
<h1>Phishing<h1>
<blockquote>  
<p>We need to sned spoofed emails to check what we can get, I used swaks</p>
<p><a href="https://github.com/jetmore/swaks" target="_blank">https://github.com/jetmore/swaks</a></p>
</blockquote>  
<img src="https://i.ibb.co/87nhc6p/dlw2ty.png" alt="dlw2ty" border="0">

<h1>Phishing script<h1>

<pre>➜  sneakymailer swaks --from "angelicaramos@sneakymailer.htb" --body "Test msg" --to angelicaramos@sneakymailer.htb
=== Trying sneakymailer.htb:25...
=== Connected to sneakymailer.htb.
 -  220 debian ESMTP Postfix (Debian/GNU)
 -  EHLO m190
 -  250-debian
 -  250-PIPELINING
 -  250-SIZE 10240000
 -  250-VRFY
 -  250-ETRN
 -  250-STARTTLS
 -  250-ENHANCEDSTATUSCODES
 -  250-8BITMIME
 -  250-DSN
 -  250-SMTPUTF8
 -  250 CHUNKING
 - MAIL FROM: angelicaramos@sneakymailer.htb
 -  250 2.1.0 Ok
 - RCPT TO: angelicaramos@sneakymailer.htb
 -  250 2.1.5 Ok
 - DATA
 -  354 End data with CR LF.CR LF
 - Date: Wed, 15 Jul 2020 22:56:30 -0400
 - To: angelicaramos@sneakymailer.htb
 - From: angelicaramos@sneakymailer.htb
 - Subject: test Wed, 15 Jul 2020 22:56:30 -0400
 - Message-Id: 20200715225630.013546@m19o
 - X-Mailer: swaks v20190914.0 jetmore.org/john/code/swaks/
 - 
 - Test msg
 - 
 - 
 - .
 -  250 2.0.0 Ok: queued as F3049248C8
 - QUIT
 -  221 2.0.0 Bye
=== Connection closed with remote host.</pre>
 
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
