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

