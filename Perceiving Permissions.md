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


# 6. Permission Tweaking Practices :

This challenge will ask us to change the permissions of the /challenge/pwn file in specific ways a few times in a row. 

## MY SOLUTION:

**Flag** :

```
pwn.college{sDaO_bIyEaBPxXL-scf3t5g_eex.QXwEjN0wCMxEzNzEzW}
```

I used the concept of octal notation to solve this challenge, although it took time to understand I was able to get the flag

````
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod 604 /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw----rwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 607 /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": rw----rwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw--wxrwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 637 /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": rw--wxrwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-----r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 404 /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": r-----r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw----rw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 606 /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": rw----rw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx---rwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 707 /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": rwx---rwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwx-wxrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 737 /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": rwx-wxrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwx-wxrw-
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ^C
hacker@permissions~permission-tweaking-practice:~$ chmod 736 /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod 400 /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{sDaO_bIyEaBPxXL-scf3t5g_eex.QXwEjN0wCMxEzNzEzW}
````


## What I learnt
I learnt about octal notations and how we can use them to change file permissions.

## References 
No reference was used for this challenge.



# 7. Permissions Setting Practice :

In this challenge we need to change the permissions like in the previous challenge but this challenge requires more radical permission changes.

## MY SOLUTION:

**Flag** :

```
pwn.college{cHF-LdYshX2oDsGzQdp94VZD8iF.QXzETO0wCMxEzNzEzW}

```

Used the same procedure as the one done in the previous challenge.

````
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw--wxr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 634 /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rw--wxr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---rw---x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ ^C
hacker@permissions~permissions-setting-practice:~$ chmod 061 /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": ---rw---x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxr----x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 741 /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": rwxr----x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---r---w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 042 /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": ---r---w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-xrwxr--
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 574 /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": r-xrwxr--
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-x--xr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 515 /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": r-x--xr-x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr---wx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 543 /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": r-xr---wx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---rwxrwx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 077 /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod 400 /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{cHF-LdYshX2oDsGzQdp94VZD8iF.QXzETO0wCMxEzNzEzW}
````


## What I learnt
This was another practice problem so nothing new was learnt.

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

