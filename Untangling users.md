# 1. Becoming root with su :


 In this challenge, we have to enter the root password that is hack-the-planet and must provide it to su to become root.

## MY SOLUTION:

**Flag** :

```
pwn.college{wdNX_n8QixiPcCkGUyJ05iKmTzi.QX1UDN1wCMxEzNzEzW}

```

Simple challenge where we had to first enter su which asked for a root password so I provided that and became the root to get the flag.

````
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# su
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{wdNX_n8QixiPcCkGUyJ05iKmTzi.QX1UDN1wCMxEzNzEzW}
````


## What I learnt
I learnt about two commands su and sudo which function as helping the user to become the root.
## References 
No reference was used for this challenge.


# 2. Other users with su :


 In this challenge, we have to switch to the zardus user and then run /challenge/run. Zardus' password is dont-hack-me. 

## MY SOLUTION:

**Flag** :

```
pwn.college{YQ0OiVZFRmgjwKLJI2DDfdERT31.QX2UDN1wCMxEzNzEzW}

```

In order to switch to the zardus user instead of root I wrote su zardus, entered the password and ran /challenge/run to get the flag.

````
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{YQ0OiVZFRmgjwKLJI2DDfdERT31.QX2UDN1wCMxEzNzEzW}
````


## What I learnt
I learnt that if we want to switch to a user instead of the root we can write su user.
## References 
No reference was used for this challenge.


# 3. Cracking passwords :


In this challenge, we have to switch to the zardus user and then run /challenge/run. Zardus' password is dont-hack-me. 

## MY SOLUTION:

**Flag** :

```
pwn.college{4vLiP5BOloe2w_5_j6Muhr0ipg-.QX3UDN1wCMxEzNzEzW}

```

So first I viewed all the passwords once then used john the ripper function on /challenge/shadow-leak which helped in cracking the password. I used that password (aardvark) on su zardus user and got the flag.

```
hacker@users~cracking-passwords:~$ cat /challenge/shadow-leak
root:*:20182:0:99999:7:::
daemon:*:20182:0:99999:7:::
bin:*:20182:0:99999:7:::
sys:*:20182:0:99999:7:::
sync:*:20182:0:99999:7:::
games:*:20182:0:99999:7:::
man:*:20182:0:99999:7:::
lp:*:20182:0:99999:7:::
mail:*:20182:0:99999:7:::
news:*:20182:0:99999:7:::
uucp:*:20182:0:99999:7:::
proxy:*:20182:0:99999:7:::
www-data:*:20182:0:99999:7:::
backup:*:20182:0:99999:7:::
list:*:20182:0:99999:7:::
irc:*:20182:0:99999:7:::
gnats:*:20182:0:99999:7:::
nobody:*:20182:0:99999:7:::
_apt:*:20182:0:99999:7:::
systemd-timesync:*:20357:0:99999:7:::
systemd-network:*:20357:0:99999:7:::
systemd-resolve:*:20357:0:99999:7:::
mysql:!:20357:0:99999:7:::
messagebus:*:20357:0:99999:7:::
sshd:*:20357:0:99999:7:::
hacker::20357:0:99999:7:::
zardus:$6$IAc4wAkpIID2t3fq$aVWKrx0NWPqArgwFtswgimXMss5j75aGeC/pFXVPAFcsMblyFQBdz.luyuiGUbW41YEoY3UqKJCLAN4BrnTMr/:20369:0:99999:7:::
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04906g/s 285.7p/s 285.7c/s 285.7C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
hacker@users~cracking-passwords:~$ su zardus
Password: 
su: Authentication failure
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{4vLiP5BOloe2w_5_j6Muhr0ipg-.QX3UDN1wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about John the ripper which is an important tool in cracking passwords stored in a particular user file.
## References 
No reference was used for this challenge.


# 4. Using sudo:


 In this challenge, we have to use sudo to get the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{Ebc6E8D5PMiMqzfR0exGHqxeeZI.QX4UDN1wCMxEzNzEzW}
```

Sticking to the basics, I first changed the directory to / then listed all the files in order to find the flag. Finally I used sudo command.

````
hacker@users~using-sudo:~$ cd /
hacker@users~using-sudo:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@users~using-sudo:/$ sudo cat /flag
pwn.college{Ebc6E8D5PMiMqzfR0exGHqxeeZI.QX4UDN1wCMxEzNzEzW}
````


## What I learnt
I learnt about the sudo command which stands for substitute user do. Now sudo defaults to running a command as root and checks policies to determine whether the user is authorized to run commands as root.
## References 
No reference was used for this challenge.
