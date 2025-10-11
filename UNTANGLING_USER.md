# UNTANGLING USERS
## BECOMING ROOT WITH SU
**FLAG** ``pwn.college{4e3rV7ZCdjJ8HV3t9ENAPwBumcb.QX1UDN1wiN1AzNzEzW}``
flag was obtained after catting `/flag` after becoming root
### my solve
```bash
hacker@users~becoming-root-with-su:~$ su
root@users~becoming-root-with-su:/home/hacker# cat /flag
```
### learning
- root has all access to a system
- we can become root by passing `su` command and giving pw
### resources -- none
---
## OTHER USERS WITH SU
**FLAG** ``pwn.college{odPSydZXkJiAvxBUJkS7FL4UW2K.QX2UDN1wiN1AzNzEzW}``
flag was obtained after running `/challenge/run` as zardus as root
### my solve
```bash
hacker@users~other-users-with-su:~$ su zardus
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
```
### learning
- we can make other users as root using `su username`
- default username is current login

### resources -- none
---
## CRACKING PASSWORDS
**FLAg** ``pwn.college{w7Zn9PwgPQ7sM9q0qkcr41AslLw.QX3UDN1wiN1AzNzEzW}``
flag was obtained after becoming root as zardus
### my solve
```bash
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
hacker@users~cracking-passwords:~$ su zardus
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
```
### learning
we can crack passwords using `john filename`\
helpful to decode hashes into common readable passwords
### resources -- none
---
## USING SUDO
**FLAG** ``pwn.college{8UL4WbZ_eVvsPbXfZf3-w2-WYjX.QX4UDN1wiN1AzNzEzW}``
flag was found after catting `/flag` as sudo
### my solve
```hacker@users~using-sudo:~$ sudo cat /flag```
### learning
- sudo stands for superuser do
- it runs commands as root instead of opening another shell with root privelege
- used in modern systems
### resources -- none
