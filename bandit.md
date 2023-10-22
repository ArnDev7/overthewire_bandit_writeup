# Bandit Writeup

---

### `level 0`
ssh bandit0@bandit.labs.overthewire.org -p 2220 

**-p is used to define port**
 
*password is 'bandit0'*

---
   
### `level 0->1`

tried typing **readme** with commands given in the hint like
ls, cd, cat, file

password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

---

### `level 1->2`

read [this](https://linux-tips.com/t/dashed-filename-in-linux/188) on google and [this](.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal)

learnerd the use of **cat./-**

was stuck for a long time beacuse I forgot to enter **bandit1** after getting the previous password
also learned to *exit*

**cat ./-**


password: **rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi**


---

### `level 2->3`

ssh bandit2@bandit.labs.overthewire.org -p 2220

*entered previously found password*

got [this](https://linuxhandbook.com/filename-spaces-linux/) about spaces


![Screenshot 2023-10-19 at 2 57 16 AM](https://github.com/ArnDev7/overthewire_bandit_writeup/assets/148140634/eab70f4b-ac55-4dd0-bf7d-eab8477fda4e)


**cat spaces\ in\ this\ filename**


password: **aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**

---

### `level 3->4`

ssh bandit3@bandit.labs.overthewire.org -p 2220

*entered previously found password*

 learning : ***cd utility shall change the working directory of the current
       shell execution environment***


       ls
       cd inhere
       find  
       cat .hidden
      

learned that hidden files exist with a '.' and cd inhere was used to change the directory to inhere

password: **2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**

---

### `level 4->5`

ssh bandit4@bandit.labs.overthewire.org -p 2220

ls -a      (for not ignoring entries starting with '.')
cd inhere 
file ./*
cat ./-file07


*[reference](https://hackmethod.com/overthewire-bandit-5/?v=06fa567b72d7)*

password : **lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR**

---

### `level 5->6`

ssh bandit5@bandit.labs.overthewire.org -p 2220

1. ls
2. cd inhere
3. find
4. find -size 1033c
5. cat ./maybehere07/.file2


   password: **P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU**

   [Reference](https://man7.org/linux/man-pages/man1/find.1.html)

   ---

   ### `level 6->7`

   ssh bandit6@bandit.labs.overthewire.org -p 2220

   1. find / -user bandit7 -group bandit6 -size 33c
   2. cat /var/lib/dpkg/info/bandit7.password
  

   password: **z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**


*Had some help [here](https://kongwenbin.wordpress.com/2016/08/14/overthewire-bandit-level-6-to-level-7/) about using '/' in 'find' when password is hidden 'somewhere'*

---


### `level 7->8`

ssh bandit7@bandit.labs.overthewire.org -p 2220

1. grep "millionth" data.txt
2. password : **TESKZC0XvTetK0S9xNwm25STk5iWrBvP**


was stuck for a long time here due to some error in the terminal which wasnt displaying the password even after typing the correct code.

Found help here
![googled and found this](https://github.com/ArnDev7/overthewire_bandit_writeup/assets/148140634/31929a87-28e4-4a99-b40e-7b1d1ac927d8)

---

### `level 8->9`

ssh bandit8@bandit.labs.overthewire.org -p 2220

1. ls
2. cat data.txt | sort | uniq -u
   

password : **EN632PlfYiZbn3PhVK3XOGSlNInNE00t**


it took too long to go through the helpful material given.

[this](https://ryanstutorials.net/linuxtutorial/piping.php) and [this](https://man7.org/linux/man-pages/man1/uniq.1.html) helped to solve.

#### *Learnings:*
*1. Piping (by using '|')
 2. sort
 3. to print unique lines using 'uniq'*

 ---


 ### `level 9->10`

 
 ssh bandit9@bandit.labs.overthewire.org -p 2220

 1. strings data.txt
    *then a series of characters was displayed with the password in it*

    password: **G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s**

[reference](https://man7.org/linux/man-pages/man1/strings.1.html) 

---

### `level 10->11`

ssh bandit10@bandit.labs.overthewire.org -p 2220


 *forgot to put '-d' at first (which is used for decoding)*

   1. base64 -d data.txt

      password: **6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**

      [Reference](https://man7.org/linux/man-pages/man1/base64.1.html)


---


### `level 11->12`

    
ssh bandit11@bandit.labs.overthewire.org -p 2220

   1. cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'


password: **JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv**

*(got stuck for a long time as I was using 'strings' instead of 'cat')*

Got help from [here](https://en.wikipedia.org/wiki/ROT13), [here](https://man7.org/linux/man-pages/man1/tr.1.html) and [here](https://mayadevbe.me/posts/overthewire/bandit/level12/)


---















       


