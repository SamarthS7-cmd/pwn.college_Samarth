## 1. MATCHING WITH * :


In this challenge, we need to first change your directory to /challenge, but use globbing to keep the argument we need to pass to cd to at most four characters and run /challenge/run for the flag!


## MY SOLUTION:

**Flag** :

```
pwn.college{8-gCCO2NcReGQwUCqy9e33Y18XL.QXxIDO0wCMxEzNzEzW}

```


As given in the question we had to first change the directory so I wrote ``` cd /ch* ``` which also satisfied the condition of having at most four characters. Then I ran /challenge/run to get the flag.

````
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{8-gCCO2NcReGQwUCqy9e33Y18XL.QXxIDO0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn about * glob, it works as when it encounters a * character in any argument, the shell will treat it as a "wildcard" and try to replace that argument with any files that match the pattern.

## References 
No reference was used for this challenge.


## 2. MATCHING WITH ? :


In this challenge, starting from your home directory, we need to change the directory to /challenge, but use the ? character instead of c and l in the argument to cd and then run /challenge/run to get the flag


## MY SOLUTION:

**Flag** :

```
pwn.college{w2IAHDh8SrAVjR4v1Vf_5ageDDL.QXyIDO0wCMxEzNzEzW}
```


As given in the question we had to first change the directory to /challenge but use ? so I wrote ``` cd /?ha??enge``` Then I ran /challenge/run to get the flag.

````
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{w2IAHDh8SrAVjR4v1Vf_5ageDDL.QXyIDO0wCMxEzNzEzW}

````


## What I learnt
Through this challenge, I was able to learn about ? glob. When it encounters a ? character in any argument, the shell will treat it as a single-character wildcard. This works like *, but only matches one character. 

## References 
No reference was used for this challenge.


## 3. MATCHING WITH [] :


In this challenge, we need to change your working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h.

## MY SOLUTION:

**Flag** :

```
pwn.college{kYDkKDliI_cbKaaFi2sSYyH6l1b.QXzIDO0wCMxEzNzEzW}
```

I first changed the directory to /challenge/files, then as in order to find the flag we need to run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h. Threfore, I used /challenge/run file_[bash] in order to get the flag.


````
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{kYDkKDliI_cbKaaFi2sSYyH6l1b.QXzIDO0wCMxEzNzEzW}
````


## What I learnt
I was able to learn about the [] glob, they are essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. For example, [pwn] will match the character p, w, or n.

## References 
No reference was used for this challenge.


## 4. MATCHING PATHS WITH [] :


In this challenge, starting from your home directory, run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files!
## MY SOLUTION:

**Flag** :

```
pwn.college{gjRimEjBYqmvvyf9ke-DhGxhZKw.QX0IDO0wCMxEzNzEzW}
```

I first changed the directory to /challenge/files, then as in order to find the flag we need to run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h. Threfore, I used /challenge/run file_[bash] in order to get the flag.


````
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{gjRimEjBYqmvvyf9ke-DhGxhZKw.QX0IDO0wCMxEzNzEzW}
````


## What I learnt
I was able to learn about the [] glob, globbing happens on a path basis, so you can expand entire paths with your globbed arguments. 

## References 
No reference was used for this challenge.


## 5. MULTIPLE GLOBS :


In this challenge, we have to first cd into /challenge/files and run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.

## MY SOLUTION:

**Flag** :

```
pwn.college{4qtUAijSpdp-aqu28d0b0bTCnHO.0lM3kjNxwCMxEzNzEzW}
```

As mentioned in the challenge, I first changed the directory to  /challenge/files then I wrote /challenge/run *p* which satisified the condition of 3 globbed words containin

````
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ ls
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{4qtUAijSpdp-aqu28d0b0bTCnHO.0lM3kjNxwCMxEzNzEzW}

````


## What I learnt
I was able to learn about the [] glob, globbing happens on a path basis, so you can expand entire paths with your globbed arguments. 

## References 
No reference was used for this challenge.


## 6. MIXING GLOBS :


In this challenge, we have to first cd into /challenge/files and write a single, short (6 characters or less) glob that (when passed as an argument to /challenge/run) will match the files "challenging", "educational", and "pwning"

## MY SOLUTION:

**Flag** :

```
pwn.college{IhwOZm6LYvw6wWc-vi8Oy9Qs4ou.QX1IDO0wCMxEzNzEzW}
```

As mentioned in the challenge, I first changed the directory to  /challenge/files. Just for the hint, I invoked echo look [pce]* which printed challenging, educational and pwning, so I went with the same glob and passed it as an argument to /challenge/run hence got the flag.
````
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~mixing-globs:/challenge/files$ echo look: [pce]*
look: challenging educational pwning
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [pce]*
You got it! Here is your flag!
pwn.college{IhwOZm6LYvw6wWc-vi8Oy9Qs4ou.QX1IDO0wCMxEzNzEzW}

````


## What I learnt
This challenge solely focused on applying all the concepts we have learned before so nothing new was learnt.

## References 
No reference was used for this challenge.


## 5. MULTIPLE GLOBS :


In this challenge, we have to first cd into /challenge/files and run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.

## MY SOLUTION:

**Flag** :

```
pwn.college{4qtUAijSpdp-aqu28d0b0bTCnHO.0lM3kjNxwCMxEzNzEzW}
```

As mentioned in the challenge, I first changed the directory to  /challenge/files then I wrote /challenge/run *p* which satisified the condition of 3 globbed words containin

````
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ ls
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{4qtUAijSpdp-aqu28d0b0bTCnHO.0lM3kjNxwCMxEzNzEzW}

````


## What I learnt
I was able to learn about the [] glob, globbing happens on a path basis, so you can expand entire paths with your globbed arguments. 

## References 
No reference was used for this challenge.


## 7. EXCLUSIONARY GLOBS :


In this challenge, we had to cd to /challenge/files and then do /challenge/run with all the files that don't start with p,w or n.

## MY SOLUTION:

**Flag** :

```
pwn.college{4vmC9dz3oKnSMcd1DTvRJUR1vct.QX2IDO0wCMxEzNzEzW}
```
As done in the previous challenges, I first went into /challenge/files and did ls to see all the files. Then I wrote a simple code /challenge/run [!pwn]* which ran all the files except those starting with p,w and n.

````
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ ls
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{4vmC9dz3oKnSMcd1DTvRJUR1vct.QX2IDO0wCMxEzNzEzW}


````


## What I learnt
In this challenge I learnt about exclusionary globs, [!] helps in filtering out the globs we dont need.

## References 
No reference was used for this challenge.


## 8. TAB COMPLETION :

In this challenge the flag is copied into /challenge/pwncollege, and then we can freely cat that file. But we can't type the file name.

## MY SOLUTION:

**Flag** :

```
pwn.college{41aXaBG-_vKlAL_l43iAl3wpe4r.0FN0EzNxwCMxEzNzEzW}
```
To solve this challenge, I did cd /challenge first. As mentioned we can cat the file but can't type the name so I wrote cat /challenge/<pwn tab> to complete the fie.

````
hacker@globbing~tab-completion:~$ cd /challenge
hacker@globbing~tab-completion:/challenge$ cat /challenge/pwncollege​ 
pwn.college{41aXaBG-_vKlAL_l43iAl3wpe4r.0FN0EzNxwCMxEzNzEzW}

````


## What I learnt
In this challenge I learnt tab completion. If you hit tab in the shell, it'll try to figure out what you're going to type and automatically complete it. Auto-completion is super useful, and this challenge will explore its use in specifying files.

## References 
No reference was used for this challenge.


## 9. MULTIPLE OPTIONS FOR TAB COMPLETION :

In this challenge /challenge/files directory with a bunch of files starting with pwncollege. We have to use Tab from pwn to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{YSYaKAI_qhdEEmG_T2H9yiR5MW5.0lN0EzNxwCMxEzNzEzW}
```
As done in the previous challenges, I did cd /challenge first. As mentioned we can cat the file so I wrote cat /challenge/files/pwn, I could see the list of files. Then I printed cat /challenge/files/pwncollege-flag to get the flag.

````
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge
hacker@globbing~multiple-options-for-tab-completion:/challenge$ /challenge/files
bash: /challenge/files: Is a directory
hacker@globbing~multiple-options-for-tab-completion:/challenge$ ls
No ls for you in this level! Use tab-completion instead!
hacker@globbing~multiple-options-for-tab-completion:/challenge$ cat /challenge/files/pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter  
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking     
hacker@globbing~multiple-options-for-tab-completion:/challenge$ cat /challenge/files/pwncollege-flag
pwn.college{YSYaKAI_qhdEEmG_T2H9yiR5MW5.0lN0EzNxwCMxEzNzEzW}


````


## What I learnt
In this challenge I learnt about multiple options for tab completion. By default bash will auto-expand until the first point when there are multiple options (in this case, fl). When you hit tab a second time, it'll print out those options. Other shells and configurations, instead, will cycle through the options.

## References 
No reference was used for this challenge.


## 10. TAB COMPLETION ON COMMANDS :

In this challenge we need to type pwncollege and hit the tab key to auto-complete it.

## MY SOLUTION:

**Flag** :

```
pwn.college{MO49a9u_BVZNKkLi-p5brA4F3d8.0VN0EzNxwCMxEzNzEzW}

```
We had to just type pwncollege and press tab key so that it generates the number and completes the challenge.

````
hacker@globbing~tab-completion-on-commands:~$ pwncollege-26645 
Correct! Here is your flag:
pwn.college{MO49a9u_BVZNKkLi-p5brA4F3d8.0VN0EzNxwCMxEzNzEzW}


````


## What I learnt
Through this challenge, I understood that we can tab complete commands also.
## References 
No reference was used for this challenge.
