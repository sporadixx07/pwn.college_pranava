# COMPREHENDING COMMANDS

## CAT THE COMMAND
**FLAG:** `pwn.college{IE411NXCABBDvnSzhzf4nj79x7N.QXxcTN0wiN1AzNzEzW}`  
Flag was found after running the command `cat flag` from `/home/hacker` directory.

### My Solve
```bash
cat flag
```

### Learning
The `cat` command stands for **concatenate** and is used to **read and display files**. It can also accept multiple file names as arguments.

### Resources
None

---

## CATTING ABSOLUTE PATH
**FLAG:** `pwn.college{UL7-1ulTKK70dOfaqIg560Krog0.QX5ETO0wiN1AzNzEzW}`  
Flag was found after specifying the **absolute path** to the `cat` command.

### My Solve
```bash
/usr/bin/cat /flag
```

### Learning
The `cat` command accepts both **absolute** and **relative paths**.

### Resources
None

---

## MORE CATTING PRACTISE
**FLAG:** `pwn.college{oTFWLZ9E5WVouvt8qE2_rtmltap.QXwITO0wiN1AzNzEzW}`  
Flag was found after running:

```bash
cat /usr/share/lintian/flag
```

Since the `cd` command was banned, we had to specify the **absolute path** directly.

### Learning
Reading files without the help of `cd` by providing full file paths.

### Resources
None

---

## GREPPING FILES
**FLAG:** `pwn.college{UEweNVZuxqXE2QQvn_hBeawmwoP.QX3EDO0wiN1AzNzEzW}`  

### My Solve
```bash
grep 'pwn.college' /challenge/data.txt
```

### Learning
The `grep` command **searches for patterns** in files. It outputs all lines containing the specified string or regular expression.

### Resources
None

---

## COMPARING FILES
**FLAG:** `pwn.college{otFKO8jKrZlKC69YOB4C3T1JPQS.01MwMDOxwiN1AzNzEzW}`

### My Solve
```bash
diff /challenge/decoys_and_real.txt /challenge/decoys_only.txt
```

### Learning
The `diff` command is used to **find differences** between two files. It can detect differences in single words, lines, or entire files.

### Resources
None

---

## LISTING FILES
**FLAG:** `pwn.college{EGsxuqfmw7Xa96tR2GP9PURmvbb.QX4IDO0wiN1AzNzEzW}`

### My Solve
```bash
ls /challenge
/challenge/21555-renamed-run-433
```

### Learning
The `ls` command lists files in a directory. If no argument is provided, it defaults to the **current directory**.

### Resources
None

---

## TOUCHING FILES
**FLAG:** `pwn.college{otgeoKAFvFxH0MJc2-d51ZKCrk8.QXwMDO0wiN1AzNzEzW}`

### My Solve
```bash
cd /tmp
touch pwn
touch college
/challenge/run
```

### Learning
The `touch` command creates **empty files** or updates timestamps of existing files.

### Resources
None

---

## REMOVING FILES
**FLAG:** `pwn.college{46TvPg-wbq_-V1lc_H0RdXyUatc.QX2kDM1wiN1AzNzEzW}`

### My Solve
```bash
rm delete_me
/challenge/check
```

### Learning
The `rm` command is used to **delete files** permanently.

### Resources
None

---

## MOVING FILES
**FLAG:** `pwn.college{Yzwfcs0wTnkB9vMWyLVDya2pTlR.0VOxEzNxwiN1AzNzEzW}`

### My Solve
```bash
mv /flag /tmp/hack-the-planet
/challenge/check
```

### Learning
The `mv` command moves or renames files. Syntax: `mv source destination`

---

## HIDDEN FILES
**FLAG:** `pwn.college{QHC_v1CXfWPx4cYP91eW3Kx01pA.QXwUDO0wiN1AzNzEzW}`

### My Solve
```bash
ls / -a
cat /.flag-234472084923762
```

### Learning
The `-a` option with `ls` shows **hidden files** (those starting with `.`).

---

## AN EPIC FILESYSTEM QUEST
**FLAG:** `pwn.college{ozLFbDh3VUtkXSHzBSDRZlGHdD6.QX5IDO0wiN1AzNzEzW}`

This challenge involved navigating through tricky locations across the filesystem with different clue types: **hidden**, **trapped**, and **delayed** clues.

### Steps
**Find LEAD clue:**
    ```bash
    cd /
    cat LEAD
    ```
    Points to `/usr/local/lib/python3.8/dist-packages/pip/_vendor/resolvelib/compat`

**Delayed clue:**
    ```bash
    cd /usr/local/lib/python3.8/dist-packages/pip/_vendor/resolvelib/compat
    cat ALERT
    ```

**Trapped clue:**
    ```bash
    ls /usr/share/locale/crh/LC_MESSAGES
    cat /usr/share/locale/crh/LC_MESSAGES/TRACE-TRAPPED
    ```

**Hidden file:**
    ```bash
    ls /usr/share/icons/hicolor/72x72/emotes -a
    cat /usr/share/icons/hicolor/72x72/emotes/.TEASER
    ```

**Navigate to lib2to3:**
    ```bash
    cd /usr/lib/python3.9/lib2to3
    cat WHISPER
    ```

**Hidden pointer file:**
    ```bash
    ls /opt/linux/linux-5.4/include/config/oprofile/nmi -a
    cat /opt/linux/linux-5.4/include/config/oprofile/nmi/.POINTER
    ```

**Read dispatch file:**
    ```bash
    cat /usr/local/lib/python3.8/dist-packages/argon2/__pycache__/DISPATCH
    ```

**Trapped clue again:**
    ```bash
    cat /usr/local/lib/python3.8/dist-packages/pwnlib/shellcraft/templates/i386/DOSSIER-TRAPPED
    ```
 **Final clue:**
    ```bash
    cat /opt/linux/linux-5.4/tools/perf/pmu-events/arch/s390/cf_z14/MEMO
    ```

### Learning
`ls -a` is essential for finding **hidden files**.
 Trapped clues **must be read without `cd`**, or they disappear.
 Delayed clues only appear **after entering the directory**.
 **Case sensitivity matters** in Linux filenames.

### Resources
None

---

## MAKING DIRECTORIES
**FLAG:** `pwn.college{I1a7m8Mmr_4nxLXf2GwbyiCcMgF.QXxMDO0wiN1AzNzEzW}`

### My Solve
```bash
mkdir /tmp/pwn
touch /tmp/pwn/college
/challenge/run
```

### Learning
The `mkdir` command creates **new directories**.

### Resources
None

---

## FINDING FILES
**FLAG:** `pwn.college{UrVvkPKGaQLUqz1f7Xd7_u9FrTZ.QXyMDO0wiN1AzNzEzW}`

### My Solve
```bash
find / -name flag
cat /usr/lib/python3/dist-packages/sympy/physics/mechanics/tests/__pycache__/flag
```

### Learning
The `find` command searches through directories for files matching a given condition. It can be slow since it scans the entire directory tree.

### Resources
None

---

## LINKING FILES
**FLAG:** `pwn.college{IIunW7KZH5IVBnsw1jPw7cLaF74.QX5ETN1wiN1AzNzEzW}`

### My Solve
```bash
ln -s /flag ~/not-the-flag
/challenge/catflag
```

### Learning
Symbolic linking connects one file to another using:
```bash
ln -s original_file link_name
```
This tricked `/challenge/catflag` into reading the actual `/flag` file.

---
