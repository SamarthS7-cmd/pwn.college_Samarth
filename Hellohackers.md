## 1. INTRO TO COMMANDS:


In this challenge we have to invoke the hello command to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{w3rL_IkrfGVvi_Xt3lFJl6vWaMZ.QX3YjM1wCMxEzNzEzW}
```

I just wrote "hello" to get the flag

````
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{w3rL_IkrfGVvi_Xt3lFJl6vWaMZ.QX3YjM1wCMxEzNzEzW}
````


## What I learnt
Through this module, I learnt how we invoke a command and also learnt that commands are case sensitive
## References 
No reference was used for this challenge.





## 2. INTRO TO ARGUMENTS :


In this challenge, to get the flag, we must run the hello command (NOT the echo command) with a single argument of hackers.

## MY SOLUTION:

**Flag** :

```
pwn.college{8ZwkwWeHxd5INZpVJ2zZL5tam90.QX4YjM1wCMxEzNzEzW}
```


I first understood the basic syntax of a command line, it is mainly composed of command space argument. We call this as the additional data passed to the command.
When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. A good example is that of "echo". Here echo is the command and the argument can be written anything. What it does is that it prints the argument or in a more better way "echoes" all of its arguments back out onto the terminal. I ran the hello command followed by the hackers argument to obtain the flag.

````
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{8ZwkwWeHxd5INZpVJ2zZL5tam90.QX4YjM1wCMxEzNzEzW}
````


## What I learnt
Through this module, I was able to learn and understand about command and arguments, also about there can be multiple arguments to a single command and how the shell parses the input into command and an argument.I was also able to learn about the command echo and how it "echoes" all of its arguments back out onto the terminal.

## References 
No reference was used for this challenge.



## 3. COMMAND HISTORY :


In this challenge we learn that how the shell saves history of the commands that you invoke.here we just have to use out up/down arrow keys to check our histroy of commands where the flag is hidden.

## MY SOLUTION:

**Flag** :

```
pwn.college{kblf8WUMIhVv0yrQYkxWNGwk8nN.0lNzEzNxwCMxEzNzEzW}
```


We just had to use up/down key to get the flag.
````
hacker@hello~command-history:~$ the flag is pwn.college{kblf8WUMIhVv0yrQYkxWNGwk8nN.0lNzEzNxwCMxEzNzEzW}
````


## What I learnt
Through this module, I learnt that the shell has history and we can use up/down arrow keys to check our history of commands in the terminal.

## References 
No reference was used for this challenge.

