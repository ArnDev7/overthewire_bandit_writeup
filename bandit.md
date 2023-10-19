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

[read this on google](https://linux-tips.com/t/dashed-filename-in-linux/188) and [this](.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal)

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


       


