
# PRACTISING PIPING

## REDIRECTING OUTPUT
**FLAG** pwn.college{gDeBKWZEq34tgh9vdHEm8pvoffq.QX0YTN0wiN1AzNzEzW}\
flag was found after redirecting output of echo PWN to file called college

### my solve
```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
```

### learning
we can redirect output of commands to files using '>' operator

### resrources -- none

## REDIRECTING MORE OUTPUT
**FLAG** pwn.college{MjTL1tX7TjYB3lmoaHvPZ33KpgG.QX1YTN0wiN1AzNzEzW}\
flag was found after redirecting output of /challenge/run to myflag and then catting myflag

### my solve
```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
hacker@piping~redirecting-more-output:~$ cat myflag
```

### learning
we can use other commands also apart from echo to redirect outputs. the > is the key to redirecting outputs. any command which gives an output can be redirected

### resources -- none

## APPENDING OUTPUTS
**Flag** pwn.college{wmbMOXfleNKCJvCnRulhkTayt4I.QX3ATO0wiN1AzNzEzW}\
flag was found after catting the-flag file after appending /challenge/run to it using >> operator

### my solve
```bash
hacker@piping~appending-output:~$ /challenge/run >> ~/the-flag
hacker@piping~appending-output:~$ cat the-flag
```

### learning
 the >> is used to append to a file whereas > is used to write to a file. > overwrites existing content

### resources -- none

## REDIRECTING ERRORS
**FLAG** [FLAG] pwn.college{UduEIMRIfGWy7HlW-B1bzNG5srD.QX3YTN0wiN1AzNzEzW}\
flag was found after redirecting output of /challenge/run to myflag and the errors (denoted by FD - 2) to instructions. then flag was obtained after catting myflag

### my solve
```bash
hacker@piping~redirecting-errors~$ /challenge/run >myflag 2>instructions
hacker@piping~redirecting-errors:~$ cat myflag
```

### learning
there are certain FD nos. 1 for stdout. 2 for std error. 0 for stdin
we can assign what needs to be redirected using FDs. implicitely, 1 is the default FD.
FD stands for file descriptors
also multpiple outputs can be redirected to multiple seprate files using proper FD nos along with > operand

### resources -- none

## REDIRECTING INPUTS
**FLAG** pwn.college{AyeBYbc8Vrp6_WZ-f1fAb8MTopH.QXwcTN0wiN1AzNzEzW}\
flag was found after redirecting input of /challenge/run to PWN which already had COLLEGE redirected into it.

### my solve
```bash
hacker@piping~redirecting-input:~$ echo COLLEGE>PWN
hacker@piping~redirecting-input:~$ /challenge/run<PWN
```

### learning
to redirect stdout we use '>'
for stdin we use '<'

### resources -- none

## GREPPING STORED RESULTS
**FLAG** pwn.college{YOC1KSI9GoS9aLQBL5PaTJmczJ4.QX4EDO0wiN1AzNzEzW}\
flag was found after grepping for 'pwn.college' in data.txt file after redirecting /challenge/run 's output to data.txt

### my solve
```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep "pwn.college" /tmp/data.txt
```

### learning
we can use grep to find for similarities in a particular file after redirecting its stdout to a dif file.
i made a mistake of echoing /challenge/run to a txt file which resulted in unintended output,
what i meant to do was write contents of /challenge/run to txt file 

### resources -- none

## GREPPING LIVE OUTPUT
**FLAG** pwn.college{g1rz9s9Y1mQ84GSX8_UFs5Wq-be.QX5EDO0wiN1AzNzEzW}\
flag was obtained after PIPING output of /challenge/run to grep and then grepping for the file

### my solve
```bash
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
```

### learning
commands' effieciency can be improved by using piping operator to write single line commands
| is the piping operator and allows for other programs to access a different program's output as its input

### resources -- none

## GREPPING ERRORS
**FLAG** pwn.college{UjHPGVKdXcWpYzZ0_nBcfeam8Iq.QX1ATO0wiN1AzNzEzW}\
flag was found after grepping thru stderr of /challenge/run after first assigning FD 2 as FD 1 using >& operator

### my solve
```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep "pwn.college"
```

### learning
the | operator can take only stdout. not stdin or stderr
the >& operator is used to redirect stderr as stdout
then grepping thru stderr is easily achieved after combining both of them on the same command/
i assumed that >& is a permanent change and tried doing the challenge by breaking them into 2 sep commands which failed to work

### resrources -- none

## FILTERING WITH GREP-v
**FLAG** pwn.college{UXjoYBd3-ftVViNUPuWM1k-ZW6q.0FOxEzNxwiN1AzNzEzW}\
flag was found after grepping through /challenge/run (after piping it) looking for lines without the word DECOY

### my solve
```bash
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
```

### learning
the argument -v when passed to GREP will return o/p as lines which donot contain the argument/
basically it inverts the grep function

### resources-- none

## DUPLICATING PIPED DATA WITH tee
**FLAG** pwn.college{kmNPFzcETARoaAzX6j2kOjfjcL5.QXxITO0wiN1AzNzEzW}\
flag was obtained after doing multiple steps
1. /challenge/pwn was piped into /challenge/college with it also teeing into a sep file
2. the teed file was read which lead to secret code
3. then /challenge/pwn was again piped into /challenge/college but this time with /pwn having required argument

### my solve
```bash
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee /tmp/intercept.txt | /challenge/college
hacker@piping~duplicating-piped-data-with-tee:~$ cat /tmp/intercept.txt
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret kmNPFzcE | /challenge/college
```

### learning
tee command is used to be a man in the middle and read through the processes happening behind the scenes for a given command

### resources -- none

## PROCESS SUBSTITUTION FOR INPUT
**FLAG** pwn.college{4BqNH6gzz_GeF2a2qvTnNor2KXu.0lNwMDOxwiN1AzNzEzW}\
flag was found after process substituion with diff to compare two programs 

### my solve
```bash
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
```

### learning
process substitution can be done by giving command name followed with (command)
process substitution makes a commands output appear as files with <(command)

### resources -- none

## WRITING TO MULTIPLE PROGRAMS
**FLAG** pwn.college{UpZQ_mN2RtZMqM9-sSJgRcjve2z.QXwgDN1wiN1AzNzEzW}\
flag was obtained after process substituting /challenge/hacks output into input for /challenge/the and piping into /challenge/planet using tee 

### my solve
```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >( /challenge/the ) | /challenge/planet
```

### learning
process substitution and teeing can be used in combo to write to multiple programs at once

### resources -- none

## SPLIT PIPING STDERR AND STDOUT
**FLAG** pwn.college{EZ5mUGcmueKhjBIdlwKFXIKfRhL.QXxQDM2wiN1AzNzEzW}\
flag was found after piping stdout of /challenge/hack into /challenge/planet whereas redirecting stderr to /challenge/the using process substitution

### my solve
```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >( /challenge/the ) | /challenge/planet
```

### learning
the whole of 'man bash'/
well understood on a deep level how process substitution works,
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/planet < /challenge/hack | 2>(/challenge/the)
was my first attempt at the challenge
few key takeaways
1. the > operand after | is logically incorrect and i spent helluva lot time on understanding why. the reason is | followed by <( creates a /dev type file which is not what i was looking to acheieve
2. the 2 must've been attached to command which was gonna produces the stderr. although that woudnt have worked here

### resources -- manual pages of bash(/process substitution )

## NAMED PIPES
**FLAG** pwn.college{EAUn5wKDQXXrLdPJjU8aqXHVeb3.01MzMDOxwiN1AzNzEzW}\
flag was found after fifo'ing /challenge/run contents into a named pipe and then catting it

### my solve
```bash
mkfifo /tmp/flag_fifo
cat /tmp/flag_fifo &
/challenge/run > /tmp/flag_fifo
```

### learning
named pipes can be created using mkfifo command
fifo stands for first in first out
has many advantages but only disadvantage is both sides of pipe must be in use for proper fucntioning
ie if echo is used, cat must be also be in use for proper functioning of the command

### resources -- none
