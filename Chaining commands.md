# 1. Chaining with semicolons :


 In this challenge, we must run /challenge/pwn and then /challenge/college, chaining them with a semicolon.
 
## MY SOLUTION:

**Flag** :

```
pwn.college{EqQ7Nsg7ncvI0ywBKq5zAYCskvN.QX1UDO0wCMxEzNzEzW}

```

Simple challenge where we had to just use semicolon to chain two commands.

````
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{EqQ7Nsg7ncvI0ywBKq5zAYCskvN.QX1UDO0wCMxEzNzEzW}
````


## What I learnt
I learnt how we can use semicolon to join two commands.
## References 
No reference was used for this challenge.




# 2. Building on Success :


In this challenge, we need to chain the programs /challenge/first-success and /challenge/second using the && operator. 
 
## MY SOLUTION:

**Flag** :

```
pwn.college{ox9yt4Zy8raIICS3qxNIRXbXzgY.0lM0MDOxwCMxEzNzEzW}

```

Simple challenge where we had to use && to chain two commands.

````
hacker@chaining~building-on-success:~$  /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{ox9yt4Zy8raIICS3qxNIRXbXzgY.0lM0MDOxwCMxEzNzEzW}
````


## What I learnt
I learnt how we can use && to join two commands and it runs the second command only if the first command succeeds.
## References 
No reference was used for this challenge.



# 3. Handling Failure:


In this challenge, we need to chain /challenge/first-failure and /challenge/second using the || operator.  
 
## MY SOLUTION:

**Flag** :

```
pwn.college{MszAGQ6L_nVOIAcAIK69NH-0_DX.01M0MDOxwCMxEzNzEzW}

```

We had to use || to chain two commands.

````
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{MszAGQ6L_nVOIAcAIK69NH-0_DX.01M0MDOxwCMxEzNzEzW}
````


## What I learnt
I learnt how we can use || to join two commands.
## References 
No reference was used for this challenge.



# 4. Your first shell script:


In this challenge, we have to run /challenge/pwn and then /challenge/college, but this time in a shell script called x.sh, then run it with bash
 
## MY SOLUTION:

**Flag** :

```
pwn.college{gsYrKQ3JVCwedk11hkJffng0CIs.QXxcDO0wCMxEzNzEzW}
```

I used GNU nano text editor and wrote /challenge/pwn , /challenge/college there and saved it. Then ran bash x.sh to get the flag

````
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{gsYrKQ3JVCwedk11hkJffng0CIs.QXxcDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about shell scripts and how we can put commands into a file. I also learnt about nano text editor.
## References 
No reference was used for this challenge.



# 5. Redirecting Script Output:


In this challenge we need to create a script that calls the /challenge/pwn command followed by the /challenge/college command, and pipe the output of the script into a single invocation of the /challenge/solve command.
 
## MY SOLUTION:

**Flag** :

```
pwn.college{YOH-1DpJoGYg5bDWnFSJ6ZG1GQ6.QX4ETO0wCMxEzNzEzW}
```

I used GNU nano text editor again and wrote /challenge/pwn , /challenge/college there and saved it. Then ran bash flag.sh | /challenge/solve to get the flag.

````
hacker@chaining~redirecting-script-output:~$ nano flag.sh
hacker@chaining~redirecting-script-output:~$ bash flag.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{YOH-1DpJoGYg5bDWnFSJ6ZG1GQ6.QX4ETO0wCMxEzNzEzW}
````


## What I learnt
This challenge was a practice of other concepts.
## References 
No reference was used for this challenge.



# 6. Executable Shell Scripts:


In this challenge we have to make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash.

## MY SOLUTION:

**Flag** :

```
pwn.college{c-jYDwZoxO0pO95RifIg33Kt3_k.QX0cjM1wCMxEzNzEzW}
```

I first made a shell script using nano and saved /challenge/solve in that. Then I ran ls and saw that write permission was missing so I wrote chmod 777 script.sh which gave the required permission. 

````
hacker@chaining~executable-shell-scripts:~$ nano script.sh
hacker@chaining~executable-shell-scripts:~$ chmod 777 script.sh
hacker@chaining~executable-shell-scripts:~$ ./script.sh
Congratulations on your shell script execution! Your flag:
pwn.college{c-jYDwZoxO0pO95RifIg33Kt3_k.QX0cjM1wCMxEzNzEzW}
````


## What I learnt
This challenge was a practice of other concepts.
## References 
No reference was used for this challenge.




# 7. Understanding Shebangs:


In this challenge we have to create a script at /home/hacker/solve.sh that has a proper shebang and outputs "hack the planet". We have to make it executable, then run /challenge/run to verify

## MY SOLUTION:

**Flag** :

```
pwn.college{82ijASm-jJWVpF85AJQp-n14Lec.0VOzMDOxwCMxEzNzEzW}
```

I created a script /home/hacker/solve.sh using nano then I wrote #!/bin/bash, echo hack the planet and saved it. Then I did the same thing done in previous challenges to get the flag.

````
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ ls -l solve.sh
-rwxrwxrwx 1 hacker hacker 33 Oct 10 18:48 solve.sh
hacker@chaining~understanding-shebangs:~$ chmod 777 solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{82ijASm-jJWVpF85AJQp-n14Lec.0VOzMDOxwCMxEzNzEzW}

````


## What I learnt
I learnt about shebang which is a term used for program files that starts with the characters #!.
## References 
No reference was used for this challenge.




# 8. Scripting with Arguments:


In this challenge we need to write a script at /home/hacker/solve.sh that:
Takes two arguments
Outputs them in REVERSE order (second argument first, then the first argument)

## MY SOLUTION:

**Flag** :

```
pwn.college{AYXEsa1gB3ENP8Wj5BJOkMt-3an.0VNzMDOxwCMxEzNzEzW}
```

I created a script /home/hacker/solve.sh using nano then I wrote #!/bin/bash, echo $2 $1 and saved it. Then I did the same thing done in previous challenges to get the flag.

````
hacker@chaining~scripting-with-arguments:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ chmod 777 solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{AYXEsa1gB3ENP8Wj5BJOkMt-3an.0VNzMDOxwCMxEzNzEzW}

````


## What I learnt
I learnt that the script can access arguments using special variables like $1 contains the first argument and so on.
## References 
No reference was used for this challenge.


# 9. Scripting with Conditionals:


In this challenge we have to write a script at /home/hacker/solve.sh that:
Takes one argument
If the argument is "pwn", output "college"
For any other input, output nothing

## MY SOLUTION:

**Flag** :

```
pwn.college{EXJR724khRSLeUkKATfDiDQ9bwG.0lNzMDOxwCMxEzNzEzW}
```

I created a script /home/hacker/solve.sh using nano then I wrote #!/bin/bash, if [ "$1" == "pwn" ]
then
    echo "college"
fi
and saved it. Then I did the same thing done in previous challenges to get the flag.

````
hacker@chaining~scripting-with-conditionals:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ ./solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{EXJR724khRSLeUkKATfDiDQ9bwG.0lNzMDOxwCMxEzNzEzW}

````


## What I learnt
I learnt that we can use if else in script.
## References 
No reference was used for this challenge.



# 10. Scripting with Deafult Cases:


In this challenge we have to write a script at /home/hacker/solve.sh that:
Takes one argument
If the argument is "pwn", output "college"
For any other input, output nothing

## MY SOLUTION:

**Flag** :

```
pwn.college{o4njO-vNa8Bm9oD0XlzSkncGIhh.01NzMDOxwCMxEzNzEzW}
```

I created a script /home/hacker/solve.sh using nano then I wrote #!/bin/bash, if [ "$1" == "pwn" ]
then
    echo "college"
else
    echo "nope"
fi
and saved it. Then I did the same thing done in previous challenges to get the flag.

````
hacker@chaining~scripting-with-default-cases:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ ./solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ ./solve.sh hack
nope
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{o4njO-vNa8Bm9oD0XlzSkncGIhh.01NzMDOxwCMxEzNzEzW}

````


## What I learnt
I learnt how we can use differential conditionals in script.
## References 
No reference was used for this challenge.



# 11. Scripting with Multiple Conditions:


In this challenge we have to write a script at /home/hacker/solve.sh that:
Takes one argument
If the argument is "pwn", output "college"
For any other input, output nothing

## MY SOLUTION:

**Flag** :

```
pwn.college{QiZmLD-fzUkQ5-ohrDR7naactLt.0FOzMDOxwCMxEzNzEzW}
```

I created a script /home/hacker/solve.sh using nano then I wrote #!/bin/bash,
if [ "$1" == "hack" ]
then
    echo "the planet"
elif [ "$1" == "pwn" ]
then
    echo "college"
elif [ "$1" == "learn" ]
then
    echo "linux"
else
    echo "unknown"
fi
and saved it. Then I did the same thing done in previous challenges to get the flag.

````
hacker@chaining~scripting-with-multiple-conditions:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ ./solve.sh hack
the planet
hacker@chaining~scripting-with-multiple-conditions:~$ ./solve.sh pwn
college
hacker@chaining~scripting-with-multiple-conditions:~$ ./solve.sh learn
linux
hacker@chaining~scripting-with-multiple-conditions:~$ ./solve.sh foo
unknown
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{QiZmLD-fzUkQ5-ohrDR7naactLt.0FOzMDOxwCMxEzNzEzW}
````


## What I learnt

## References 
No reference was used for this challenge.



# 12. Reading Shell Scripts:


In this challenge we have to write a script at /home/hacker/solve.sh that:
Takes one argument
If the argument is "pwn", output "college"
For any other input, output nothing

## MY SOLUTION:

**Flag** :

```
pwn.college{o4njO-vNa8Bm9oD0XlzSkncGIhh.01NzMDOxwCMxEzNzEzW}
```

I first opened /challenge/run then I understood that password is hack the PLANET so I entered that and got the flag.

````
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
pwn.college{46FKCHWxpY0LamjIGf0J5W3-9nA.0lMwgDOxwCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to read how we can read shell scripts.
## References 
No reference was used for this challenge.
