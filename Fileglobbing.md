## 1. MATCHING WITH * :


In this challenge, we need to first change your directory to /challenge, but use globbing to keep the argument we need to pass to cd to at most four characters and run /challenge/run for the flag!


## MY SOLUTION:

**Flag** :

```
pwn.college{8-gCCO2NcReGQwUCqy9e33Y18XL.QXxIDO0wCMxEzNzEzW}

```


As given in the question we had to first change the directory so I wrote ``` cd /ch* ``` which also satisfied the condition of having at most four characters. Then I ran /challenge/run to get the flag.

````
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{8-gCCO2NcReGQwUCqy9e33Y18XL.QXxIDO0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn about * glob, it works as when it encounters a * character in any argument, the shell will treat it as a "wildcard" and try to replace that argument with any files that match the pattern.

## References 
No reference was used for this challenge.
