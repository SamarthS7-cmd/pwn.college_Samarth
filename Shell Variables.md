## 1. PRINTING VARIABLES :


In this challenge we have to use shell to print out the FLAG variable.

## MY SOLUTION:

**Flag** :

```
pwn.college{UORR58zTIA3ryhIok-puda6kt_B.QX3UTN0wCMxEzNzEzW}

```

As given in the challenge we have to use shell to print out the FLAG variable. We can do this by using the varaible with $.
````
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{UORR58zTIA3ryhIok-puda6kt_B.QX3UTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn how we can print variables with the help of $
## References 
No reference was used for this challenge.


## 2. SETTING VARIABLES :


In this challenge we have to set the PWN variable to the value COLLEGE.

## MY SOLUTION:

**Flag** :

```
pwn.college{ELtHfHwNREMGz0JuI8p-Vz1vca0.QX5UTN0wCMxEzNzEzW}

```

We had to set the PWN variable to COLLEGE so I simply wrote PWN=COLLEGE which gave me the flag
````
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{ELtHfHwNREMGz0JuI8p-Vz1vca0.QX5UTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn how we can set variables
## References 
No reference was used for this challenge.

## 3. MULTI-WORD VARIABLES :


In this challenge we 'll need to set the variable PWN to COLLEGE YEAH

## MY SOLUTION:

**Flag** :

```
pwn.college{EtMDLExhl_gflcGHc762Q_L2Nyi.QXwYTN0wCMxEzNzEzW}

```

Another easy challenge where we had to just write PWN="COLLEGE YEAH" to get the flag.
````
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{EtMDLExhl_gflcGHc762Q_L2Nyi.QXwYTN0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I learnt about quoting so that we can set multi-worded variable
## References 
No reference was used for this challenge.


## 4. EXPORTING VARIABLES :


In this challenge we must invoke /challenge/run with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported.

## MY SOLUTION:

**Flag** :

```
pwn.college{UxrL6-FTpQY0iHQJrJMnWei0u6u.QXyYTN0wCMxEzNzEzW}

```

So firstly we have to set the variable PWN to COLLEGE and export that, then we need to set COLLEGE to PWN. Finally print /challenge/run PWN$ to get the flag.
````
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ sh
sh-5.2$ /challenge/run PWN$
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{UxrL6-FTpQY0iHQJrJMnWei0u6u.QXyYTN0wCMxEzNzEzW}

````


## What I learnt
I learnt about the sh, a minimal shell implementation that is invoked as a child of the main shell process and it does not receive the VAR variable. I also learnt about the export command.
## References 
No reference was used for this challenge.


## 5. PRINTING EXPORTED VARIABLES :


In this challenge we 'll need to use the env command which will print out every exported variable set in your shell, and we can look through that output to find the FLAG variable.

## MY SOLUTION:

**Flag** :

```
pwn.college{QhNarWRcspQHKQg-yaUZkmNj-Dr.QX4UTN0wCMxEzNzEzW}
```

We had to just print env command which executed all the exported variables, there I found out the FLAG variable.
````
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=a06ecad28719b05e9e60d07b83bd63a58f032f98fc62913a9ef78ac59821094b
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{QhNarWRcspQHKQg-yaUZkmNj-Dr.QX4UTN0wCMxEzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
````


## What I learnt
I learnt about env command which is one of the commands to access variables in bash.
## References 
No reference was used for this challenge.


## 6. STORING COMMAND OUTPUT :


In this challenge we have to read the output of the /challenge/run command directly into a variable called PWN and get the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{41rbmH1qSyNIuFm_IeHkxq2F1m-.QX1cDN1wCMxEzNzEzW}
```

As given in the challenge first we need to read the output of /challenge/run to a variable PWN. Which can be done with PWN=$(/challenge/run). Then I printed it out to get the flag
````
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{41rbmH1qSyNIuFm_IeHkxq2F1m-.QX1cDN1wCMxEzNzEzW}
````


## What I learnt
I learnt how we can store output of commands into a variable.
## References 
No reference was used for this challenge.

## 7. READING INPUT :


In this challenge we have to use read to set the PWN variable to the value COLLEGE.

## MY SOLUTION:

**Flag** :

```
pwn.college{kecsFFe3P_8gp-daY3YqOkKZeXz.QX4cTN0wCMxEzNzEzW}
```
As asked in the question, I set the PWN variable to COLLEGE using ``` read -p "INPUT: " PWN```

````
hacker@variables~reading-input:~$ read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{kecsFFe3P_8gp-daY3YqOkKZeXz.QX4cTN0wCMxEzNzEzW}
````


## What I learnt
I learnt about the read builtin which reads input into a variable. To do this, I used to -p argument which lets me specify a prompt.

## References 
No reference was used for this challenge.


## 8. READING FILES :


In this challenge we have to read /challenge/read_me into the PWN environment variable.


## MY SOLUTION:

**Flag** :

```
pwn.college{YXh59fFjhmhNLaRqey69u1qUgep.QXwIDO0wCMxEzNzEzW}
```
To read /challenge/read_me into the PWN environment variable, I used the read builtin.

````
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YXh59fFjhmhNLaRqey69u1qUgep.QXwIDO0wCMxEzNzEzW}
````


## What I learnt
I learnt that we can read files using the read command.

## References 
No reference was used for this challenge.
