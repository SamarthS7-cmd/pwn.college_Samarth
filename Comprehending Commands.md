# 1. cat : not the pet, but the command :


In this challenge. we have to use the cat command to find the flag which is hidden in the home directory.

## MY SOLUTION:

**Flag** :

```
pwn.college{kS-F7ivpVy5JQV1t0yGdEaeWTcJ.QXxcTN0wCMxEzNzEzW}
```

A simple challenge where we had to use the cat command to get the flag.
````
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{kS-F7ivpVy5JQV1t0yGdEaeWTcJ.QXxcTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn cat command which is a short form for concatenate. It will also read from the terminal input and output it. 
## References 
No reference was used for this challenge.


# 2. CATTING ABSOLUTE PATHS :


In this challenge, we have to read it with cat at its absolute path: /flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{opov5Qii-MZcH4MNcQ2ipK5-tZE.QX5ETO0wCMxEzNzEzW}
```

To solve this challenge, I wrote cat /flag which helped in reading the file which is in the root directory instead of home directory.
````
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{opov5Qii-MZcH4MNcQ2ipK5-tZE.QX5ETO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I was able to understand that we can specify cat's arguments as absolute paths.
## References 
No reference was used for this challenge.


# 3. MORE CATTING PRACTICE :


In this challenge, we have to retrieve the flag from an absolute path which will be mentioned.

## MY SOLUTION:

**Flag** :

```
pwn.college{Ap2xSWQVHGBeWTx6nUc541pAxt0.QXwITO0wCMxEzNzEzW}
```

To solve this challenge, the path was mentioned as /lib/terminfo/d/flag. So I wrote cat /lib/terminfo/d/flag to get the flag.
````
hacker@commands~more-catting-practice:~$ cat /lib/terminfo/d/flag
pwn.college{Ap2xSWQVHGBeWTx6nUc541pAxt0.QXwITO0wCMxEzNzEzW}
````


## What I learnt
This challenge was just a practice one.
## References 
No reference was used for this challenge.

# 4. GREPPING FOR A NEEDLE IN HAYSTACK :


In this challenge, a hundred thousand lines of text into the /challenge/data.txt file. We have to grep it for the flag.
 
## MY SOLUTION:

**Flag** :

```
pwn.college{8jCR5d4w9KFa3J0JseKQXmke1CS.QX3EDO0wCMxEzNzEzW}
```

To solve this challenge, I simply used the grep command and it was given that the flag starts with pwn.college.
````
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{8jCR5d4w9KFa3J0JseKQXmke1CS.QX3EDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about the grep command which helps in searching for the content from large files.
## References 
No reference was used for this challenge.

# 5. COMPARING FILES :


In this challenge, we have to use diff command to find out the difference between /challenge/decoys_only.txt and /challenge/decoys_and_real.txt files.
 
## MY SOLUTION:

**Flag** :

```
pwn.college{wqXDRLZ1mLhAX8NTMOf-AOB_4rR.01MwMDOxwCMxEzNzEzW} 

```
We had to just use diff and name the two files in order to get the flag
````
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
67a68
> pwn.college{wqXDRLZ1mLhAX8NTMOf-AOB_4rR.01MwMDOxwCMxEzNzEzW}

````


## What I learnt
I learnt about the diff command which compares two files line by line and shows you exactly what's different between them. 
## References 
No reference was used for this challenge.


# 6. LISTING FILES :


In this challenge, /challenge/run has been named with some random name. We have to List the files in /challenge to find it.
 
## MY SOLUTION:

**Flag** :

```
pwn.college{QV53Gm7ejjh85LAed7VZaKfFoN7.QX4IDO0wCMxEzNzEzW}

```
I used the ls command to list all the files, then I ran 29873-renamed-run-20453 from /challenge to get the flag.
````
hacker@commands~listing-files:~$ ls /challenge
29873-renamed-run-20453  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/29873-renamed-run-20453
Yahaha, you found me! Here is your flag:
pwn.college{QV53Gm7ejjh85LAed7VZaKfFoN7.QX4IDO0wCMxEzNzEzW}

````


## What I learnt
I learnt about the ls command which helps in listing files in all the directories provided to it as arguments, and in the current directory if no arguments are provided

## References 
No reference was used for this challenge.


# 7. TOUCHING FILES :


In this challenge, we have to create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get the flag
 
## MY SOLUTION:

**Flag** :

```
pwn.college{gQY1wRl9neKy8VnVjmPWK-MwYuj.QXwMDO0wCMxEzNzEzW}

```
I first changed my directory to tmp, then I created two files pwn and college using touch.
````
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{gQY1wRl9neKy8VnVjmPWK-MwYuj.QXwMDO0wCMxEzNzEzW}

````


## What I learnt
I learnt about the touch command which lets me create new files.

## References 
No reference was used for this challenge.


# 8. REMOVING FILES :


In this challenge, we have to create a delete_me file in the home directory. Delete it, then run /challenge/check, which will make sure we've deleted it and then give the flag.
## MY SOLUTION:

**Flag** :

```
pwn.college{44maG2tBOs1LYc-nHK_dq-WHbRD.QX2kDM1wCMxEzNzEzW}

```
I removed delete_me file using the rm command then wrote /challenge/check to check for the deletion of the file.
````
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{44maG2tBOs1LYc-nHK_dq-WHbRD.QX2kDM1wCMxEzNzEzW}

````


## What I learnt
I learnt about the rm command which lets me delete files.

## References 
No reference was used for this challenge.


# 9. MOVING FILES :


In this challenge, we have to move the /flag file into /tmp/hack-the-planet and run /challenge/check, which will check things out and give the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{AQSMAu0NLIfXlPTfPj-uMbetQX2.0VOxEzNxwCMxEzNzEzW}

```
I used the mv command to move /flag into /tmp/hack-the-planet and then ran /challenge/check to get the flag.
````
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{AQSMAu0NLIfXlPTfPj-uMbetQX2.0VOxEzNxwCMxEzNzEzW}

````


## What I learnt
I learnt about the mv command which helps in moving the files around.
## References 
No reference was used for this challenge.


# 10. HIDDEN FILES :


In this challenge, we have to find the flag, hidden as a dot-prepended file in /.

## MY SOLUTION:

**Flag** :

```
pwn.college{4Q2IzHjVunOjRTtPV7xfGLLPCiz.QXwUDO0wCMxEzNzEzW}

```

To solve this challenge, I first changed the directory to / then I listed all the files. there I could see .flag-10401327583397 which I printed through cat and got the flag.

````
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-10401327583397  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ ca^C
hacker@commands~hidden-files:/$ cat .flag-10401327583397
pwn.college{4Q2IzHjVunOjRTtPV7xfGLLPCiz.QXwUDO0wCMxEzNzEzW}

````


## What I learnt
I learnt about the -a command which lets me list out the files which are dot prepended.
## References 
No reference was used for this challenge.

# 11. AN EPIC FILESYSTEM QUEST :


In this challenge we have to use our knowledge of previous modules and practice problems to find the flag using given clues : 0.Your first clue is in /. Head on over there. 1.Look around with ls. There'll be a file named HINT or CLUE or something along those lines! 2.cat that file to read the clue! 3.Depending on what the clue says, head on over to the next directory (or don't!). 4.Follow the clues to the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{soEP51DJx52ThAf7D7mn-c3QG3n.QX5IDO0wCMxEzNzEzW}

```

We had to just follow the clues given and play with cd ls and cat.

````
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
MEMO  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat MEMO
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/drivers/net/team

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/$ cat /opt/linux/linux-5.4/drivers/net/team/TIP-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/cachetools-5.5.2.dist-info

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/local/lib/python3.8/dist-packages/cachetools-5.5.2.dist-info
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/cachetools-5.5.2.dist-info$ ls
INSTALLER  LICENSE  METADATA  RECORD  WHEEL  top_level.txt
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/cachetools-5.5.2.dist-info$ ls -a
.  ..  .NOTE  INSTALLER  LICENSE  METADATA  RECORD  WHEEL  top_level.txt
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/cachetools-5.5.2.dist-info$ cat .NOTE
Great sleuthing!
The next clue is in: /usr/share/X11/locale/km_KH.UTF-8

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/cachetools-5.5.2.dist-info$ cd  /usr/share/X11/locale/km_KH.UTF-8
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/locale/km_KH.UTF-8$ ls
Compose  SPOILER  XI18N_OBJS  XLC_LOCALE
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/locale/km_KH.UTF-8$ cat SPOILER
Tubular find!
The next clue is in: /usr/share/bug/libgl1

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/locale/km_KH.UTF-8$ cd /usr/share/bug/libgl1
hacker@commands~an-epic-filesystem-quest:/usr/share/bug/libgl1$ ls -a
.  ..  .CLUE  control
hacker@commands~an-epic-filesystem-quest:/usr/share/bug/libgl1$ cat .CLUE
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/scripts/kconfig/tests/err_recursive_dep
hacker@commands~an-epic-filesystem-quest:/usr/share/bug/libgl1$ cd /opt/linux/linux-5.4/scripts/kconfig/tests/err_recursive_dep
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/scripts/kconfig/tests/err_recursive_dep$ ls
Kconfig  SECRET  __init__.py  expected_stderr
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/scripts/kconfig/tests/err_recursive_dep$ cat SECRET
Tubular find!
The next clue is in: /usr/lib/python3/dist-packages/urllib3-1.25.8.egg-info

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/scripts/kconfig/tests/err_recursive_dep$ cd /usr/lib/python3/dist-packages/urllib3-1.25.8.egg-info
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/urllib3-1.25.8.egg-info$ ls
PKG-INFO  WHISPER  dependency_links.txt  requires.txt  top_level.txt
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/urllib3-1.25.8.egg-info$ cat WHISPER
Lucky listing!
The next clue is in: /usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/urllib3-1.25.8.egg-info$ cd /usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__$ ls
__init__.cpython-38.pyc       cartan_type.cpython-38.pyc     root_system.cpython-38.pyc  type_b.cpython-38.pyc  type_d.cpython-38.pyc  type_f.cpython-38.pyc  weyl_group.cpython-38.pyc
cartan_matrix.cpython-38.pyc  dynkin_diagram.cpython-38.pyc  type_a.cpython-38.pyc       type_c.cpython-38.pyc  type_e.cpython-38.pyc  type_g.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__$ ls -a
.   .README                  cartan_matrix.cpython-38.pyc  dynkin_diagram.cpython-38.pyc  type_a.cpython-38.pyc  type_c.cpython-38.pyc  type_e.cpython-38.pyc  type_g.cpython-38.pyc
..  __init__.cpython-38.pyc  cartan_type.cpython-38.pyc    root_system.cpython-38.pyc     type_b.cpython-38.pyc  type_d.cpython-38.pyc  type_f.cpython-38.pyc  weyl_group.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__$ cat .README
Great sleuthing!
The next clue is in: /usr/share/racket/pkgs/scheme-lib/scheme/exists/lang/compiled

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__$ ls /usr/share/racket/pkgs/scheme-lib/scheme/exists/lang/compiled
BRIEF-TRAPPED  reader_rkt.dep  reader_rkt.zo
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/liealgebras/__pycache__$ cat /usr/share/racket/pkgs/scheme-lib/scheme/exists/lang/compiled/BRIEF-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{soEP51DJx52ThAf7D7mn-c3QG3n.QX5IDO0wCMxEzNzEzW}

````


## What I learnt
This challenge helped me improve my skills in searching for files.
## References 
No reference was used for this challenge.


# 12. MAKING DIRECTORIES :


In this challenge, we have to create a /tmp/pwn directory and make a college file in it. Then run /challenge/run, which will check your solution and give the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{8an3gY73k7OuEwX5KkVJdGvBlEM.QXxMDO0wCMxEzNzEzW}
```

To solve this challenge, I created a /tmp/pwn directory using mkdir command then changed it to that directory. then I created a file college using touch command then finally ran /challenge/run

````
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{8an3gY73k7OuEwX5KkVJdGvBlEM.QXxMDO0wCMxEzNzEzW}

````


## What I learnt
I learnt about the mkdir command which is used to create directories and is the short form for make directory.
## References 
No reference was used for this challenge.


# 13. FINDING FILES :


In this challege we have to find the hidden flag which is in a random directory on the filesystem.

## MY SOLUTION:

**Flag** :

```
pwn.college{Q3Mb6fW0ivRxifXvNG9G2v6PXLE.QXyMDO0wCMxEzNzEzW}
```

To solve this challenge, I used the file command to find the hidden flag.After a few tries, i was successful in finding the correct flag.

````
hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.4mK6TfTSUV’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/vim/vim81/pack/dist/opt/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
cat: /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /usr/share/vim/vim81/pack/dist/opt/flag
pwn.college{Q3Mb6fW0ivRxifXvNG9G2v6PXLE.QXyMDO0wCMxEzNzEzW}

````


## What I learnt
I learnt about the find command. The find command takes optional arguments describing the search criteria and the search location. If you don't specify a search criteria, find matches every file. If you don't specify a search location, find uses the current working directory 
## References 
No reference was used for this challenge.


# 14. LINKING FILES :


In this challenge, the flag is in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. We have to use the symlink, and fool it into giving the flag.
## MY SOLUTION:

**Flag** :

```
pwn.college{8an3gY73k7OuEwX5KkVJdGvBlEM.QXxMDO0wCMxEzNzEzW}
```

As given in the challenge /challenge/catflag will read out /home/hacker/not-the-flag, hence we can just swap the symlink to point it towards the /flag, and get the flag.
````
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{ITQpNPNLdASZ4qtYVUHoEKSWf4A.QX5ETN1wCMxEzNzEzW}

````


## What I learnt
I learnt about the types of links which can be classified into hard and soft links. I also learnt about symbolic links (also known as symlinks). Symbolic links are created with the ln command with the -s argument.
## References 
No reference was used for this challenge.

