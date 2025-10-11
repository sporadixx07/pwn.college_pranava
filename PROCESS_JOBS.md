## Listing Processes 

i first opened the /challenge using cd command and then used ps -ef to find the currently running processes and found the renamed /challenge/run then obtained the flag

### learning 
how we can use ps to list the processes running in our terminal. but when we use ps -ef and ps -aux to get a more detailed list. There are many commonalities between ps -ef and ps aux: both display the user (USER column), the PID, the TTY, the start time of the process (STIME/START), the total utilized CPU time (TIME), and the command (CMD/COMMAND). ps -ef ALSO outputs the Parent Process ID (PPID), which is the PID of the process that launched the one in question, while ps aux outputs the percentage of total system CPU and Memory that the process is utilizing

---
## Killing Processes 

i first used ps -ef to view all the processes and found the PID of thw /challenge/dont_ru and then used kil 136 to elimante the process and then did the command /challenge/run to obtain the flag 

### learning
how we can terminate a prcoess using kill PID of a particular process

---
## Interrupting Processes 

i used Ctrl+C to interrupt /challenge/run to obtain the flag 

### learning 
how we can interrupt processes by pressing down on Ctrl and then clicking C.

---
## Killing Misbehaving Processes 

i first used the command ps -ef to view all the current running processes and then found the PID of the decoy and killed it. then i ran /challenge/run command which showed me a lot fo flags and i obtained the last flag in that which was the correct one

### learning 
how we can kill misbehaving prcoesses using kill command with its PID 

---

## Suspending Processes 

i ran the /challenge/run command and then used Ctrl Z to suspend it and then did /challenge/run to obtain the flag

### learning 
how we can suspend processes to the background with Ctrl-Z

---
## Resuming Processes

i ran /challenge/run then i suspended it using Ctrl Z and then resumed it using fg command to obtain the flag

### learning 
how we can use fg command to resume suspended processes

---

## Backgrounding Processes

i first ran /challenge/run then suspended it then used the bg command to background it and then ran /challenge/run again to obtain the flag

### learning 
how we can use bg command to background processes. ALSO when we do ps command in the -o column T meand that is it suspended, S means its sleeping, R means its actively running, + means in foreground. 

---
## Foregrounding Processes 

i first ran /challenge/run then suspended it, then backgrounded it, then foregrounded it and then ran it again and finally hit enter to obtain the flag

### learning 
how we can foreground a backgrounded process using fg

---

## Startinf Backgrounded Processes

i used the command /challenge/run & to directly background the prcoess and obtain the flag

### learning 
how we can directly background processes without suspending them first using command &

---
## Process Exit Codes

i used /challenge/get-code command which exited with errors. then i did echo $? command to obtain the code and then ran /challenge/submit-code 199 to obtain the flag

### learning 
how we can view the error code of a particular command just after a failed process usinf echo $?

---
