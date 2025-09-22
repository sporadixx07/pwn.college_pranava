# PONDERING PATH
## the root
**flag** pwn.college{41vm9_DSd37waDFicyIYmbqDQnM.QX4cTO0wiN1AzNzEzW}\
flag was found in ' /pwn '
### learning
root is the basis of all directories and everything else diverges from root. paths starting from the root are called ABSOLUTE PATH

## program and absolute paths
**flag** pwn.college{4ONoqZOStL_QdSpo8-d3GkuyBNc.QX1QTN0wiN1AzNzEzW}\
flag was found in ' /challenge/run '
### learning
any program inside of any dir can be accessed thru the absolute path starting in root

## position thy self
**flag** pwn.college{ktvvJy2OAOrz1TyZSjOBp846-Q1.QX2QTN0wiN1AzNzEzW}\
flag was found after running absolute path ' /challenge/run ' after first moving into usr/include directory using 'cd' commands
### learning
cd is used to change directories

## position elsewhere
**flag** pwn.college{AEp_cYQnD9qutX3w66J8L199NyA.QX3QTN0wiN1AzNzEzW}\
flag was found after running the absolute path after changing directories into the root first
### learning
even if accessing anything from root, absolute path still requires / 

## position yet elsehwere
**flag** pwn.college{Y3Y0_lmqdE-kwD2Nd-aATB9_H8r.QX4QTN0wiN1AzNzEzW}\
flag was found after running the absolute path from home dir
### learning
different directories present under root

## implicit relative paths from /
**flag** pwn.college{MU8MlnKTYsJwPTDPXTy17VQNKRc.QX5QTN0wiN1AzNzEzW}\
flag was found after running relative path after changing to / dir
### learning
relative paths starts from the current directory and DO NOT NEED / at begining.

## explicit relative path
**flag** pwn.college{wcjLgZ-mDewlEQ87Xqdy2jRJk76.QXwUTN0wiN1AzNzEzW}\
flag was found after explicitly ordering command to start from current directory by specifying . in the command
### learning
. corresponds to cwd and running relative paths from cwd, specifying it is optional.

## implicit relavtive path
**flag** pwn.college{EFm8Alg8tWPQ-7286tLNNGu09s6.QXxUTN0wiN1AzNzEzW}\
flag was found after specifically asking shell to run the command by specifying ./run
### learning
programs in cwd wont run unless specifed. this is a safety measure directed at preventing malicious programs from running from the current dit

## home sweet home
**flag** pwn.college{MY8GtTXpBP3J2ZZaeRuFtOnNWs8.QXzMDO0wiN1AzNzEzW}
flag was found after writing the flag in /challenge/run into ~/~.
### learning
bash makes ~ a shorthand for /home/hacker. 




