# DIGESTING DOCUMENTATION

## LEARNING FROM DOCUMENTATION
**FLAG:** `pwn.college{cRMIOL96eMWgHuRdI-EDiGM8MfO.QX0ITO0wiN1AzNzEzW}`  
Flag was found after passing the `--giveflag` argument to `/challenge/challenge`.

### My Solve
```bash
/challenge/challenge --giveflag
```

### Learning
Documentation serves as a guide on how to run programs. It lists all available arguments and other useful information about a program.

### Resources
None

---

## LEARNING COMPLEX USAGE
**FLAG:** `pwn.college{MRU-crhzjzfLUlxCoFN2XpVQbU3.QX1ITO0wiN1AzNzEzW}`  
Flag was found by passing the `--printfile` argument to `/challenge/challenge` and providing `/flag` as its input.

### My Solve
```bash
/challenge/challenge --printfile /flag
```

### Learning
Arguments can **themselves accept arguments**.  
For example, `--printfile` requires a file path. Similarly, the `find` command has arguments like `-name` which themselves take parameters such as the filename to search for.

### Resources
None

---

## READING MANUALS
**FLAG:** `pwn.college{IVtNtZLCCeweUZtOvSzJ1mpuv-G.QX0EDO0wiN1AzNzEzW}`  
Flag was found by passing the `--ttewet 100` argument to `/challenge/challenge` after reading the program’s **man page**.

### My Solve
```bash
/challenge/challenge --ttewet 100
```

### Learning
The `man` command opens the **manual page** for a command.  
Man pages include details like:
Command description  
Arguments and their usage  
Additional information

Manual files are stored locally, often in `/usr/bin/man` or similar directories.

### Resources
None

---

## SEARCHING MANUALS
**FLAG:** `pwn.college{ouwOvN69nYFvXVdPbjW0lkC35I0.QX1EDO0wiN1AzNzEzW}`  
Flag was found by **searching for the keyword "flag"** inside the man page and passing the correct argument.

### My Solve
```bash
/challenge/challenge --rmzy
```

### Learning
In `man` pages, press `/` followed by a term to **search**.
Use:
`n` to move to the next result  
`N` to move to the previous result  
Navigate using **arrow keys**.
Press `q` to **quit** the man page.

### Resources
None

---

## SEARCHING FOR MANUALS
**FLAG:** `pwn.college{AHsy48G1Zgb3PRXtIUcWD5rvBYN.QX2EDO0wiN1AzNzEzW}`  
The manual page for the `challenge` command was located using `man -k challenge`. By reading the man page for the alias command, the correct argument was obtained to retrieve the flag.

### My Solve
```bash
man man
man -k challenge
sygbtcrvwi (1)       - print the flag!
man sygbtcrvwi
/challenge/challenge --sygbtc 481
```

### Learning
The `man` command itself has a manual page. `man man` provides crucial information about options like `-k` and `-K` which help in searching manuals.

### Resources
None

---

## HELPFUL COMMANDS
**FLAG:** `pwn.college{wI17MqNEaCaTvcMJGVnVJlHdhwL.QX3IDO0wiN1AzNzEzW}`  
Using `--help` on `/challenge/challenge` provided the correct value to use with `-g` to obtain the flag.

### My Solve
```bash
/challenge/challenge --help
/challenge/challenge -p
The secret value is: 173
/challenge/challenge -g 173
```

### Learning
`man` might not always work. Many programs support `--help` or `-h` to display usage information and supported options.

### Resources
None

---

## HELP FOR BUILTINS
**FLAG:** `pwn.college{M97UP7L4QJbPd5rgDwhSF5551jd.QX0ETO0wiN1AzNzEzW}`  
Flag was found after using the `help` command to inspect the built-in `challenge` command and passing the retrieved secret value.

### My Solve
```bash
help challenge
challenge/challenge --secret M97UP7L4
bash: challenge/challenge: No such file or directory
challenge --secret M97UP7L4
```

### Learning
Certain commands are **builtins**, meaning they are part of the shell itself:
Use `help` to view documentation for builtins.
Unlike `man` or `--help`, builtins do not start a new process.
The syntax is simpler and direct, such as `help command_name`.

### Resources
None
