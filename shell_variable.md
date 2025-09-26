# SHELL VARIABLES

## PRINTING VARIABLES
**FLAG** pwn.college{k6equdYKAXEkOW2ZZ_FJPExlvts.QX3UTN0wiN1AzNzEzW}\
flag was obtained after echo'ing the FLAG variable into the shell
### my solve
```bash
hacker@variables~printing-variables:~$ echo $FLAG
```
### learning
echo prints whatever argument is passed into it to the shell.if we want to print variables using echo, its necessary to prepend it using $ sign
### resources -- none

## SETTING VARIABLES
**FLAG** pwn.college{gtCktXZnXPqGqyXaPVdDth1jJis.QX5UTN0wiN1AzNzEzW}\
flag was found after assigning value as COLLEGE to variable PWN
### my solve
```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
```
### learning
varibale assignment can be done by VARNAME=VALUEnote that no space btwn = signs. $ symbol is used only when variable expansion
### resources -- none

## MULTI WORD VARIABLES
**FLAG** pwn.college{86ip_vzcA9rUPGfFX14AQ_nbIFx.QXwYTN0wiN1AzNzEzW}\
FLAG was obtained after assigning value COLLEGE YEAH to variable PWN
### my solve 
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
```
### learning
to assign multi word value to a variable, its necessary to enclose value inside " " 
### resources -- none

## EXPORTING VARIABLES
**FLAG** pwn.college{IgpgJf-vGnn-2Y-DNodoMKE-WaP.QXyYTN0wiN1AzNzEzW}\
flag was obtained after running /challenge/run after exporting PWN variable and creating local variable COLLEGE
### my solve 
```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{IgpgJf-vGnn-2Y-DNodoMKE-WaP.QXyYTN0wiN1AzNzEzW}
```
### learning
export varname=var_value or #arname=value export #oth serves the same purpose of exporting the variable and its value to all the other child shells that may be accessed through the main bash shell
### resources -- none

## PRINTING EXPORTED VARIABLES
**FLAG** FLAG=pwn.college{URUaHyDSO96uA13KHPwblKORvJM.QX4UTN0wiN1AzNzEzW}\
flag was obtained after reading through values of all exported variables printed using help of env command
### my solve
```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=26dd0e52d8b5f0e29225d5fa172ff44aaea63a124194c5faff42e6e88eae479e
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{URUaHyDSO96uA13KHPwblKORvJM.QX4UTN0wiN1AzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-kitty
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```
### learning
exported variables can be printed by executing the env command
### resource -- none

## STORING COMMAND OUTPUT
**FLAG** pwn.college{kkPQnfAbpSzXQg2NflAyJbkoNCi.QX1cDN1wiN1AzNzEzW}\
flag was found after command substituting the value of /challenge/run into PWN and the printing variable PWN
### my solve
```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{kkPQnfAbpSzXQg2NflAyJbkoNCi.QX1cDN1wiN1AzNzEzW}
```
### learning
command substitution can be done by var_name=$(command)
### resources -- none

## READING INPUT
**FLAG** pwn.college{gZTSjUxOeawcV1nWIvzV94M6jGO.QX4cTN0wiN1AzNzEzW}\
flag was obtained after reading COLLEGE into variable named PWN using read command
### my solve
```bash
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{gZTSjUxOeawcV1nWIvzV94M6jGO.QX4cTN0wiN1AzNzEzW}
```
### learning
read command is used to read into a variable. argument -p is used to display prompt message and is optional
### resource -- none

## Reading files
**FLAG** pwn.college{Y0yLNnoChq2EZctT3VaOmoN4q5z.QXwIDO0wiN1AzNzEzW}\
flag was obtained by reading /challenge/read_me into the pwn variable
### my solve
```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Y0yLNnoChq2EZctT3VaOmoN4q5z.QXwIDO0wiN1AzNzEzW}
```
### learning
files can be read into variable in the following mannerread var_name < file_name
echo $var_name
### resources -- none
