# Personal Notes ( OTW Bandit )

My personal notes on learning Linux CLI from OverTheWire bandit 

this is still work in progress

---


First access the game through the command prompt by typing :
> `ssh bandit0@bandit.labs.overthewire.org -p 2220`

user : bandit0 

pass : bandit0 

for the upper levels, use *bandit # * based on the level, and the password must be obtained from the previous levels

explenation below :
- `ssh` is a cryptographic network protocol that starts an encrypted connection between a client and a server for a secure remote access, command execution, etc
- ` bandit0@bandit.labs.overthewire.org ` is the target destination
  - `bandit0` (USER) is the username of the account you want to log into
  - `bandit.labs.overthewire.org` (IP) is the target ip
  - `@` acts as a seperator between the username and the ip
- `-p 0000` is a way to redirect the ssh to another port  other than the default port that ssh uses. The default port when using ssh is *2200*

---


# level 0-1

used commands ; `ls`, `cd`, `cat`, `file`, `du`, `find`

Summary :
- `ls` (List) : lists files and foldoers in the current directory
  - use `ls -la` to see hidden and detailed lists
- `cd` (Change Directory) : Move into a diffrent **folder**. \
  usage : `cd -foldername-`\
  - use `cd ..` to move out one step from the current directory
- `cat` (Cncatenate) : printss the content  of a selected file directly to the CLI\
  usage : `cat -filename-`
- `file` : tells you what kind of data is inside a file (text, image, binary, etc)
- `du` (Disk Usage) : shows how much storage space files and directories take up
- `find` : Searches for files across a directory tree based on rules (size, name, type)

use `ls` to list the files, and `cat` to print out the password for bandit1


---
