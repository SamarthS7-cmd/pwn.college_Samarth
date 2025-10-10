# 1. Changing File Ownership :

In this challenge we need to change the owner of the /flag file to the hacker user, and then read the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{kyO3IzNj9V4MKaKqqUok8aVWkvq.QXxEjN0wCMxEzNzEzW}

```

As given in the challenge that we need to change the owner of the /flag file in order to get the flag. We can do this by using the chown hacker /flag command.

````
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{kyO3IzNj9V4MKaKqqUok8aVWkvq.QXxEjN0wCMxEzNzEzW}
````


## What I learnt
I learnt about the chown command, which is the short form of change owner and as the name suggests it is used to change the owner of a given file.
## References 
No reference was used for this challenge.


# 2. Groups and Files :

In this challenge we need to change the group ownership of the flag file to hacker and get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{EzlsMzepdoiHpP7YmMKZq957pp7.QXxcjM1wCMxEzNzEzW}

```

We can change ownership of the flag file with the help of chgrp and I did cat /flag to get the flag.

````
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{EzlsMzepdoiHpP7YmMKZq957pp7.QXxcjM1wCMxEzNzEzW}
````


## What I learnt
I learnt about chgrp command which is basically the short form for change group, and as the name suggests this command is used to change the ownership of a group. I also learnt about the id command which can be used to check what groups you are part of.
## References 
No reference was used for this challenge.



# 3. Fun with Group Names :

In this challenge the name of the group in which the user is present is randomized. We need to find the group name and then change the group ownership in order to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{Ah8_hO1etgxpekVjFt910ux1SlI.QXycjM1wCMxEzNzEzW}

```

So first I used id command to list out all the ids then changed ownership of grp15480 and finally used cat to get the flag.

````
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp15480) groups=1000(grp15480)
hacker@permissions~fun-with-groups-names:~$ chgrp grp15480 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{Ah8_hO1etgxpekVjFt910ux1SlI.QXycjM1wCMxEzNzEzW}
````


## What I learnt
Practice problem so nothing new was learnt.

## References 
No reference was used for this challenge.




# 4. Changing Permissions :

In this challenge we must change the permissions of the /flag file to read it.

## MY SOLUTION:

**Flag** :

```
pwn.college{4JXN2nRbNbf5T_w8FIUIyCSH35H.QXzcjM1wCMxEzNzEzW}

```

I wrote chmod u+r which gave read access to the user's permissions, then we can read the flag

````
hacker@permissions~changing-permissions:~$ chmod go-u+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{4JXN2nRbNbf5T_w8FIUIyCSH35H.QXzcjM1wCMxEzNzEzW}
````


## What I learnt
I learnt about chmod or change mode which helps in changing file permissions with a mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute.

## References 
No reference was used for this challenge.



# 5. Executable Files :

In this challenge we must make /challenge/run executable to get the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{ExmEeYphQc4MKZKu-P-bORdsusR.QXyEjN0wCMxEzNzEzW}

```

In order to make the file executable I wrote chmod u+x and then ran /challenge/run to get the flag.

````
hacker@permissions~executable-files:~$ chmod u+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{ExmEeYphQc4MKZKu-P-bORdsusR.QXyEjN0wCMxEzNzEzW}
````


## What I learnt
I learnt how the various arguments are used with the chmod command for eg: u+r adds read access to the user's permissions g+wx adds write and execute access to the group's permissions o-w removes write access for other users a-rwx removes all permissions for the user, group, and world.

## References 
No reference was used for this challenge.




# 8. The SUID Bit :

In this challenge we have to add the SUID bit to the /challenge/getroot program in order to spawn a root shell to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{AL5wrbXH7QZzgDP6gkHQrxF2EIO.QXzEjN0wCMxEzNzEzW}

```

 given in the challenge we need to add the SUID bit to /challenge/getroot. We can do this by using chmod u+s command.

````
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{AL5wrbXH7QZzgDP6gkHQrxF2EIO.QXzEjN0wCMxEzNzEzW}
````


## What I learnt
I learnt about the SUID bit which stands for "Set User ID". SUID allows the user to run a program as the owner of that program's file.

## References 
No reference was used for this challenge.

