# 1. Launching screen :


 In this challenge, we have to launch the screen to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{EowtheoENZrNsDxCBSLRxHE13OV.0VN4IDOxwCMxEzNzEzW}

```

A simple challenge where I just wrote screen and got the flag.

````
hacker@terminal-multiplexing~launching-screen:~$ screen
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{EowtheoENZrNsDxCBSLRxHE13OV.0VN4IDOxwCMxEzNzEzW}
````


## What I learnt
I learnt about screen in linux terminal, it is a program that creates virtual terminals inside your terminal. It's somewhat like having multiple browser tabs.
## References 
No reference was used for this challenge.




# 2. Detaching and Attaching :


For this challenge, we'll need to:

1.Launch screen
2.Detach from it.
3.Run /challenge/run (this will secretly send the flag to our detached session)
4.Reattach to get the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{cTR9lZjBR8sHYJncXm7PdpgimJL.0lN4IDOxwCMxEzNzEzW}

```

I just followed the step by step procedure as mentioned in the code below and got the flag.

````
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
hacker@terminal-multiplexing~detaching-and-attaching:~$ ctrl + A then d
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo
Yes! Flag is: pwn.college{cTR9lZjBR8sHYJncXm7PdpgimJL.0lN4IDOxwCMxEzNzEzW}
````


## What I learnt
I learnt about how we can dettach and attach a screen in linux. Dettaching can be done by ctrl-A d and attaching can be done by writing screen -r.
## References 
No reference was used for this challenge.



# 3. Finding Sessions :


In this challenge, three screen sessions have been created. One of them contains the flag. The other two are decoys

## MY SOLUTION:

**Flag** :

```
pwn.college{UqpAGK8-TmobLaaWqx4374FKDqI.01N4IDOxwCMxEzNzEzW}

```

I first listed all the sessions in screen and then attached the correct session to get the flag

````
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -ls
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r "session"
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{UqpAGK8-TmobLaaWqx4374FKDqI.01N4IDOxwCMxEzNzEzW}
pwn.college{UqpAGK8-TmobLaaWqx4374FKDqI.01N4IDOxwCMxEzNzEzW}
````


## What I learnt
I learnt how we can list screen sessions that are currently preesent in our terminal.
## References 
No reference was used for this challenge.



# 4. Switching Windows :

In this challenge, two screen sessions with two windows have been set up. We need to attach to the session then use one of the key combinations to switch to Window 1.

## MY SOLUTION:

**Flag** :

```
pwn.college{ELgNGfWYtdXCcpWN0ZKNcBkcZZp.0FO4IDOxwCMxEzNzEzW}

```

As done in the previous challenge, I listed all the sessions in the screen then attached challenge_session. Then I used ctrl-A 0 to switch the window from 1 to 0 and got the flag.

````
hacker@terminal-multiplexing~switching-windows:~$ screen -ls
There are screens on:
        158.pts-0.terminal-multiplexing~launching-screen        (Remote or dead)
        188.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        214.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        148.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_c965cbbc0975848e    (Remote or dead)
        147.session_71c8358bfcb55084    (Remote or dead)
        150.session_a7687f687417b4c9    (Remote or dead)
        147.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_536fd0c208b504b6    (Remote or dead)
        147.session_c464bc61e1a2ae9e    (Remote or dead)
        150.session_e64a3c16e0f3b871    (Remote or dead)
        144.session_99c198eceec5fcac    (Remote or dead)
        147.session_198df031393981d9    (Remote or dead)
        150.session_69004c73e499e06e    (Remote or dead)
        144.session_baca7db33e2e622e    (Remote or dead)
        147.session_14d712da29358b4a    (Remote or dead)
        150.session_396b48dfc2ba3bc2    (Remote or dead)
        144.session_4ad8d23eec12a199    (Remote or dead)
        147.session_6673d96b7ec36f8e    (Remote or dead)
        150.session_a3b6f758c0fcb9e6    (Remote or dead)
        145.session_f0a81e230be80da1    (Remote or dead)
        148.session_5821f26f8c54d1c8    (Remote or dead)
        151.session_65795defb99976d0    (Remote or dead)
        135.challenge_session   (Detached)
24 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~switching-windows:~$ screen -r challenge_session
 cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!

hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{ELgNGfWYtdXCcpWN0ZKNcBkcZZp.0FO4IDOxwCMxEzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{ELgNGfWYtdXCcpWN0ZKNcBkcZZp.0FO4IDOxwCMxEzNzEzW}
````


## What I learnt
I learnt how we can use different keyboard shortcuts in screen session.
## References 
No reference was used for this challenge.




# 5. Detaching and Attaching (tmux) :


This challenge is similar to the 2nd one just that we are using tmux here.

## MY SOLUTION:

**Flag** :

```
pwn.college{c3xeJrOzvwwBubW_KXHcU5twkwO.0VO4IDOxwCMxEzNzEzW}

```

Firstly I launched tmux and then used ctrl-B d to detach the screen then ran /challenge/run and finally attached the screen to get the flag.

````
hacker@terminal-multiplexing~detaching-and-attaching-tmux: tmux
hacker@terminal-multiplexing~detaching-and-attaching-tmux: ctrl + B then d
hacker@terminal-multiplexing~detaching-and-attaching-tmux: /challenge/run
hacker@terminal-multiplexing~detaching-and-attaching-tmux: tmux a
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ Congratulations, here is your flag: pwn.college{c3xeJrOzvwwBubW_KXHcU5twkwO.0VO4IDOxwCMxEzNzEzW}

````


## What I learnt
I learnt about tmux(terminal multiplexer) which is the modern version of screen and does the same function but through different key bindings.
## References 
No reference was used for this challenge.



# 6. Switiching Windows (tmux) :


This challenge is similar to the 4thd one just that we are using tmux here.

## MY SOLUTION:

**Flag** :

```
pwn.college{wbWWC8wJKuCFRhP0tNkmSfANBuK.0FM5IDOxwCMxEzNzEzW}

```

Firstly I launched tmux and then used ctrl-B d to detach the screen then attached challenge_session got the flag.

````
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux
hacker@terminal-multiplexing~switching-windows-tmux:~$ ctrl + b d
[detached (from session 1)]
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux attach -t challenge_session
[detached (from session challenge_session)]
ctrl + b + 0
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{wbWWC8wJKuCFRhP0tNkmSfANBuK.0FM5IDOxwCMxEzNzEzW}
````


## What I learnt
I learnt about different key combinations used in tmux.
## References 
No reference was used for this challenge.
