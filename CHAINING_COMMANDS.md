# CHAINING COMMANDS
## CHAINING WITH SEMI COLONS
**FLAG** `pwn.college{c853Ad1skos5IZQVqWpSyL1llpZ.QX1UDO0wiN1AzNzEzW}`
flag was obtained after chaining 2 commands using ;
### my solve
bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college

### learning
- we can use ; to chain commands
- its essentially same as writing in different lines
- ; replaces the eol charater and allows for single line commands
### resources -- none
---
## BUILDING ON SUCCESS
**FLAG** `pwn.college{s9kiweWLmhekchhIjJIq0KnbVjU.0lM0MDOxwiN1AzNzEzW}`
flag was obtained after chaining 2 commands using &&.
### my solve
bash
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second

### learning
- && is used when u wanna chain commands but second should run only if the first is true/success
- what happens behind the scenes is that && essentially checks for exit code of the first command and if it returns 0 signifying proper execution, second one executes
### resources -- none
---
## HANDLING FAILURES
**fLAG** `pwn.college{UK3cwV2xw8UPbyAWc29li8olJEl.01M0MDOxwiN1AzNzEzW}`
flag was found after chaining 2 commands using ||
### my solve
bash
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second

### learning
- || is used when u wanna chain commands but second should run only if the first is false/failure
- what happens behind the scenes is that && essentially checks for exit code of the first command and if it returns non 0 signifying improper execution, second one executes
- || behaves like logical or and && behaves like and
### resources -- none
---
## YOUR FIRST SHELL SCRIPT
**FLAG** `pwn.college{cWHyv6Rm3uMNAa8l6MYkdN3I095.QXxcDO0wiN1AzNzEzW}`
flag was obtained after creating shell script called x.sh which had other commands inside of it and then running the script
### my solve
bash
hacker@chaining~your-first-shell-script:~$ touch x.sh
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh

### learning
- executable scripts in shell are called shell scripts and are by default saved by .sh extenstion
- u can write to them using text editors and they are called upon by bash filename.sh
- the execute the commands inside of them in the current shell
### resources -- none
---
## REDIRECTING SCRIPT OUTPUT
**FLAG** `pwn.college{EjAKvVx7-Qskfd3UwWaxV9E_Koa.QX4ETO0wiN1AzNzEzW}`
flag was obtained after piping output of x.sh into /challenge/solve
### my solve
bash
hacker@chaining~redirecting-script-output:~$ nano x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve

### learning
- when u have necessity to pipe output of multiple programs into a single program, the method is to combine all the programs inside of a shell script and then pipe the script into reqd program
### resources -- none
---
## EXECUTABLE SHELL SCRIPTS
**FLAG** `pwn.college{IVz0sbadQ5jpvzBSHGv5NeR-IeC.QX0cjM1wiN1AzNzEzW}`
flag was obtained after i ran /challenge/solve inside of a script and executed it without calling bash
### my solve
bash
hacker@chaining~executable-shell-scripts:~$ touch ab.sh
hacker@chaining~executable-shell-scripts:~$ nano ab.sh
hacker@chaining~executable-shell-scripts:~$ ls -l
hacker@chaining~executable-shell-scripts:~$ chmod u+x ab.sh
hacker@chaining~executable-shell-scripts:~$ ./ab.sh

### learning
- we can run a script without help of bash if following conditions are followes
- 1. it has execute permissions(change with chmod)
  2. run it with ./filename
### resources -- none
---
## UNDERSTANDING SHEBANGS
**FLAG** `` pwn.college{cBnaymRpV4G_vKWHtNX4wKbbjR5.0VOzMDOxwiN1AzNzEzW}``
flag was found after:
- make a solve.sh file
- initiate it with shebangs(#!)
- make it output `hack the planet`
- exit text editor and make the file executable
- run `/challenge/run`
### my solve
```bash
hacker@chaining~understanding-shebangs:~$ nano solve.sh
hacker@chaining~understanding-shebangs:~$ chmod a+x ~/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
```
### learning
when running commands, programs are unable to execute shell scripts and help of ceraint "intepretors" are needed\
shebangs are one of them. \
linux doesnt check for extensions, it rather checks the first few bites of the program to understand what it does.\
those lines are called shebangs\
for bash related programs, the shebang reqd are: `#!/bin/bash`
### resources -- none
---
## SCRIPTING WITH ARGUMENTS
**FLAG** ``pwn.college{QQDl_TN99XPEomDnZSnd0xtPaq5.0VNzMDOxwiN1AzNzEzW}``
flag was obtained after creating such a shell script such that it input 2 variables and output them in rev order
### my solve
```bash
hacker@chaining~scripting-with-arguments:~$ nano solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
```
### learning
we can use variables `$1` type to input values from user when running shell scripts
### resources -- none
---
## SCRIPTING WITH CONDITIONALS
**flag** ``pwn.college{0fOu-U2D-oALPAN26e1yfHJhdlU.0lNzMDOxwiN1AzNzEzW}``
flag was found after implementing such a shell script using conditional statements such that a input of pwn gave o/p as college and anything else did nothing
### my solve
```bash
hacker@chaining~scripting-with-conditionals:~$ nano solve.sh
#!/bin/bash
if [ "$1" == "pwn" ]
then 
	echo "college"
fi
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
```
### learning
- we can use conditionals commands like `if` in our shell scripts
- follows format
    ```bash
    if [ condition ]
    then
      dostuff
    fi
    ```
### resources -- none
---
## SCRIPTING WITH DEFAULT CASES
**FLAG** ``pwn.college{4nEEQN36gLi2C2TOsJMe03-FmUn.01NzMDOxwiN1AzNzEzW}``
flag was obtained after using if-else clause inside of shellscript
### my solve
```bash
hacker@chaining~scripting-with-default-cases:~$ nano solve.sh
        #!/bin/bash
        if [ "$1" == "pwn" ]
        then 
        	echo "college"
        else
        	echo "nope"
        fi
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
```
### learning
if else follows same syntax as plain if with the only difference that else DOES NOT NEED THEN
### resources -- none
---
## SCRIPTING WITH MULTIPLE CONDITIONALS
**FLAG** ``pwn.college{cHW6qnt4Hx7di91dnw7Ex9gvZSv.0FOzMDOxwiN1AzNzEzW}``
flag was found after building a shellscript with if-elif-else statements
### my solve
```bash
hacker@chaining~scripting-with-multiple-conditions:~$ nano solve.sh
      #!/bin/bash
      if [ "$1" == "pwn" ]
      then 
      	echo "college"
      elif [ "$1" == "hack" ]
      then 
      	echo "the planet"
      elif [ "$1" == "learn" ]
      then 
      	echo "linux"
      else
      	echo "unknown"
      fi
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
```
### learning
elif command is used when we need to check for multiple conditions\
it NEEDS A THEN just like if\
### resources -- none
---
## READING SHELL SCRIPTS
**FLAG** ``pwn.college{ofQ5DiC3aoQ0F6eoqZfwU2N0N6g.0lMwgDOxwiN1AzNzEzW}``
flag was found after first finding pw of a certain command after reading thru it
### my solve
```bash
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
```
### learning
- we can read thru code with `cat` function
- gives valuble info on the program written and the logic behind it
### resources -- none
