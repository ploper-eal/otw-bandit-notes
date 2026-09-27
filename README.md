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


## level 0-1 // bandit0

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


## level 1-2 // bandit1

used commands ; `ls`, `cd`, `cat`, `file`, `du`, `find`

Summary :
there will be a file with a dasb(-). Typing in `cat -` wont work, since it acctually tells the cat (concatenate) utility to read data from standard input (your keyboard or a piped stream) instead of a file.
- use `./` to tell cat that it is a normal argument or file since there is a slash
- can also use `--` before a filename, to stop flagchecking


---


## level 2-3 // bandit2

used commands ; `ls`, `cd`, `cat`, `file`, `du`, `find`

Summary : 
there will be a file with the name --spaces in this filename--. when we type in `cat --spaces in the filename--`, it will acctullay look for 3 diffrent files(--spaces, in, the, filename--)
- use `" "` to treat the name as a singgle word
- also use `--` to stop flagchecking also


---


## level 3-4 // bandit3

used commands ; `ls`, `cd`, `cat`, `file`, `du`, `find`

Summary :
there will be a hidden file inside a directory.
- use `cd` to change the directory
- use `ls -la`. the added "-la" means show all files including the hidden ones


---


## level 4-5 // bandit4

used commands ; `ls`, `cd`, `cat`, `file`, `du`, `find`

Summary :
there will be a lot of files inside the inhere directory, use the file command to see the files filetype
- use `file ./*` to check all file data types
    - `file` is to check the filetype
    - `*` means everyfile in the current directory, followed by `./` to stop flagchecking files with dashed filenames


---


## level 5-6 // bandit5

Summary :
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

1. human-readable
2. 1033 bytes in size
3. not executable

- use `find . -type f -size 1033c ! -executable`
  - using find  to search for a file with specific details
  - `.` means the current directory
  - `-type f` means to find a regular file and not a directory
  - `-size 1033c` means to search for a file with 1033c(bytes) in size
  - `! -executable` means to exclude any executable files from the search


 ---


 ## level 6-7 // bandit6

 Summary : 
 find the password somewhere in the server that has these properties:
 1. owned by user bandit7
 2. owned by group bandit6
 3. 33 bytes in size

- use `find / -user bandit7 -group bandit6 2>/dev/null`
  - `/` means to lookup the intire server
  - `-user bandit7` shrinks the lookup to only files owned by user bandit7
  - `-group bandit6` shrinks it again to only files owned by group bandit6
  - `2>/dev/null` means to hide any error massage (permission denied, etc)


---


## level 7-8 // bandit7
