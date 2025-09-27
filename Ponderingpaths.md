
## 1. THE ROOT :


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


## 5. IMPLICIT RELATIVE PATHS, FROM / :
In this challenge we need to run  /challenge/run using a relative path while having a current working directory of /.


## MY SOLUTION:

**Flag** :

```
pwn.college{M_Ub5V0uWDbQcnPqF4J6w2dzZbj.QX5QTN0wCMxEzNzEzW}
```


We understand that a relative path is the path which does not start at the root. The cwd here is '/' so first we'll do ``` cd / ``` then ``` challenge/run ``` 

````
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{M_Ub5V0uWDbQcnPqF4J6w2dzZbj.QX5QTN0wCMxEzNzEzW}
````


## What I learnt
I got to learn that a relative path is any path that does not start at root (i.e., it does not start with /) and it is interpreted relative to the current working directory (cwd).

## References 
No reference was used for this challenge.

## 6. EXPLICIT RELATIVE PATHS, FROM / :
In this challenge we need to run /challenge/run using a relative path while having a current working directory of / but we have to use . in our relative paths.


## MY SOLUTION:

**Flag** :

```
pwn.college{svLmatEnvdEyqJQimaN7WpvMDAK.QXwUTN0wCMxEzNzEzW}
```

I found the problem statement's phrasing quite confusing so I wasted quite a lot in understanding what needs to be written. Basically I first wrote the root directory to ``` / ``` and then wrote ``` ./challenge/run``` as mentioned in the challenge

````
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{svLmatEnvdEyqJQimaN7WpvMDAK.QXwUTN0wCMxEzNzEzW}
````


## What I learnt
In the previous challenge, the relative path was "naked" i.e it directly specified the directory to descend into from the current directory. In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory while .. refers to the parent directory.

## References 
No reference was used for this challenge.


## 7. IMPLICIT RELATIVE PATH :
In this challenge we dove a bit deeper into practicing reference to paths using ```.``` . We had to run it from the /challenge directory.


## MY SOLUTION:

**Flag** :

```
pwn.college{k1bIEYlbn51oABsoXNF9Nb329Wv.QXxUTN0wCMxEzNzEzW}
```

Since our aim was to launch run, I first wrote the root directory ```  cd /challenge ``` then wrote ``` ./run ``` which ensured that it was a relative path invoked from the correct directory.

````
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ /run
bash: /run: Is a directory
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{k1bIEYlbn51oABsoXNF9Nb329Wv.QXxUTN0wCMxEzNzEzW}
````


## What I learnt
I understood that if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities.

## References 
No reference was used for this challenge.


## 8. HOME SWEET HOME :
In this challenge, /challenge/run will write a copy of the flag to any file we specify as an argument on the commandline, with these constraints: 1.Your argument must be an absolute path. 2.The path must be inside your home directory. 3.Before expansion, your argument must be three characters or less.


## MY SOLUTION:

**Flag** :

```
pwn.college{YMj3ddCLqCUKrnH_M5IjuIDm5aI.QXzMDO0wCMxEzNzEzW}
```

This was a fairly easy challenge where we just had to abide by the three conditions while specifying the argument. I wrote ``` ~/x ``` which wrote the file to /home/hacker/x

````
hacker@paths~home-sweet-home:~$ /challenge/run ~/x
Writing the file to /home/hacker/x!
... and reading it back to you:
pwn.college{YMj3ddCLqCUKrnH_M5IjuIDm5aI.QXzMDO0wCMxEzNzEzW}
````


## What I learnt
I learnt that  ~ is the shorthand for /home/hacker. Bash provides and uses this shorthand because, again, most of our time will be spent in our home directory. Thus, whenever bash sees ~ provided as the start of an argument in a way consistent with a path, it will expand it to our home directory and ~ is also an absolute path. It was also worth noting that cd will use our home directory as the default destination

## References 
No reference was used for this challenge.

