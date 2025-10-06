# 1. Translating Characters :


In this challenge, /challenge/run will print the flag but will swap the casing of all characters. We have to undo it with tr and get the flag


## MY SOLUTION:

**Flag** :

```
pwn.college{cZ0yiXkhdus-W7ug66u0Jqz2zbD.01MxEzNxwCMxEzNzEzW}

```

As given, I first printed /challenge/run which gave the flag in PWN.COLLEGE, so I used tr command to change it to pwn.college. We had to replace "A-Z" with "a-z" and vice versa.
````
hacker@data~translating-characters:~$ /challenge/run
Your case-swapped flag:
PWN.COLLEGE{Cz0YIxKHDUS-w7UG66U0jQZ2ZBd.01mXeZnXWcmXeZnZeZw}

hacker@data~translating-characters:~$ echo PWN.COLLEGE{Cz0YIxKHDUS-w7UG66U0jQZ2ZBd.01mXeZnXWcmXeZnZeZw} | tr ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
pwn.college{cZ0yiXkhdus-W7ug66u0Jqz2zbD.01MxEzNxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about the tr command which is the short form for translate. It translates characters it receives over standard input and prints them to standard output.
## References 
No reference was used for this challenge.


# 2. Deleting Characters :


In this challenge, the flag characters will be interspersed with some decoy characters (specifically: ^ and %). We have to use tr -d to remove them.


## MY SOLUTION:

**Flag** :

```
pwn.college{4EeSq86nlViqRJFmxwvlYQVthdH.0FNxEzNxwCMxEzNzEzW}
```

Fairly simple challenge where we had to first print the character stuffed flag then I could identify that it was laden with % and ^ so I used echo "flag" | tr -d % and echo "flag" | tr -d ^ to get the final flag.
````
hacker@data~deleting-characters:~$ /challenge/run
Your character-stuffed flag:
pw%n%.%c%o^%l^%le%g^%e%{4^%E^eSq8^%6n%l^%Vi%qR^J%F%m^%x%w^%v^l^Y^Q^Vt%h%d%H^%.^0FN%x^%E%zN^x^w^C^M%xE%z^%N^z^%Ez^%W^%}^^
hacker@data~deleting-characters:~$ echo pw%n%.%c%o^%l^%le%g^%e%{4^%E^eSq8^%6n%l^%Vi%qR^J%F%m^%x%w^%v^l^Y^Q^Vt%h%d%H^%.^0FN%x^%E%zN^x^w^C^M%xE%z^%N^z^%Ez^%W^%} | tr -d % ^
tr: extra operand ‘^’
Only one string may be given when deleting without squeezing repeats.
Try 'tr --help' for more information.
hacker@data~deleting-characters:~$ echo ^C
hacker@data~deleting-characters:~$ echo pw%n%.%c%o^%l^%le%g^%e%{4^%E^eSq8^%6n%l^%Vi%qR^J%F%m^%x%w^%v^l^Y^Q^Vt%h%d%H^%.^0FN%x^%E%zN^x^w^C^M%xE%z^%N^z^%Ez^%W^%}^^ | tr -d %
pwn.co^l^leg^e{4^E^eSq8^6nl^ViqR^JFm^xw^v^l^Y^Q^VthdH^.^0FNx^EzN^x^w^C^MxEz^N^z^Ez^W^}^^
hacker@data~deleting-characters:~$ echo pwn.co^l^leg^e{4^E^eSq8^6nl^ViqR^JFm^xw^v^l^Y^Q^VthdH^.^0FNx^EzN^x^w^C^MxEz^N^z^Ez^W^}^^ | tr -d ^
pwn.college{4EeSq86nlViqRJFmxwvlYQVthdH.0FNxEzNxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt that tr command can also be used for deleting characters.
## References 
No reference was used for this challenge.


# 3. Deleting newlines :


In this challenge, a bunch of newlines will be injected into the flag. We have to delete them with tr's -d flag and the escaped newline specification.


## MY SOLUTION:

**Flag** :

```
pwn.college{0so2QHnSRfXJYI-P5xwVTQf4_L7.0VNxEzNxwCMxEzNzEzW}
```

Fairly simple challenge where we had to first print the line split flag through /challenge/run, then I used tr -d "\n" which deleted new lines and gave the flag on a single line.
````
hacker@data~deleting-newlines:~$ /challenge/run
Your line-split flag: 
p
wn.c
o
l
l
e
g
e
{0so
2QHn
S
Rf
X
J
Y
I
-
P
5x
w
V
T
Qf4_L7
.0
VNxEz
Nx
w
C
M
xE
z
Nz
E
z
W}
hacker@data~deleting-newlines:~$ echo "p
wn.c
o
l
l
e
g
e
{0so
2QHn
S
Rf
X
J
Y
I
-
P
5x
w
V
T
Qf4_L7
.0
VNxEz
Nx
w
C
M
xE
z
Nz
E
z
W}" | tr -d "\n"
pwn.college{0so2QHnSRfXJYI-P5xwVTQf4_L7.0VNxEzNxwCMxEzNzEzW}
````


## What I learnt
I learnt that \n is a standin for this newline, and it must be used in quotes to prevent the shell interpreter itself from trying to interpret it.
## References 
No reference was used for this challenge.



 # 4. Extracting the first lines with head :


In this challenge, /challenge/pwn outputs a bunch of data, and we'll need to pipe it through head to grab just the first 7 lines and then pipe them onwards to /challenge/college in order to get the flag.


## MY SOLUTION:

**Flag** :

```
pwn.college{ELsQqn2MKQHngNw-bSzS-Hr9H9A.0lNxEzNxwCMxEzNzEzW}
```

Fairly simple challenge where we had to use the head command to print the first 7 lines of /challenge/pwn, then I piped them to /challenge/college to get the flag.
````
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{ELsQqn2MKQHngNw-bSzS-Hr9H9A.0lNxEzNxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about the head command. The head command is used to display the first few lines of its input. By default it prints the first 10 lines but this can be edited by writing ``` -n (number) ```
## References 
No reference was used for this challenge.



 # 5. Extracting specific sections of text:


In this challenge, the /challenge/run program will give a bunch of lines with random numbers and single characters (characters of the flag) as columns. We have to use cut to extract the flag characters, then pipe them to tr -d "\n" (like the previous level!) to join them together into a single line. 

## MY SOLUTION:

**Flag** :

```
pwn.college{serXxjzYoW37VAUTiSm_-Q0dfSG.01NxEzNxwCMxEzNzEzW}
```

So first I ran /challenge/run to check out the lines, then I could see that cutting the 2nd column will help in printing the flag but it will be line split so I further used tr -d "\n" to print the flag in single line. 
````
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
27888 p
8071 w
6503 n
27967 .
29064 c
21354 o
27411 l
13509 l
12144 e
26702 g
32430 e
29143 {
55 s
7842 e
23751 r
17934 X
20452 x
8579 j
10611 z
27610 Y
23468 o
11459 W
28921 3
2770 7
8375 V
30204 A
5273 U
30437 T
21571 i
434 S
27332 m
7764 _
7652 -
27364 Q
19355 0
25592 d
26339 f
19841 S
24578 G
18669 .
21995 0
25407 1
20964 N
27542 x
19494 E
910 z
30466 N
15548 x
29818 w
3029 C
25039 M
26759 x
10394 E
11967 z
13165 N
21644 z
28764 E
16990 z
14946 W
31802 }
hacker@data~extracting-specific-sections-of-text:~$ cut -d " " -f 2 /challenge/run
#!/opt/pwn.college/bash

/flag

done
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{serXxjzYoW37VAUTiSm_-Q0dfSG.01NxEzNxwCMxEzNzEzW}
````


## What I learnt
I learnt about the cut command and how it used to extract a specific coloumn form the data.
## References 
No reference was used for this challenge.


 # 6. Sorting data:


In this challenge, there's a file at /challenge/flags.txt containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be at the end.

## MY SOLUTION:

**Flag** :

```
pwn.college{44odDIqdCh-s4tqISq0gVsVYi9K.0FM0MDOxwCMxEzNzEzW}
```

A simple challenge where we had to use the sort command directly to print the flags in alphabetical order, the last flag was the correct one.
````
hacker@data~sorting-data:~$ sort /challenge/flags.txt
ovm.bokkefd{34odCHqdCg-s4spISp0gVsUYh9K.0EM0MDOxwBMxEyNyEzV}
ovm.cnllege{34odDIqdCh-s4tqISq0gUsVYi8K.0FM0MDOwwCMxEzMzEzW}
ovn.bnklege{44odCIqcCh-s3tqHSq0gUrVXi8K.0FM0LDNxwCMxDzMzEzV}
ovn.cnklefe{33odDIqdCg-r4tqISp0gVsVYi9J.0FM0MCOxvCMwEyMzEzV}
ovn.cokldfe{44odDIpcBh-r4tqHSq0fVsVYi8K.0FL0LDOwwCMwEzNzEyV}
ovn.college{44odDIqdCh-s4tqHSq0fUsUYi8K.0FM0MDNxwBMxEzNyEzW}
owm.bollefe{43ocDIpdCh-r3tqISq0gVsVYi9K.0EL0LDOxwBMwEzMzEzW}
owm.college{44odCHpdCh-r4spISq0gVrVYi8K.0FM0MCOwwCMxEzNzDyW}
own.bnllefe{44ocDHpdBh-s3tpISq0gVsUYh9J.0FL0MDNxwCLxEzMzEzW}
own.bnllege{43ndDHpdBg-s4spHRp0gVsVYi9K.0FL0MCOwwCMxDyNzDyV}
own.bokkegd{43ocCIqdCh-r4tqIRq0fVsVYi9J.0FM0MDNxwCMxDzNzDzW}
own.bolldfe{44odCHpdCg-s4tpHSq0gVsVYi9J.0FM0MDNxwCLwEzMzDyV}
own.bolldgd{44odCIpcCh-s3sqIRq0fVsVXi9J.0FM0MDOxwBMxEyNzEzW}
own.bollege{34odCHpdCg-r4tpISq0gVsVYi8J.0FM0MCOwvCMwDzNyEzW}
own.coklege{44odDIqdCh-s4tqISq0gVrUYi9K.0FL0MCOxwCMxEzNzEzW}
own.collefe{44ndCIqdCh-s4sqISp0gVsUYi8K.0FM0LDOxwCLxDyNzEzW}
own.collefe{44odDIqdCh-r4tqISq0gVrVYi8K.0FM0MDOxwCMxEyNzDzW}
own.college{33ndCHqdBg-s4tqISp0fVrUYh9K.0EM0MDOwwCMwDzNzDyW}
own.college{44ndDIqdCh-r4sqHSq0gUsVYi9K.0FM0MDNxwCLwEzNyDzW}
pvm.bnlldgd{43ndCIqdBh-r3tqHRq0fVsUYi8K.0EL0MCOwwCMxEyMzEyW}
pvm.cnlkefe{43ndDHpdCh-r3tqISq0gVrVYh9J.0FM0LCOxwBMwDyNzEyW}
pvm.cnllegd{44odCIqdCg-s4spHSq0fUrVXi9K.0EL0MDOwwBMxEyNzEzW}
pvm.cnllege{44odDHqdBh-s4sqISq0gUsVYh9K.0FM0LDNwwCMwDzNzDyV}
pvm.colkege{44ncDIqdCh-s3tqHSq0gUsVYi9K.0FM0MCNxwCLxEzNzEyW}
pvm.colldfd{44odDHpdBg-r4tqISp0gUsUXi9K.0FL0MCOwwCMwEyMzEzW}
pvn.bokkegd{43ocCIpcBh-s4tqHRq0gVsVYi8K.0FL0MCOxwCLxEzNzDzW}
pvn.cnkkege{44ocCHqdBh-s3tpIRq0gUsVYi9K.0FM0LCOxvBMxDyMyEyV}
pvn.coklege{33odCIpdCg-s4tpISq0gVsVYi9K.0EM0LDOxwCMxEyNzDzW}
pvn.colkege{44odCIpcCh-s4sqISq0gUsUXi8K.0FM0LDNwvCMxDzNyDyW}
pvn.colldge{43odCIpdBh-s3sqISq0fVrUXi9K.0EL0LDNxwBMxDzNzEzW}
pvn.colldge{44ndDIqdCh-s4tqISq0gVrVYi9K.0FM0MDOxwCMxEzNzEzW}
pvn.colldge{44odDIqdCh-s4tqIRq0gVsUXi9K.0FM0MCOxwBMxEzNyEzW}
pvn.collegd{44ncCIqcCg-s4tpHSq0gUsUXi8K.0EL0MCNxwBMxEzNyDyW}
pvn.college{33odDIpdCh-s3tqISq0gVrVYi9J.0FM0MDOxwBMxEzNzEyW}
pwm.bnllegd{43ocCIpdBg-s4spISp0fVrVYi8K.0FM0MDNxwBMwEzNyEyV}
pwm.bnllegd{44ndDIqcBh-r4sqIRp0gUrVYi9J.0FM0LDOxwBLxEzNyEzW}
pwm.bolldgd{44odDHpcCg-s3tqISq0fUsVYi8K.0EL0MDOxwBLwDzNyEzW}
pwm.bollege{43ocCIpdCg-s4sqISp0gVsVYi9J.0EM0MDNxwCMxDyMzEzW}
pwm.cnklege{44ocDIqcBg-s4spISp0gUrUYi9K.0FM0MDOxvBMxEzNzEzW}
pwm.cnllege{44odDHqdCg-r3tqISp0gUsUYi8K.0FM0LCOxwCLxDyMyEyW}
pwm.cnllege{44odDIqdCh-s4sqIRq0gVsVYi9J.0FM0MCOwwCLxEzNzEzW}
pwm.coklefe{44odDIqdBh-s4tqISq0gVsVYi9K.0FM0MDOxwCMwDzNyEzW}
pwm.coklege{34odDHqdCg-r3tqHSp0fVsUYi9K.0FL0MCNxvCMwEzMyDyW}
pwm.colkdfd{34odDIpcCh-s4tpHSq0gUsUYh8K.0FL0LCNwvCMwEzNzDzW}
pwm.colkege{43odDIpcBh-s4sqIRq0gUrUYi9K.0EM0MCNxwCLxEyMzEyW}
pwm.colldge{44odDIqdCh-r4tqIRq0gVsVYh9K.0FL0MDOxvBMxDzNzEzW}
pwm.collefe{44odDIqdCh-s4tqISq0gVsUYi9K.0FM0MDOxvCMxDzNzEyW}
pwm.college{33odDIqdCh-s4tqISq0gVsVYi9K.0FM0MCOxwCMxEzNzEzW}
pwn.bnlkefe{44ocCIqdBh-s4spHRp0gVsUXi8K.0FM0MCOxwCMxEyMyEyW}
pwn.bokkege{33odDIqcBh-s3tqIRp0gVsUXi9K.0FM0MDOwwCLwEzMzEzV}
pwn.bolkdge{34odDIpdCh-s3tpISp0gVsVYh9K.0FM0LCOwwCMwDzMzEzW}
pwn.bolkege{44odDHpcBh-s3tqHRp0gVsVXh8J.0FM0MDOxwCMxEzNzDzV}
pwn.cnlkege{44ndCIqdBh-s4sqIRq0gVsUXi9J.0EM0MCNxwCMxDyNzEzW}
pwn.cnllefe{34odDIqdBg-r3tpISq0gVsUYi8J.0EM0MDNxwCMwDyNzEzV}
pwn.cnllefe{44ndDHqdCh-r4sqISq0gVsVXi9J.0FL0LCNxwBMwEyNzEzV}
pwn.cnllege{34odDIpdCh-s3spISq0fVrUYi8K.0FM0LCNxwCMwEzNzDzW}
pwn.cnllege{43odDIqdCh-s4tpISq0gVsVYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.cnllege{43odDIqdCh-s4tqHSq0fVsVYi9K.0FL0MDOxwCMxEzNzEzW}
pwn.cokkdge{43ocDIqdBh-s4tqHSq0gVsVXi8K.0EM0MDOwvCMwEyMzEzW}
pwn.coklege{43odDIqdCh-s4tqIRq0gVrUYi9J.0FM0MDOxwCMxEyNzEzW}
pwn.colkdfd{44odDHpcCh-s4sqHSq0gVrVYi9K.0EM0MDNxwBMxEzMzEzV}
pwn.colkdge{44odDIqdCh-s3tqISq0gVsUYh9K.0FM0MDOxwCLxDzNzDyW}
pwn.colkegd{33odDHqcCh-r3tqHSq0gVsUXi8K.0EM0LDOwwBMxEzNzEzW}
pwn.colkegd{34ocDIqdBh-r4tqHRq0gVrVXh9J.0FM0MDOxwCMxEyNzDzW}
pwn.colldge{43ocDIqdBh-s4tpHSq0gVsUXi9K.0FM0LCOwvCMxEyNyEzW}
pwn.colldge{44ncDIqdCh-s4tpISq0gVrVYi9K.0FM0MDOxwCLxDzNzEzV}
pwn.colldge{44ocDIqdCh-s4sqISp0gVsVYh8J.0FL0MDOwwCMxEzNzDzW}
pwn.colldge{44ocDIqdCh-s4tqISq0gVsVXi9K.0FM0MDOxwCMxEzNzDzW}
pwn.collefd{33ncCIqdCh-s3sqISq0gVsUXi8J.0EM0LCOxwCMwEzMyEzW}
pwn.collefd{34ndCIqdCg-s4sqHSq0gUrVYi8K.0FM0MCNwvCMxEzNyDzW}
pwn.collegd{44odDIqdBh-s4tqISq0gVsVYi9K.0FM0MDNxwCMxEzNzEzW}
pwn.collegd{44odDIqdCh-s3tqISq0fVsVYi9K.0FM0MCOxwCMxEzNzDyW}
pwn.college{34odCIqcCh-s4tqISq0gVsVYi9J.0FL0MDOxvBMxEzNzEzW}
pwn.college{34odDHqdCh-s3tqISq0gVsUYi9K.0FM0MDOxwCMwEzNzEzW}
pwn.college{34odDIpdCh-s4tpISq0gVsUXi9J.0FM0LCOxvCLxEzNzEyW}
pwn.college{43ndDIqcBh-s3tqISq0fVrUYh9J.0EM0MCNxwCMxDyNyDzW}
pwn.college{43odDIqdCh-s4sqISq0gUsVYi9K.0EM0LDOxwCMxEzNzEzW}
pwn.college{44ndCIqcBh-r3tpISp0fVsVYi8J.0FM0MCNxvCMxEzNzEyW}
pwn.college{44ndDIpdCh-s3tqISq0fUrVXi9K.0EM0MDOxwBMwEzNyEzW}
pwn.college{44ndDIqdCh-s3sqISq0gUsVYi8K.0EL0LDOwwCLxEzNzDzW}
pwn.college{44ndDIqdCh-s4tqHSq0gVsVYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44ocDIqdCh-s4tqISq0gVsVYi9K.0EM0MDOxwCMxEzNzEzW}
pwn.college{44odCIpcCg-s4tpISq0gVrUYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDHqdCh-s4sqISq0gVrVYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDIpdCh-s4tqIRq0gVsUYi9K.0EM0MDOxwBMxEzNzEzW}
pwn.college{44odDIqcCg-r4tqISp0gVsVYi9J.0FM0MDOxwCLxEzNzEzW}
pwn.college{44odDIqdBh-s4tqISq0gVsVYh9K.0FM0MDOxwCMxEzNzEyV}
pwn.college{44odDIqdBh-s4tqISq0gVsVYi9K.0EL0LDOwwCMwEyNzEzW}
pwn.college{44odDIqdCh-s3tqISq0gVsVYi9K.0FM0MDOxvCMxEzNzEzW}
pwn.college{44odDIqdCh-s4spISq0gVsVYh9K.0EM0MDOxwCMxEzNzEzW}
pwn.college{44odDIqdCh-s4spISq0gVsVYi9K.0FM0LDOxwBMxEzNzEyW}
pwn.college{44odDIqdCh-s4sqISp0gVsVYi9K.0FM0MDOxwBMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqHSq0gUsVYi9K.0FM0MDOxvCMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqIRq0gUsVYi8K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqISq0fVsVYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqISq0gUsVYi9K.0FM0MDOxvCMwEyNzEzW}
pwn.college{44odDIqdCh-s4tqISq0gVrVYi9K.0FM0MDOxwCMxEyNzEzW}
pwn.college{44odDIqdCh-s4tqISq0gVrVYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqISq0gVsUYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqISq0gVsVYi9K.0FM0MDOxwCMxEzNzEzW}
pwn.college{44odDIqdCh-s4tqISq0gVsVYi9K.0FM0MDOxwCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt about the sort command. The sort command helps you organize data. It reads lines from input (or files) and outputs them in sorted order, by default sort orders the lines alphabetically.

## References
No reference was used for this challenge.

