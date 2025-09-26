# FILE GLOBBING

## MATCHING WITH *
**FLAG:** `pwn.college{EDjqNCIvaJ-APjrBTC7mHWUYOoZ.QXxIDO0wiN1AzNzEzW}`  
Flag was found after cd'ing into /challenge dir with the help of `*`. Then by running `/challenge/run`, flag was obtained.

### My Solve
```bash
hacker@globbing~matching-with-:~$ cd /c*e
hacker@globbing~matching-with-:/challenge$ /challenge/run
```

### Learning
The `*` is used to match files in a directory and is replaced by files which match the criteria. It's basically treated as a wildcard. 

### Resources
None

---

## MATCHING WITH ?
**FLAG:** `pwn.college{EgG1RGu3PIYxgylTHWpLlEYPEph.QXyIDO0wiN1AzNzEzW}`  
Flag was obtained after cd'ing into `challenge` dir with `c` and `l` replaced with `?`.

### My Solve
```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
```

### Learning
The `?` acts same as the `*` but only for single characters.

### Resources
None

---

## MATCHING WITH []
**FLAG:** `pwn.college{0wTHVsnGq5Znzmx2dcTu9ZXI7qZ.QXzIDO0wiN1AzNzEzW}`  
Flag was found after running `/challenge/run` with files named file_a, file_b, file_s, file_h using file globbing with `[]`.

### My Solve
```bash
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
```

### Learning
`[]` does the same work as `?`, that is matches a single character but only searches for those characters provided inside the square brackets.

### Resources
None

---

## MATCHING PATH WITH []
**FLAG:** `pwn.college{Ych-nKGAsq3I33YYf2uCZzeLrEs.QX0IDO0wiN1AzNzEzW}`  
Flag was found after globbing the files directly to `/challenge/run` using the absolute path.

### My Solve
```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
```

### Learning
File globbing using `[]` can be applied on both relative and absolute paths.

### Resources
None

---

## MULTIPLE GLOBS
**FLAG:** `pwn.college{ML-xDCK8DWvmU_6XhFP6QNCe8tV.0lM3kjNxwiN1AzNzEzW}`  
Flag was found after writing a statement using globbing concepts to run `/challenge/run` with all files having `p` in them.

### My Solve
```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
```

### Learning
In globbing, `*` takes all values including nothing. i.e. `*p*` can match `ap`, `bp`, `cp` or just `p` as well.

### Resources
None

---

## MIXING GLOBS
**FLAG:** `pwn.college{k_YI6OzhKBaH-iOODxB6tfaOTyY.QX1IDO0wiN1AzNzEzW}`  
Flag was found after creating a command that within 6 characters, using globbing methods, matches words like `challenging`, `educational`, and `pwning`. This was achieved by combining `*` and `[]` methods.

### My Solve
```bash
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run_[pec]*
```

### Learning
Combination of globbing can be utilised to shorten our input length and optimise the command. With proper combination of `*` and `[]` we can cover all files in a directory.

### Resources
None

---

## EXCLUSIONARY GLOBBING
**FLAG:** `pwn.college{AEshUl_7vF7YSDRqrQT4hbzPWWm.QX2IDO0wiN1AzNzEzW}`  
Flag was obtained after running the command to run all files that don't start with `p`, `w`, or `n`. This was achieved through exclusionary globbing using `^` and continuing condition with `*`.

### My Solve
```bash
/files@globbing~exclusionary-globbing:~$ cd /challenge
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
```

### Learning
`!` or `^` can be used as exclusionary globbing clauses.  
`!` can lead to logical issues if not used at first position of glob.  
`^` can throw syntax error on older bash versions.

### Resources
None

---

## TAB COMPLETION
**FLAG:** `pwn.college{YKgmUS4n8czaAxvwzWkmJJq92SJ.0FN0EzNxwiN1AzNzEzW}`  
Flag was obtained after catting the `pwncollege` file but using tab to autocomplete the file name.

### My Solve
```bash
hacker@globbing~tab-completion:~$ cd /challenge
hacker@globbing~tab-completion:/challenge$ ls
DESCRIPTION.md  pwncollege
hacker@globbing~tab-completion:/challenge$ cat pwncollege
pwn.college{YKgmUS4n8czaAxvwzWkmJJq92SJ.0FN0EzNxwiN1AzNzEzW}
```

### Learning
Tabbing to autocomplete is a useful feature and far safer than using globbing methods.

### Resources
None

---

## MULTIPLE OPTIONS TAB COMPLETION
**FLAG:** `pwn.college{Iw29hKT7u_Gderx7O9J-TfNrBLl.0lN0EzNxwiN1AzNzEzW}`  
Flag was found after catting `pwncollege-flag`. The file was selected after tabbing into `/challenge/files` and typing `pwn`.

### My Solve
```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge/files
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwn
pwn                    pwncollege-flag
pwn-college            pwncollege-flamingo
pwn-the-planet         pwncollege-flyswatter
pwncollege-family      pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwncollege-flag
```

### My Learning
When multiple file names can fit the current autocomplete criteria, tabbing displays all possible options.

### Resources
None

---

## TAB COMPLETION FOR COMMANDS
**FLAG:** `pwn.college{A9NeRkO8bUd32y6Zr4yuBoZ9wdx.0VN0EzNxwiN1AzNzEzW}`  
Tab completion can be used to complete commands as well. Flag was found after tab completing the `pwncollege` command.

### My Solve
```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-26036
```

### Learning
Tab completion can be used for both commands and file names. Be careful though because sometimes it may trigger unintended commands.

### Resources
None
