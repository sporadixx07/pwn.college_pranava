# TERMINAL MULTIPLEXING

---

## Launching screen
**FLAG:**  
`pwn.college{Eyg_ug_u0vkpglltnymq1T7ysJ5.0VN4IDOxwiN1AzNzEzW}`

Flag found after opening another virtual terminal (screen) inside the main terminal.

**Solve**
```bash
hacker@terminal-multiplexing~launching-screen:~$ screen
```

**Learning**  
The `screen` command opens a virtual terminal inside your current terminal. It behaves like a separate session and can be exited by running `exit` inside it.\
**Resources:** None

---

##  Detaching and Attaching (screen)
**FLAG:**  
`pwn.college{shNSJQCIhq6l-MTFQc_3HlLOOH7.0lN4IDOxwiN1AzNzEzW}`

Flag found after detaching a `screen` session and reattaching it after running a command in the main terminal.

**Solve**
```bash
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
# detach the session:
# press Ctrl-a then d (written here as: ctrl a + d)
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
# reattach:
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
```

**Learning**  
- Use `Ctrl-a d` to detach a `screen` session.  
- Use `screen -r` to reattach a detached session. Sessions persist while detached.

**Resources:** None

---

##  Finding Sessions
**FLAG:**  
`pwn.college{cAL3_vn2T5AQP9zrMmm51Csc-Zm.01N4IDOxwiN1AzNzEzW}`

Flag found by reattaching to a specific detached session.

**Solve**
```bash
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 150.session_6dba0ba05b7cf482
```

**Learning**  
- `screen -ls` lists all current attached/detached sessions.  
- `screen -r <session-id>` reconnects to a specified detached session.

**Resources:** None

---

##  Switching Windows (screen)
**FLAG:**  
`pwn.college{c4uPdOwXpu1dpURam7Z5lC6hxjd.0FO4IDOxwiN1AzNzEzW}`

Flag found after switching between multiple windows inside `screen` (using Ctrl-a + window number).

**Learning**  
Useful `screen` controls:  
- `Ctrl-a c` — create a new window  
- `Ctrl-a n` — next window  
- `Ctrl-a p` — previous window  
- `Ctrl-a 0..9` — jump to numbered windows

**Resources:** None

---

##  Detaching and Attaching (tmux)
**FLAG:**  
`pwn.college{YRxHxvZRurBc7k0_3wrvO0cbQRG.0VO4IDOxwiN1AzNzEzW}`

Flag found after opening `tmux`, detaching, running `/challenge/run` in the main terminal, and then reconnecting.

** Solve**
```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
# detach:
# press Ctrl-b then d (written here as: ctrl b + d)
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
# reattach:
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux a
```

**Learning**  
`tmux` is a modern terminal multiplexer similar to `screen`. Key differences:  
- `tmux` uses `Ctrl-b` as its prefix (vs `Ctrl-a` for `screen`).  
- Reattach with `tmux attach` or `tmux a` (vs `screen -r`).

**Resources:** None

---

##  Switching Windows in `tmux`
**FLAG:**  
`pwn.college{cAL3_vn2T5AQP9zrMmm51Csc-Zm.01N4IDOxwiN1AzNzEzW}`

Flag found after switching through windows using `Ctrl-b + <window-number>` inside `tmux`.

**Learning**  
Common `tmux` window commands:  
- `Ctrl-b c` — new window  
- `Ctrl-b n` — next window  
- `Ctrl-b p` — previous window  
- `Ctrl-b <number>` — switch to numbered window  
- `Ctrl-b w` — window list/picker

**Resources:** None
