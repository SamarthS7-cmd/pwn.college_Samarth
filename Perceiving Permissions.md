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



````
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp15480) groups=1000(grp15480)
hacker@permissions~fun-with-groups-names:~$ chgrp grp15480 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{Ah8_hO1etgxpekVjFt910ux1SlI.QXycjM1wCMxEzNzEzW}
````


## What I learnt

## References 
No reference was used for this challenge.
