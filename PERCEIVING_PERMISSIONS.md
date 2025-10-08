# PERCEIVING PERMISSIONS
---
## CHANGING FILE OWNERSHIP
**FLAG**
``pwn.college{4Q3mK1JHUSirAGgGyUAF0rveXfD.QXxEjN0wiN1AzNzEzW}``\
flag was obtained after changing owner of /flag from root to hacker
### my solve
```bash
hacker@permissions~changing-file-ownership:/$ chown hacker /flag
hacker@permissions~changing-file-ownership:/$ whoami
hacker@permissions~changing-file-ownership:/$ cat /flag
```
### learning
linux has owners for files which gives them priveleges to edit view or modify them\
we can change owners using ``chown`` command with following syntax:  
``chown ownername filename ``\
chown -- change owner
### resources -- none
---
## GROUPS AND FILES 
**FLAG** ``pwn.college{0xEu4f4jFsjP3HJb9rNHHci3HsX.QXxcjM1wiN1AzNzEzW}``\
flag was found after changing group of /flag to hacker from root
### my solve
```bash
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
```
### learning
we can change group of a particular file using ``chgrp`` command\
chgrp -- stands for change group\
changing group usually stands to give higher priveleges for certain files\
we can check current group detailes using ``id`` command

### resources -- none

---

## FUN WITH GROUP NAMES
**FLAG** ``pwn.college{EqQrNtjGso-P4ONJyaRt6_8rRtx.QXycjM1wiN1AzNzEzW}``\
flag was found after changing group after initially listing all present groups using id

### my solve
```bash
hacker@permissions~fun-with-groups-names:~$ id
hacker@permissions~fun-with-groups-names:~$ chgrp grp31910 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
```
### learning
- ``id`` is used to list out groups present
- we can change grps using grpid which is present in id
- syntax is ``chgrp grpid file``
### resources -- none

---

## CHANGING PERMISSIONS
**FLAG** ``pwn.college{Q2QanM_LKTP0ao40uT8YEQZZpW3.QXzcjM1wiN1AzNzEzW}``\
flag was found after changing mode of /flag from readble only to owner to readable to all ppl using ``chmod``
### my solve
```bash
hacker@permissions~changing-permissions:~$ chmod a+r /flag
hacker@permissions~changing-permissions:~$ ls / -l
hacker@permissions~changing-permissions:~$ cat /flag
```
### learning
`chmod` is used to change mode of files. it follows ``chmod who+what filename``
### resources -- none

## EXECUTABLE FILES
**FLAG** ``pwn.college{wSUi9SZ1rJiR9Ft-4nQD0_lqSGP.QXyEjN0wiN1AzNzEzW}``\
flag was found after making sure /challenge/run was executable by hacker by changing chaninging mode of it
### my solve
```bash
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
```
### learning
``chmod`` can be used to update modes even on commands and not only files.\
`r` is for read\
`w` is for write\
`x` is for executing
### resources -- none
---

## PERMISSION TWEAKING PRACTISE
**FLAG** ``pwn.college{Qlg13phlGH0swSQpTF9WwJYgMh5.QXwEjN0wiN1AzNzEzW}``\
flag was obtained after multiple `chmod` operations on /challenge/pwn3
### my solve
```bash
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
hacker@permissions~permission-tweaking-practice:~$ chmod g+w /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod a+x,g-x /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod a-r /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod u-x /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod g-w /challenge/pwn
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
```
### learning
learned how to change modes for mutiple users and files efficiently

### resources -- none
---
## PERMISSION SETTING PRACISES
**FLAG** ``pwn.college{QKglFYVmhaWtwks-OSVlbQ5Pn8U.QXzETO0wiN1AzNzEzW}``\
flag was obtained after tweaking multiple mode settings using `=` rather than `+-`
### learning
we can set file modes using = which erases all previously set modes.\
``chmod mode filename`` is the syntax
### resources -- none
---
## SUID BIT
**FLAG** ``pwn.college{cR4wDj_UQVwj1HNCP5BxnVb0sNQ.QXzEjN0wiN1AzNzEzW}``\
flag was found after catting for flag inside root shell.\
we enter root shell by changing suid of /challenge/getroot
### my solve
```bash
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
root@permissions~the-suid-bit:~# cat /flag
```
### learning
SUID stands for set user id and it gives root level access to a non root user on a file to file basis.
we can set it using `chmod` by adding +s parameter
### resources -- none
---

