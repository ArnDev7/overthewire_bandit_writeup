# Bandit Writeup

---

### level 0
ssh bandit0@bandit.labs.overthewire.org -p 2220 

**-p is used to define port** 
 
*password is 'bandit0'*

---
   
### level 0->1

tried typing **readme** with commands given in the hint like
`ls, cd, cat, file`

password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

---

### level 1->2

read [this](https://linux-tips.com/t/dashed-filename-in-linux/188) on google and [this](.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal)

learnerd the use of **cat./-**

was stuck for a long time beacuse I forgot to enter **bandit1** after getting the previous password
also learned to *exit*

`cat ./-`


password: **rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi**


---

### level 2->3

ssh bandit2@bandit.labs.overthewire.org -p 2220

*entered previously found password*

got [this](https://linuxhandbook.com/filename-spaces-linux/) about spaces


`cat spaces\ in\ this\ filename`


password: **aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**

---

### level 3->4

ssh bandit3@bandit.labs.overthewire.org -p 2220

*entered previously found password*

 learning : ***cd utility shall change the working directory of the current
       shell execution environment***


  1. `ls`
  1. `cd inhere`
  1. `find`
  1. `cat .hidden`
      

learned that hidden files exist with a '.' and cd inhere was used to change the directory to inhere

password: **2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**

---

### level 4->5

ssh bandit4@bandit.labs.overthewire.org -p 2220

1. `ls -a `     (for not ignoring entries starting with '.')
1. `cd inhere` 
1. `file ./*`
1. `cat ./-file07`


*[reference](https://hackmethod.com/overthewire-bandit-5/?v=06fa567b72d7)*

password : **lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR**

---

### level 5->6

ssh bandit5@bandit.labs.overthewire.org -p 2220

1. `ls`
1. `d inhere`
1. `find`
1. `find -size 1033c`
1.  `cat ./maybehere07/.file2`


   password: **P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU**

   [Reference](https://man7.org/linux/man-pages/man1/find.1.html)

   ---

   ### level 6->7

   ssh bandit6@bandit.labs.overthewire.org -p 2220

   1. `find / -user bandit7 -group bandit6 -size 33c`
   2. `cat /var/lib/dpkg/info/bandit7.password`
  

   password: **z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**


*Had some help [here](https://kongwenbin.wordpress.com/2016/08/14/overthewire-bandit-level-6-to-level-7/) about using '/' in 'find' when password is hidden 'somewhere'*

---


### level 7->8

ssh bandit7@bandit.labs.overthewire.org -p 2220

 `grep "millionth" data.txt`
 password : **TESKZC0XvTetK0S9xNwm25STk5iWrBvP**


was stuck for a long time here due to some error in the terminal which wasnt displaying the password even after typing the correct code.

Found help here
![googled and found this](https://github.com/ArnDev7/overthewire_bandit_writeup/assets/148140634/31929a87-28e4-4a99-b40e-7b1d1ac927d8)

---

### level 8->9

ssh bandit8@bandit.labs.overthewire.org -p 2220

`ls`
 `cat data.txt | sort | uniq -u`
   

password : **EN632PlfYiZbn3PhVK3XOGSlNInNE00t**


it took too long to go through the helpful material given.

[this](https://ryanstutorials.net/linuxtutorial/piping.php) and [this](https://man7.org/linux/man-pages/man1/uniq.1.html) helped to solve.

#### *Learnings:*
*1. Piping (by using '|')
 2. sort
 3. to print unique lines using 'uniq'*

 ---


 ### level 9->10

 
 ssh bandit9@bandit.labs.overthewire.org -p 2220

`strings data.txt`
    *then a series of characters was displayed with the password in it*

    password: **G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s**

[reference](https://man7.org/linux/man-pages/man1/strings.1.html) 

---

### level 10->11

ssh bandit10@bandit.labs.overthewire.org -p 2220


 *forgot to put '-d' at first (which is used for decoding)*

`base64 -d data.txt`

      password: **6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**

      [Reference](https://man7.org/linux/man-pages/man1/base64.1.html)


---


### level 11->12

    
ssh bandit11@bandit.labs.overthewire.org -p 2220

   ` cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`


password: **JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv**

*(got stuck for a long time as I was using 'strings' instead of 'cat')*

Got help from [here](https://en.wikipedia.org/wiki/ROT13), [here](https://man7.org/linux/man-pages/man1/tr.1.html) and [here](https://mayadevbe.me/posts/overthewire/bandit/level12/)


---

### level 12->13

*was comparitively a very tough level, took a lot of time to get through. I had to read the manuals of various commands, had to do a lot of trial and error, got stuck at various steps too.*




ssh bandit12@bandit.labs.overthewire.org -p 2220

`mkdir /tmp/sick`          
\
`cp data.txt /tmp/sick`            *to copy the data file*
\
`cd /tmp/sick`                   *to set it to the current directory*
\
`ls`                            *to display files*
\
*data.txt*
\
`xxd -r data.txt > data`         *converting hex to binary*
\
Read this ![](https://github.com/ArnDev7/overthewire_bandit_writeup/assets/148140634/33feda7f-a836-4361-ae06-17afc20fa113)
\
`ls` 
<br>
*data*   *data.txt*
<br>
`file data`
<br>
*data: gzip compressed data, was "data2.bin"*
<br>
*found out that this is a gzip file, so, have to decompress it*
<br>

`mv data file.gz`
<br>
<br>
Had help [here](https://linuxize.com/post/gzip-command-in-linux/)
`gzip -d file.gz`  
<br>
`ls`
<br>
*data.txt*   *file*
`file file`
<br>
*file: bzip2 compressed data, block size = 900k*
<br>
`mv file file.bz2`
<br>
`bzip2 -d file.bz2`
<br>
`ls`
<br>
*data.txt  file*
<br>
<br>
`file file`
<br>
*file: gzip compressed data, was "data4.bin"* <br>
\

`mv file file.gz`
<br>
`gzip -d file.gz`
<br>
`ls`
<br>
*data.txt*  *file* <br>
\
`file file`
<br>
*file: POSIX tar archive (GNU)* <br>
\
`mv file file.tar`
<br>
`tar xf file.tar`
<br>
`ls`
<br> 
*data5.bin  data.txt  file.tar*
<br>

`file data5.bin`
<br>
*data5.bin: POSIX tar archive (GNU)*
<br>
`rm file.tar`
<br>
`rm data`
<br>
`rm data.txt`
<br>
`ls`
<br>
*data5.bin* <br>
<br>

`file file`
<br>
`file data5.bin`
<br>
data5.bin: POSIX tar archive (GNU)<br>
<br>

`mv data5.bin data.tar`
<br>
`tar xf data.tar`
<br>
`ls`
<br>
*data6.bin  data.tar*
<br>

`file data6.bin`
<br>
`mv data6.bin data.bz2`
<br>
`bzip2 -d  data.bz2`
<br>
`ls`
<br>
*data  data.tar*
<br>

`file data` <br>
*data: POSIX tar archive (GNU)*
<br>
`mv data data.tar`
<br>
`ls`
<br>
*data.tar*
<br>
`tar xf data.tar`
<br>
`ls`
<br>
*data8.bin  data.tar*
<br>
`file data8.bin`
<br>
<br>
*data8.bin: gzip compressed data, was "data9.bin"*
<br>
`mv data8.bin data.gz`
<br>
`gzip -d data.gz`
<br>
`ls`
<br>
<br>
*data  data.tar*
<br>
`file data`
<br>
*data: ASCII text*
<br>
`cat data`
<br>
<br>
<br>
***The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw***

[Reference 1](https://en.wikipedia.org/wiki/Hex_dump) <br>
[Reference 2](https://man7.org/linux/man-pages/man1/tar.1.html) <br>
[Reference 3](https://man7.org/linux/man-pages/man1/mv.1.html) <br>



---

### level 13->14

ssh bandit13@bandit.labs.overthewire.org -p 2220 

`ls`

<br>

ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

`ls`
<br>
`ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`
<br>
`cat /etc/bandit_pass/bandit14`
<br>

password: **fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq**

---

### level 14->15


`nc localhost 30000`
<br>

prev password: *fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq*

<br>

password obatined: **jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt**

---

### level 15->16

ssh bandit15@bandit.labs.overthewire.org -p 2220 

`man s_client`
<br>
`openssl s_client -connect  localhost:30001`
<br>
*I was stuck for very long here, as I did not know that i had to use '-connect' to connec to the local host*

*s_client is used as we were asked to use SSL encryption*
<br>
<br>
**Entered previous password**
<br>

password: **JQttfApK4SeyHwDlI9SXGR50qclOAil1**

---

### level 16->17

ssh bandit16@bandit.labs.overthewire.org -p 2220

`nmap -p 31000-32000 bandit.labs.overthewire.org`

Referred from[here](https://man7.org/linux/man-pages/man1/nmap.1.html)
<br>


`-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----`


I copied the RSA key and logged out. I logged in to bandit17 by using `ssh -i sshkey.private bandit17@localhost -p 2220`
<br>
`cat /etc/bandit_pass/bandit17`

password: **VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e**




[Reference 1](https://www.hackercoolmagazine.com/target-specification-in-nmap/)
<br>
[Reference 2](https://unix.stackexchange.com/questions/494788/omit-one-column-in-ls-hal)


---

### level 17->18

`ls`
<br>
`diff passwords.old passwords.new`
<br>

password: **hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg**

---

### level 18->19

ssh bandit18@bandit.labs.overthewire.org -p 2220

This immediately logs the host out.
I tried reading ssh manuals, and then put another command in front of the login commmand.

`ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme`  got the next level's password right away.
<br>

password: **awhqfNnAbc1naukrpqDYcF95h7HoMTrC**

---

### level 19->20

ssh bandit19@bandit.labs.overthewire.org -p 2220

`ls`
<br>
`file bandit20-do`
<br>

I set bandit20-do to the current directory and followed further as the question said..

`./bandit20-do cat /etc/bandit_pass/bandit20`
<br>

![Screenshot 2023-10-28 at 5 12 11 PM](https://github.com/ArnDev7/overthewire_bandit_writeup/assets/148140634/d3cf1e67-7ca1-4a2c-9c5f-3c09fba95c3a)


password: **VxCazJaVykI6W36BkBU0mJTCM8rR95XT**

---

### level 20->21

ssh bandit20@bandit.labs.overthewire.org -p 2220

`nc -lp 1212` set this up in the background and run
<br>
`./suconnect 1212` setting this at the bankground and bringing back to the foreground by using `fg` later.
<br>

can also use a second terminal to perform rather than using `bg` and `fg`

password: **NvEJF7oVjkddltPSrdKEFOllh9V1IBcq**


---

### level 21->22

ssh bandit21@bandit.labs.overthewire.org -p 2220

`cd /etc/cron.d`
<br>
`ls -l`
<br>
*the output was:*
`-rw-r--r-- 1 root root  62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r-- 1 root root  62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r-- 1 root root 120 Oct  5 06:19 cronjob_bandit22
-rw-r--r-- 1 root root 122 Oct  5 06:19 cronjob_bandit23
-rw-r--r-- 1 root root 120 Oct  5 06:19 cronjob_bandit24
-rw-r--r-- 1 root root  62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r-- 1 root root 201 Jan  8  2022 e2scrub_all
-rwx------ 1 root root  52 Oct  5 06:20 otw-tmp-dir
-rw-r--r-- 1 root root 396 Feb  2  2021 sysstat`
<br>
I started checking all of them one by one, then found the correct one by `cat cronjob_bandit22`
<br>
`cat bandit22 /usr/bin/cronjob_bandit22.sh`
<br>
*Output:*
<br>
`#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`
<br>
\
`cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`
<br>


password: **WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff**
<br>


Had help [here](https://serverfault.com/questions/162388/what-does-five-asterisks-in-a-cron-file-mean)

---

### level 22->23

ssh bandit22@bandit.labs.overthewire.org -p 2220

`cat /etc/cron.d/cronjob_bandit23`
\
`cat /usr/bin/cronjob_bandit23.sh`  (following the previous level's pattern)
<br>
it gave the output: 
<br>
![Screenshot 2023-10-31 at 12 11 08 AM](https://github.com/ArnDev7/overthewire_bandit_writeup/assets/148140634/5bfae7a8-94a0-40cc-9634-9be70e5698ac)

`myname=bandit23`
<br>
`echo I am user $myname | md5sum | cut -d ' ' -f 1`
output: `8ca319486bfbbc3663ea0fbe81326349` 
<br>
`cat /tmp/8ca319486bfbbc3663ea0fbe81326349`
<br>

password: **QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G**

***got stuck as I didnt change the username to 'bandit23', so it was echoing the wrong username therby giving the wrong key.***

---


### level 23->24
















       


