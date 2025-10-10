# 1. The Path Variable :


In this challenge. we have to disrupt the operation of the /challenge/run program. This program will delete the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to the user.

## MY SOLUTION:

**Flag** :

```
pwn.college{ECrK8mQi4SnOjCUTAveIzbjr2Ky.QX2cDM1wCMxEzNzEzW}

```

It was given that /challenge/run is a child process of the shell, so it was clear that we had to use concepts of shell variable in this challenge. I set the PATH variable to /challenge/run and ran it which gave me the flag.
````
hacker@path~the-path-variable:~$ PATH="/challenge/run"
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: command not found
The flag is still there! I might as well give it to you!
pwn.college{ECrK8mQi4SnOjCUTAveIzbjr2Ky.QX2cDM1wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I learnt about PATH that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. In other words through PATH is how the shell can find ls.
## References 
No reference was used for this challenge.




# 2. Setting Path :


In this challenge. This level's /challenge/run will run the win command via its bare name, but this command exists in the /challenge/more_commands/ directory, which is not initially in the PATH. The win command is the only thing that /challenge/run needs, so we can just overwrite PATH with that one directory. 

## MY SOLUTION:

**Flag** :

```
pwn.college{MFVAbDbiqnWoGL4QC25Ii07PuqF.QX1cjM1wCMxEzNzEzW}

```

I first set the PATH variable to /challenge/more_commands and as given this overwrote PATH so I ran /challenge/run which invoked win and gave me the flag.
````
hacker@path~setting-path:~$ PATH="/challenge/more_commands/"
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{MFVAbDbiqnWoGL4QC25Ii07PuqF.QX1cjM1wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I learnt that we can add a new directory of programs to our command repertoire. 
## References 
No reference was used for this challenge.




# 3. Finding Commands :


In this challenge.A win command is added somewhere in $PATH, but it won't give the flag. Instead, it's in the same directory as a flag file that has been made readable. We must find win (with the which command), and cat the flag out of that directory

## MY SOLUTION:

**Flag** :

```
pwn.college{88EjH7sZblcxhM8BKvgRLkoCTAv.01NzEzNxwCMxEzNzEzW}

```

As given in the question I first ran "which win" which printed the name of the file. Then I ran cat "file" which was wrong since we had to first go to the directory in which that file is located so I did that and then ran cat flag.
````
hacker@path~finding-commands:~$ which win
/challenge/paths/1658/win
hacker@path~finding-commands:~$ cat /challenge/paths/1658/win
#!/bin/bash

/bin/fold -s <<< "Search for the flag in the same directory in which I am located!"
hacker@path~finding-commands:~$ cd /challenge/paths/1658/win
bash: cd: /challenge/paths/1658/win: Not a directory
hacker@path~finding-commands:~$ cd /challenge/paths/1658
hacker@path~finding-commands:/challenge/paths/1658$ ls
flag  win
hacker@path~finding-commands:/challenge/paths/1658$ cat flag
pwn.college{88EjH7sZblcxhM8BKvgRLkoCTAv.01NzEzNxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about the "which" command that finds whose name matches the argument that we passed and prints that file.
## References 
No reference was used for this challenge.



# 4. Adding Commands :


In this challenge, we have to make a shell script called win add its location to the PATH, and enable /challenge/run to find the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{swFRUvZ5JqewMJQy9x06V7I4rrA.QX2cjM1wCMxEzNzEzW}
```

As per the challenge, I first created nano win and added 
!#/bin/bash
read flag < /flag 
echo "$flag". 
Then did chmod 777 win to make it read. Then I put PATH=/home/hacker and ran /challenge/run to get the flag.
````
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ cat win
!#/bin/bash
read flag < /flag 
echo "$flag"
hacker@path~adding-commands:~$ chmod 777 win
hacker@path~adding-commands:~$ PATH=/home/hacker
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
/home/hacker/win: line 1: !#/bin/bash: No such file or directory
pwn.college{swFRUvZ5JqewMJQy9x06V7I4rrA.QX2cjM1wCMxEzNzEzW}
````


## What I learnt
It was a practice of shell scripts
## References 
No reference was used for this challenge.



# 5. Hijacking Commands :


This challenge will delete the flag using the rm command. But unlike before, it will not print anything out.

## MY SOLUTION:

**Flag** :

```
pwn.college{YsmWgsTh_fJwoFEGXiqs-sjlOqN.QX3cjM1wCMxEzNzEzW}
```


This was a very good problem, so first to stop the removal of the flag I created a fake directory named /tmp/fake and put the commands into /tmp/fake/rm then I added execute permission to it and exported PATH=/tmp/fake:$PATH. Then I used which rm to check the directories and finally ran /challenge/run to get the flag.
````
hacker@path~hijacking-commands:~$ mkdir -p /tmp/fake
hacker@path~hijacking-commands:~$ echo '#!/bin/bash' > /tmp/fake/rm
hacker@path~hijacking-commands:~$ echo 'cat "${!#}"' >> /tmp/fake/rm
hacker@path~hijacking-commands:~$ chmod +x /tmp/fake/rm
hacker@path~hijacking-commands:~$ export PATH=/tmp/fake:$PATH
hacker@path~hijacking-commands:~$ which rm
/tmp/fake/rm
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /tmp/fake/rm. Executing!
pwn.college{YsmWgsTh_fJwoFEGXiqs-sjlOqN.QX3cjM1wCMxEzNzEzW}
````


## What I learnt
This problem covered the concepts of previous challenges
## References 
No reference was used for this challenge.





