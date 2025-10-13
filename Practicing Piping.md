# 1. REDIRECTING OUTPUT :


In this challenge. we have to use the output redirection to write the word PWN (all uppercase) to the filename COLLEGE (all uppercase).

## MY SOLUTION:

**Flag** :

```
pwn.college{o0RqXXwiHDuiYXgRsyAuFdGVxuf.QX0YTN0wCMxEzNzEzW}

```

Fairly simple challenge where we had to make use of >, which helped in writing PWN to COLLEGE
````
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{o0RqXXwiHDuiYXgRsyAuFdGVxuf.QX0YTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn about the use of ``` > ``` in redirecting stdout to files
## References 
No reference was used for this challenge.


# 2. REDIRECTING MORE OUTPUT :


In this challenge, /challenge/run will once more give us the flag, but we have to redirect its output to the file myflag.

## MY SOLUTION:

**Flag** :

```
pwn.college{0Acnenx3pOeFSM9vSj6dXDR8v44.QX1YTN0wCMxEzNzEzW}
```

As the challenge suggests, we can easily redirect the output of /challenge/run to myflag  using /challenge/run my stdout > myflag
````
hacker@piping~redirecting-more-output:~$ /challenge/run my stdout > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{0Acnenx3pOeFSM9vSj6dXDR8v44.QX1YTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I learnt that aside from redirecting the output of echo, we can also redirect the output of any command.

## References 
No reference was used for this challenge.


# 3. APPENDING OUTPUT :

We have to run /challenge/run with an append-mode redirect of the output to the file /home/hacker/the-flag. The practice will write the first half of the flag to the file, and the second half to stdout if stdout is redirected to the file. 
If you properly redirect in append-mode, the second half will be appended to the first, but if you redirect in truncation mode (>), the second half will overwrite the first and you won't get the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{4aEF39ROPU2QQQXATwkPnh0HtFy.QX3ATO0wCMxEzNzEzW}
```

As the challenge suggests, we can run /challenge/run with an append-mode (>>) and redirect the output to /home/hacker/the-flag by /challenge/run stdout >> /home/hacker/the-flag
````
hacker@piping~appending-output:~$ /challenge/run stdout >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{4aEF39ROPU2QQQXATwkPnh0HtFy.QX3ATO0wCMxEzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!

````


## What I learnt
Through this challenge, I learnt that we can redirect input in append mode using >> which will append in the same file. > creates a new file everytime we redirect the output which is not the case with >>

## References 
No reference was used for this challenge.


# 4. REDIRECTING ERRORS :


In this challenge, we will need to redirect the output of /challenge/run, like before, to myflag, and the "errors" (in our case, the instructions) to instructions.

## MY SOLUTION:

**Flag** :

```
pwn.college{or-x_IM2zPAkTxLyagi3aGx6UoA.QX3YTN0wCMxEzNzEzW}
```

This challenge asked us to redirect multiple file descriptors which was easily done with /challenge/run stdout > myflag 2> instructions
````
hacker@piping~redirecting-errors:~$ /challenge/run stdout > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{or-x_IM2zPAkTxLyagi3aGx6UoA.QX3YTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I learnt that we can redirect errors channel of commands. I also learnt about file descriptor numbers.

## References 
No reference was used for this challenge.

# 5. REDIRECTING INPUT :


In this challenge, we will practice using /challenge/run, which will require US to redirect the PWN file to it and have the PWN file contain the value COLLEGE.

## MY SOLUTION:

**Flag** :

```
pwn.college{cVv1IGpkWqDyLqLCA4vMDxJIjxy.QXwcTN0wCMxEzNzEzW}
```

So first I used echo COLLEGE > PWN in order to make sure that PWN file contains COLLEGE. Then I wrote /challenge/run rev < PWN which redirected the PWN file into the standard input.
````
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run rev < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{cVv1IGpkWqDyLqLCA4vMDxJIjxy.QXwcTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I learnt about how we can redirect input using <

## References 
No reference was used for this challenge.


# 6. GREPPING STORED RESULTS :


In this challenge, we have to do the following :
1.Redirect the output of /challenge/run to /tmp/data.txt.
2.This will result in a hundred thousand lines of text, with one of them being the flag, in /tmp/data.txt.
3.Grep that for the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{88QeUk1EZ2WsGhKGTM84d7wDZ4p.QX4EDO0wCMxEzNzEzW}
```

I just went step by step with what the problem statement directed me to do and finally got the flag.
````
hacker@piping~grepping-stored-results:~$ /challenge/run stdout > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{88QeUk1EZ2WsGhKGTM84d7wDZ4p.QX4EDO0wCMxEzNzEzW}

````


## What I learnt
Since it was a practice problem, nothing new was learnt instead I used the concepts of previous challenges.

## References 
No reference was used for this challenge.



# 7. GREPPING LIVE OUTPUT:


In this challenge, /challenge/run will output a hundred thousand lines of text, including the flag, we have to grep for the flag
## MY SOLUTION:

**Flag** :

```
pwn.college{M7C93Wo5mt-qGQQWsrZYWR0bIVE.QX5EDO0wCMxEzNzEzW}
```

As given in the challenge we need to find the flag using the pipe command and grep therefore, i just used /challenge/run echo pwn.college-pwn.college | grep pwn.college in order to get the flag.
````
hacker@piping~grepping-live-output:~$ /challenge/run echo pwn.college-pwn.college | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{M7C93Wo5mt-qGQQWsrZYWR0bIVE.QX5EDO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about the pipe command and how we can use grep with the pipe command.

## References 
No reference was used for this challenge.


# 8. GREPPING ERRORS:


In this challenge we need to redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal.
## MY SOLUTION:

**Flag** :

```
pwn.college{cu2QTnSXzHvpUguuzS-Ukods4Sh.QX1ATO0wCMxEzNzEzW}
```
As directed, I used /challenge/run 2>&1 to redirect standard error to standard output. Then I used pipe command to grep and got the flag.

````
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{cu2QTnSXzHvpUguuzS-Ukods4Sh.QX1ATO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about >& operator which redirects a file descriptor to another file descriptor.

## References 
No reference was used for this challenge.


# 9. FILTERING WITH GREP-V:


In this challenge we need to use grep -v to filter out all the lines containing "DECOY" and get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{sEHo8jIXyLSgNsmLnHn1L8_4Huf.0FOxEzNxwCMxEzNzEzW}
```
An easy challenge where we had to just -v function.

````
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{sEHo8jIXyLSgNsmLnHn1L8_4Huf.0FOxEzNxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about -v which is used when we want to show lines that do not match a pattern.

## References 
No reference was used for this challenge.


# 10. DUPLICATING PIPED DATA WITH TEE:


In this challenge /challenge/pwn must be piped into /challenge/college, but we'll need to intercept the data to see what pwn needs from us.

## MY SOLUTION:

**Flag** :

```
pwn.college{8kT5GeZCyWBXBTE0Xa7MmvSvs8Y.QXxITO0wCMxEzNzEzW}
```
As the challenge suggests we have to first intercept the data from pwn so I did cat pwn and got the secret_arg as 8kT5GeZC which needed to be used. Then I piped /challenge/pwn into /challenge/college by writing /challenge/pwn --secret 8kT5GeZC | /challenge/college and got the flag

````
hacker@piping~duplicating-piped-data-with-tee:~$ cat pwn
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "8kT5GeZC"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 8kT5GeZC | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{8kT5GeZCyWBXBTE0Xa7MmvSvs8Y.QXxITO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about the tee command, named after a "T-splitter" from plumbing pipes and it performs the function of duplicating data flowing through the pipes to any number of files provided on the command line.

## References 
No reference was used for this challenge.


# 11. PROCESS SUBSTITUTION FOR INPUT:


In this challenge we need to use process substitution with diff to compare the outputs of /challenge/print_decoys and /challenge/print_decoys_and_flag

## MY SOLUTION:

**Flag** :

```
pwn.college{sEHo8jIXyLSgNsmLnHn1L8_4Huf.0FOxEzNxwCMxEzNzEzW}
```
It was an easy challenge where we had to use diff function.

````
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
29a30
> pwn.college{8AWG50yKF-Gv57DKdygYMzNWCQB.0lNwMDOxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I could first understand that Linux follows the philosophy of classifying everything as a file. Then I learnt about process substitution for hooking input and output of programs to arguments of commands. 
## References 
No reference was used for this challenge.

# 12. WRITING TO MULTIPLE PROGRAMS:


In this challenge we need to run the /challenge/hack command, and duplicate its output as input to both the /challenge/the and the /challenge/planet commands.

## MY SOLUTION:

**Flag** :

```
pwn.college{UukGJqX-uYIdXl5wgQ3YJChv2eK.QXwgDN1wCMxEzNzEzW}
```
I used tee command to duplicate the output of /challenge/hack as input to /challenge/the and /challenge/planet.

````
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
21997241411568229068
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{UukGJqX-uYIdXl5wgQ3YJChv2eK.QXwgDN1wCMxEzNzEzW}
hacker@piping~writing-to-multiple-programs:~$ ^C
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{UukGJqX-uYIdXl5wgQ3YJChv2eK.QXwgDN1wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I could understand tee and pipe command in a more better way.

## References 
No reference was used for this challenge.

# 13. SPLIT PIPING stderr and stdout:


In this challenge we have:
/challenge/hack: this produces data on stdout and stderr
/challenge/the: you must redirect hack's stderr to this program
/challenge/planet: you must redirect hack's stdout to this program

## MY SOLUTION:

**Flag** :

```
pwn.college{YgIhQJv3L1cDKsljPhwEVvBfG0w.QXxQDM2wCMxEzNzEzW}
```
To redirect stderr of /challenge/hack to /challenge/the, I used >(/challenge/the) and to redirect stdout of /challenge/hack to /challenge/planet stdout I used the pipe command.

````
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{YgIhQJv3L1cDKsljPhwEVvBfG0w.QXxQDM2wCMxEzNzEzW}
hacker@piping~split-piping-stderr-and-stdout:~$ ^C
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{YgIhQJv3L1cDKsljPhwEVvBfG0w.QXxQDM2wCMxEzNzEzW}
````


## What I learnt
This challenge was an amalgamation of previous concepts we learnt.

## References 
No reference was used for this challenge.

# 14. NAMED PIPES:


In this challenge we have:
/challenge/hack: this produces data on stdout and stderr
/challenge/the: you must redirect hack's stderr to this program
/challenge/planet: you must redirect hack's stdout to this program

## MY SOLUTION:

**Flag** :

```
pwn.college{gami27lwEKqoxeE92E1u_Kx8X_2.01MzMDOxwCMxEzNzEzW}

```
So first I created a fifo file using mkfifo then I redirected the output of /challenge/run to /tmp/flag_fifo. In the other terminal I wrote cat /tmp/flag_fifo to get the flag.

````
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo! 
Bash will now try to open the FIFO for writing, to pass it as the stdout of 
/challenge/run. Recall that operations on FIFOs will *block* until both the 
read side and the write side is open, so /challenge/run will not actually be 
launched until you start reading from the FIFO!


terminal 2


hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{gami27lwEKqoxeE92E1u_Kx8X_2.01MzMDOxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about FIFO which stands for First In First Out. they are named pipes and are useful for facilitating complex data flows, merging and splitting data in flexible ways

## References 
No reference was used for this challenge.

