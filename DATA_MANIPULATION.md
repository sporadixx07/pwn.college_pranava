# DATA MANIPULATION

## TRANSLATING CHARACTERS
**FLAG** pwn.college{McJaGtzxVcEvQoEV6-CvJGWiBp0.01MxEzNxwiN1AzNzEzW}  
flag was found after case swapping all characters in the flag using `tr` operator

### my solve
```bash
hacker@data~translating-characters:~$ /challenge/run | tr abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
```

### learning
`tr` operator is used to change certain characters to other ones.

### resources
none


## DELETING CHARACTERS
**FLAG** pwn.college{EFzku7RuHO4NrHTFQL4l-SM4EaG.0FNxEzNxwiN1AzNzEzW}  
flag was found after removing `^` and `%` by using `tr` command with `-d` argument

### my solve
```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
```

### learning
the `-d` tag with `tr` corresponds to deleting

### resources
none


## DELETING NEWLINES
**FLAG** pwn.college{gib5qUhwV4uV1WUVipzcmDXQlkf.0VNxEzNxwiN1AzNzEzW}  
flag was found after removing several newline characters from original flag.  
`tr -d` was used along with `\n` which is the escape sequence for newlines

### my solve
```bash
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
```

### learning
`\n` is the newline character. it's an escape sequence.  
`tr -d` can also remove escape sequences.

### resources
none


## EXTRACTING FIRST LINES WITH HEAD
**FLAG** pwn.college{srwbZnWkr3rB5zCGVtO9YmQjdgk.0lNxEzNxwiN1AzNzEzW}  
flag was found after piping first 7 lines of `/challenge/pwn` to `/challenge/college` using `head`

### my solve
```bash
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
```

### learning
`head` is used to read first few lines of a file.  
Default value is 10 but can be modified with `-n` tag.

### resources
none


## EXTRACTING SPECIFIC SECTIONS OF TEXT
**FLAG** pwn.college{QSgtdAIpBLs_fptvoFEW8yBm3mW.01NxEzNxwiN1AzNzEzW}  
flag was found after piping the last column of `/challenge/run` into `tr` with argument as `-d "\n"`.  
last column was extracted using `cut -d " " -f2`.

### my solve
```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f2 | tr -d "\n"
```

### learning
`cut` command is used to cut certain portions of text out of a larger file.  
Column wise cutting can be done by passing argument `" "` to `-d`.

### resources
none


## SORTING DATA
**FLAG** pwn.college{gQz2QLUFcIWba7JoiwOn-dbaCNh.0FM0MDOxwiN1AzNzEzW}  
flag was found after heading the first line of `flags.txt` after sorting it in reverse order

### my solve
```bash
hacker@data~sorting-data:~$ sort -r /challenge/flags.txt | head -n 1
```

### learning
`sort` command is used to sort through text files.  
It accepts various arguments:  
- `-r` for reverse  
- `-n` for numeric  
- `-u` for unique  
- `-R` for random  

### resources
none
