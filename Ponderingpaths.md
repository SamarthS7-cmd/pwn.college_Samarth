
## THE ROOT :


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
