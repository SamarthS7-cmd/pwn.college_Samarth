
##1. THE ROOT :


In this challenge, to get the flag, we must invoke the pwn program using its absolute path


## MY SOLUTION:

**Flag** :

```
pwn.college{4GIqTOOnDJQUiJMC4QRPL5PDH4H.QX4cTO0wCMxEzNzEzW}
```


This module aims in teaching the basics of linux file paths. The Linux filesystem is a "tree". That is, it has a root (written as /). 
The root of the filesystem is a directory, and every directory can contain other directories and files. So the file system starts with a '/', in this challenge I provided the exact path on the command line
i.e /pwn. This style of path which starts with a root directory is called absolute path.


````
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{4GIqTOOnDJQUiJMC4QRPL5PDH4H.QX4cTO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I was able to learn about how linux file system works through a chain of directories and get to know about absolute and relative paths.

## References 
No reference was used for this challenge.


## 2. PROGRAM AND ABSOLUTE PATHS :
The challenge requires launching the program using its absolute path — specifically the run directory located under the challenge folder.



## MY SOLUTION:

**Flag** :

```
pwn.college{oFPUIKuj-g2nJ39bIEHLQZ-dMuU.QX1QTN0wCMxEzNzEzW}
```


The prompt indicates you must execute the program by its absolute path (/challenge/run) rather than relying on a relative path or shell path.

````
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{oFPUIKuj-g2nJ39bIEHLQZ-dMuU.QX1QTN0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I was able to learn that there are two kinds of paths in Linux: absolute paths and relative paths.

## References 
No reference was used for this challenge.


## 3. POSITION THY SELF :
This challenge asks us to execute the /challenge/run program from a specific path which will be given and we have to cd that path and re run.



## MY SOLUTION:

**Flag** :

```
pwn.college{kvUjABjzEvg7igD40YJDII9do8t.QX2QTN0wCMxEzNzEzW}
```


For solving this challenge I had to use cd which is a command for changing directories. Now as it was mentioned that to find the flag we had to first find the specific path from which we had to invoke /challenge/run. So I first ran /challenge/ran, got the directory then applied cd and re ran it to get the flag.

````
hacker@paths~position-thy-self:~$ cd /usr/aarch64-linux-gnu/include/gnu
hacker@paths~position-thy-self:/usr/aarch64-linux-gnu/include/gnu$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{kvUjABjzEvg7igD40YJDII9do8t.QX2QTN0wCMxEzNzEzW}
````


## What I learnt
I learnt about the cd command how it is used in changing the directories and files in linux, and how i can use the cd command to navigate through different directories. I also learnt what the (~) was in the prompt. It shows the current path that your shell is located at.

## References 
No reference was used for this challenge.


## 4. POSITION YET ELSEWARE :
This challenge asks us to execute the /challenge/run program from a specific path which will be given and we have to cd that path and re run.



## MY SOLUTION:

**Flag** :

```
pwn.college{8CUK36SXkjNGN1xmp1Qgabt1kEU.QX4QTN0wCMxEzNzEzW}
```


For solving this challenge I had to use cd which is a command for changing directories. Now as it was mentioned that to find the flag we had to first find the specific path from which we had to invoke /challenge/run. So I first ran /challenge/ran, got the directory then applied cd and re ran it to get the flag.

````
hacker@paths~position-yet-elsewhere:~$ cd /usr/share/doc/fontconfig
hacker@paths~position-yet-elsewhere:/usr/share/doc/fontconfig$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8CUK36SXkjNGN1xmp1Qgabt1kEU.QX4QTN0wCMxEzNzEzW}
````


## What I learnt
Since this was a similar problem nothing new was learnt.

## References 
No reference was used for this challenge.
