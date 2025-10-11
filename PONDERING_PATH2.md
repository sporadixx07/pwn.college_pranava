# PONDERING PATH
## THE PATH VARIABLE
**FLAG** ``pwn.college{015-tzSbmlbywz1HFg6r_R-yrb5.QX2cDM1wiN1AzNzEzW}``
flag was obtained after running `/challenge/run` after removing the ability to rum `rm` command
### my solve
```bash
hacker@path~the-path-variable:~$ rm x.sh
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
```
### learning
-There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands
- we can stop a specific command from being run by just deleting the path variable for that
- just running `PATH=""` deletes the path and that command cant be used
### resources -- none
---
## SETTING PATH
**FLAG** `pwn.college{suFIDK6WGgEAkywwqxo6aUPoVv-.QX1cjM1wiN1AzNzEzW}`
flag was obtained after setting PATH=`/challenge/more_commands` so that win could be run wo invoking
### my solve
```bash
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ /challenge/run
```
### learning
- path variable is really helpful if we dont wanna enter the whole directory name when running commands
- the purpose of path is to preload that directory name to easen up calling process
### resources -- none
---
## FINDING COMMANDS
**FLAG** ``pwn.college{8iA2iieOOux_1hbWXwwdhnsYCfn.01NzEzNxwiN1AzNzEzW}``
flag was found after catting it from proper directory. directory was found using `which`
### my solve
```bash
hacker@path~finding-commands:~$ which win
hacker@path~finding-commands:~$ ls /challenge/paths/12819
hacker@path~finding-commands:~$ cat /challenge/paths/12819/flag
```
### learning
`which commandname` returns where PATH is reading that command from. ie basically which returns which direcotry the command is in.
### resources -- none
---
## ADDING COMMANDS
**FLAG** `` ``
flag was found after doing following steps
- which cat to find the path of cat
- open file called win and write a shebang into it
- make win executable
- change path to point to win
- run /challenge/run
### my solve
```bash
hacker@path~adding-commands:~$ which cat
/run/dojo/bin/cat
hacker@path~adding-commands:~$ nano win
      #!/bin/bash
      /run/dojo/bin/cat
hacker@path~adding-commands:~$ chmod a+x ~/win
hacker@path~adding-commands:~$ PATH="home/hacker/win"
hacker@path~adding-commands:~$ /challenge/run

```
### learning
learnt how to manipulate and run certain commands without help of builtin commands\
here we are catting a flag without actually using cat
### resources -- none
---

## HIJACKING COMMANDS
**FLAG** ````
flag was found after making a fake `rm` command inside of `/home/hacker` so that file doesnt get deleted
### my solve
```bash
hacker@path~hijacking-commands:~$ which cat
hacker@path~hijacking-commands:~$ nano rm
        #!/bin/bash
        /run/dojo/bin/cat
hacker@path~hijacking-commands:~$ chmod a+x rm
hacker@path~hijacking-commands:~$ PATH=/home/hacker
hacker@path~hijacking-commands:~$ /challenge/run
```
### learning
we can control which file executes first using PATH\
when two files of same name exists, the one on the current path executes first and we can modify that by chanhing value of path
### resources -- none







