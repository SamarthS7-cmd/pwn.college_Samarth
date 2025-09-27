
## INTRO TO ARGUMENTS :


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
