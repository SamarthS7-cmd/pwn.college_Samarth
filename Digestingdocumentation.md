## 1. LEARNING DOCUMENTATION :


In this challenge we need to pass the correct argument to /challenge/challenge to get the flag.


## MY SOLUTION:

**Flag** :

```
pwn.college{cSCjJUBqEzYtN2RyYSxdauQc08S.QX0ITO0wCMxEzNzEzW}
```


As given in this challenge we need to pass the right argument which is --giveflag through the /challenge/challenge program to get the flag


````
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{cSCjJUBqEzYtN2RyYSxdauQc08S.QX0ITO0wCMxEzNzEzW}

````


## What I learnt
The correct usage of programs depends, in a large part, on the proper specification of arguments to them. The -a of ls -a in the hidden files challenge of the Basic Commands module: that -a was an argument that told ls to list out hidden files as well as non-hidden files. Because we wanted to list out hidden files, invoking ls with the -a argument was the correct way to use it in our scenario.

## References 
No reference was used for this challenge.



## 2. LEARNING COMPLEX USAGE :

In this challenge we need to use the --printfile argument correctly in order to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{MtuAaED8Q0HHuFwWTTh6R5kt9hG.QX1ITO0wCMxEzNzEzW}

```


So first, I wrote ```/challenge/challenge --printfile /challenge/DESCRIPTION.md ``` This program allows you to print arbitrary files to the terminal, when given the `--printfile` argument. The argument to the `--printfile` argument is the path of the flag to read.


````
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/DESCRIPTION.md
Correct argument! Here is the /challenge/DESCRIPTION.md file:
While using most commands is straightforward, the usage of some commands can get quite complex.
For example, the arguments to commands like `sed` and `awk`, which we're definitely not getting into right now, are entire programs in an esoteric programming language!
Somewhere on the spectrum between `cd` and `awk` are commands that take arguments to their arguments...

This sounds crazy, but you've already encountered this with the `find` level in [Basic Commands](/linux-luminarium/commands).
`find` has a `-name` argument, and the `-name` argument itself takes an argument specifying the name to search for.
Many other commands are analogous.

Here is this level's documentation for `/challenge/challenge`:

> Welcome to the documentation for `/challenge/challenge`! This program allows you to print arbitrary files to the terminal, when given the `--printfile` argument. The argument to the `--printfile` argument is the path of the flag to read. For example, `/challenge/challenge --printfile /challenge/DESCRIPTION.md` will print out the description of the level!

Given that documentation, go get the flag!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/flag
Correct argument! Here is the /challenge/flag file:
cat: /challenge/flag: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{MtuAaED8Q0HHuFwWTTh6R5kt9hG.QX1ITO0wCMxEzNzEzW}


````


## What I learnt
I learnt the complex usage of commands and how different arguments work.

## References 
No reference was used for this challenge.


## 3. READING MANUALS :


We have to first invoke the manpage for a certain command line which when printed will help printing the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{01LVHnqcWDOQLcm4SBEDZj7730N.QX0EDO0wCMxEzNzEzW}

```
Firstly, we had to print ``` man challenge ``` and then read through the description. I then found out that --nqccmj 014 is used to the print the flag if the NUM is 014.





````
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --nqccmj 014
Correct usage! Your flag: pwn.college{01LVHnqcWDOQLcm4SBEDZj7730N.QX0EDO0wCMxEzNzEzW}


````


## What I learnt
I learnt about the man command which is the shortform of manual and as the name suggests, man command is used to check the manual of a particular command and then we can read about the command.

## References 
No reference was used for this challenge.


## 4. SEARCHING MANUALS :

In this challenge we have to search the manual to find the flag with different options in manual page such as arrow keys (and PgUp/PgDn) and search with /. we can also use n to go to the next result and N to go to the previous result.


## MY SOLUTION:

**Flag** :

```
pwn.college{YcQ7kRPYgB_VlZchkSblAtJ2Xfw.QX1EDO0wCMxEzNzEzW}

```
So we had to first invoke the man challenge which opened a long documentation, there I could identify that printing --ntu (found out by searching through '/') will help in giving me the flag



````
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ 
hacker@man~searching-manuals:~$ /challenge/challenge --ntu
Initializing...
Correct usage! Your flag: pwn.college{YcQ7kRPYgB_VlZchkSblAtJ2Xfw.QX1EDO0wCMxEzNzEzW}


````


## What I learnt
I learnt how we can go up and down in a manual and also use / to search within the documentation.
## References 
No reference was used for this challenge.


## 5. SEARCHING FOR MANUALS :

In this challenge the manpage for the challenge is hidden by randomizing its name.we have to use the hints to find the flag. HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge. HINT 2: though the manpage is randomly named, you still actually use /challenge/challenge to get the flag!


## MY SOLUTION:

**Flag** :

```
pwn.college{oq1StzejEkkxnOoPdGUgP1aC9QR.QX2EDO0wCMxEzNzEzW}

```
So first I invoked man man which gave me a long manual there I could see that -k argument can be used for searching keywords. I did man -k challenge and then it gave me the next step to be done which is invoking man oqtzejkkxn, now this further laid out another hint of using --oqtzej NUM if the NUM is 119.


````
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ 
hacker@man~searching-for-manuals:~$ man -k challenge
oqtzejkkxn (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man oqtzejkkxn
hacker@man~searching-for-manuals:~$ 
hacker@man~searching-for-manuals:~$ /challenge/challenge --oqtzej 119
Correct usage! Your flag: pwn.college{oq1StzejEkkxnOoPdGUgP1aC9QR.QX2EDO0wCMxEzNzEzW}


````


## What I learnt
I learnt that man command also has a man page for its different arguments.I also learnt that -k argument is used to search.
## References 
No reference was used for this challenge.
