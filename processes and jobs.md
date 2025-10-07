# 1. Listing processes :


In this challenge, /challenge/run has been renamed to a random filename, and we cannot ls the /challenge directory. But it is launched in the background so we have to find the filename to get the flag

## MY SOLUTION:

**Flag** :

```
pwn.college{o611SfpeFI2dyrdLQLCuOfnAZ_V.QX4MDO0wCMxEzNzEzW}

```

To solve this challenge, any one of ps -ef and ps -aux can be used to view the file. I found out that /challenge/run has been renamed to /challenge/23010-run-16569 so I used that and got the flag.
````
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 14:00 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 14:00 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 14:00 ?        00:00:00 /challenge/23010-run-16569
root         135     132  0 14:00 ?        00:00:00 sleep 6h
hacker       146       1  0 14:00 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.
hacker       150     146  0 14:00 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       160     150  0 14:01 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   14:00   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/do
root           7  0.0  0.0 231708  2560 ?        S    14:00   0:00 /run/dojo/bin/sleep 6h
root         132  0.0  0.0   4132  2560 ?        S    14:00   0:00 /challenge/23010-run-16569
root         135  0.0  0.0   2744  1280 ?        S    14:00   0:00 sleep 6h
hacker       146  0.0  0.0  36972 22080 ?        Sl   14:00   0:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --i
hacker       150  0.0  0.0 231940  4160 pts/0    Ss   14:00   0:00 /run/dojo/bin/bash --login
hacker       161  0.0  0.0 233600  3840 pts/0    R+   14:01   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/23010-run-16569
Yahaha, you found me! Here is your flag:
pwn.college{o611SfpeFI2dyrdLQLCuOfnAZ_V.QX4MDO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I was able to learn about the ps command which lists the processes running in our terminal also -ef and -aux are used to list every process in the shell
## References 
No reference was used for this challenge.


# 2. Killing processes :


 In this challenge, /challenge/run will refuse to run while /challenge/dont_run is running. We must find the dont_run process and kill it. 

## MY SOLUTION:

**Flag** :

```
pwn.college{o7gmklZmMOV7I7uC3_riCDaX66J.QXyQDO0wCMxEzNzEzW}

```

To solve this challenge, I first searched for the process by using ps -e | grep /challenge/dont_run then I wrote ps aux in order to list the processes. There I could identify that killing PID 136 will get me the flag.
````
hacker@processes~killing-processes:~$ ps -e | grep /challenge/dont_run
hacker@processes~killing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.2  0.0   1056   640 ?        Ss   14:12   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/do
root           7  0.0  0.0 231708  2560 ?        S    14:12   0:00 /run/dojo/bin/sleep 6h
root         135  0.0  0.0   5204  3520 ?        S    14:12   0:00 su -c /challenge/.launcher hacker
hacker       136  0.0  0.0 231576  3520 ?        Ss   14:12   0:00 /challenge/dont_run
hacker       137  0.0  0.0 231708  2560 ?        S    14:12   0:00 sleep 6h
hacker       148  0.1  0.0  36972 22080 ?        Sl   14:12   0:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --i
hacker       152  0.0  0.0 231940  4160 pts/0    Ss   14:13   0:00 /run/dojo/bin/bash --login
hacker       164  0.0  0.0 233600  3840 pts/0    R+   14:13   0:00 ps aux
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{o7gmklZmMOV7I7uC3_riCDaX66J.QXyQDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about the kill command which is used to terminate the process. It can be done by identifying the PID no.
## References 
No reference was used for this challenge.


# 3. Interrupting processes :


 In this challenge, we have to interrupt /challenge/run in order to get the flag.

## MY SOLUTION:

**Flag** :

```
pwn.college{Up9H9-gj7Sl51VsbudtAXBY210D.QXzQDO0wCMxEzNzEzW}

```

First I ran /challenge/run then I used crtl-c to interrupt and got the flag.

````
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{Up9H9-gj7Sl51VsbudtAXBY210D.QXzQDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about interrupting processes which helps in ultimately getting rid of it, to do that crtl-c is the right command.
## References 
No reference was used for this challenge.



# 4. Killing misbehaving processes :

In this challenge, the workflow will be :
1.Check what processes are running.
2.Find /challenge/decoy in the list and figure out its process ID.
3.Kill it.
4.Run /challenge/run to get the flag without being overwhelmed by decoys

## MY SOLUTION:

**Flag** :

```
pwn.college{kdsWntGXiW92RPafNcslns1kZ79.0FNzMDOxwCMxEzNzEzW}

```

So first I ran ps aux in order to view the processes then I found the PID for /challenge/decoy and killed it. After killing that process, I ran /challenge/run which sent the flag to /tmp/flag_fifo so I used cat /tmp/flag_fifo to get the flag.

````
hacker@processes~killing-misbehaving-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.4  0.0   1056   640 ?        Ss   17:15   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/do
root           7  0.3  0.0 231708  2560 ?        S    17:15   0:00 /run/dojo/bin/sleep 6h
root         137  0.0  0.0   4132  1280 ?        S    17:15   0:00 /bin/bash /challenge/.init
root         138  0.0  0.0   4132  1280 ?        S    17:15   0:00 /bin/bash /challenge/.init
root         139  0.0  0.0   5204  3520 ?        S    17:15   0:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
root         140  0.0  0.0   2744  1600 ?        S    17:15   0:00 sleep 6h
root         141  0.0  0.0   2744  1280 ?        S    17:15   0:00 sleep 6h
hacker       142  0.3  0.0  13516  8960 ?        Ss   17:15   0:00 /usr/bin/python /challenge/decoy
hacker       153  0.3  0.0  36972 22080 ?        Sl   17:15   0:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --i
hacker       157  0.0  0.0 231972  4160 pts/0    Ss   17:15   0:00 /run/dojo/bin/bash --login
hacker       167  0.0  0.0 233600  3840 pts/0    R+   17:15   0:00 ps aux
hacker@processes~killing-misbehaving-processes:~$ kill 142
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
^C
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{jPNMqtqHTcUVa8BbPqf.LsLR6e1rYcLK8bT2sMXAVdtw4GJ}
pwn.college{.dT2Jl-4ri1TVf8QHijjqHBF0c-RzG.FAsNS3O7u1ltdgJa}
pwn.college{.wSSNFxgqRQ4f0uz.VUJUAljG3piDDevZKQ8kXcrsPCXxII}
pwn.college{hYhctsQr4C-QfbJC6FN2RSQk-OrLzTA4VBoF-P-2vOom6Yt}
pwn.college{pI331dGUnFVJ.VQaQ7k.ibjkViwBbfFG7IJIwkgs0-eTM7Q}
pwn.college{B6J2y36WDDmD.il4ECkwrKa-YOdvhsudhZryLqAwqgefMbi}
pwn.college{MP4nn6zSQm4pgwyioFVCkE6CQ0crPqe..-nfIHR2MaigNi6}
pwn.college{qILaSCfaDtMGrkazBgW2AJZXemhIDl2.TvrV3Ux4xvEU78m}
pwn.college{2hWRDVl1pNmcQVHf9RYpc8D7axzEZ9-aprI5cbJ3LENt2ZT}
pwn.college{69iypeRMMX-TH.cVkY.FBkejxYIbqvdbSF8nboG8cBLI3-5}
pwn.college{UpgrwP36S0UfYmXv5qQOacPSl8AzQ67lep-4k8nKYO4zKsf}
pwn.college{R0tp0f6vCfE6yr9mfJf2-k3DsQDz8xXqtG--pE0I8Q7LeUY}
pwn.college{D4i4bfQXrMt2T5QmI47bpMtg6-WLkiZEkYRhI-r0.48AUXf}
pwn.college{dha9stiyU483wVYb427cborazwiGRBHRdFPyk4tG0SoUmBc}
pwn.college{uuqWNOPcNlA0jyU7j-fRos7S4raGcRU-4rQ0cOEJXLa10Xy}
pwn.college{.0yvUOsajFyzQ4liTAxXcQS96MPnSVXLWkBOI25jGL5LwQn}
pwn.college{wS5-y1GZSeSU9lpFNzm2EulGL-Fp5l8uUGuEnc7mv680h98}
pwn.college{F6Y2HE2.R64AHg.h0GZvfI2Rs9r-zn8YehWWmhouSFbrvLI}
pwn.college{bK7fDxCGbJ3OSyBZ7BU7D2Bc97Db0yYN.OvpT0EC9sIzQKs}
pwn.college{G596gDUs-hDRF9zN294IgF.5hzLcjs0M-4IOBKVi9X8qcBb}
pwn.college{QeSjPq1pkT4Usal8JNvSGcDYG5a18ZwaXQ5SIcZsMsaGvHq}
pwn.college{Z8H0vsczV-REYdUP3GP59Vth6r7rgUu7mU3bbgh50cdHvG6}
pwn.college{nxL71IVY06zNUEWOJXnHXIHRYsGGtTLpFLjp.BF3FjG-KUS}
pwn.college{pZajvVp0xln81ZCHJDYDd3svR4cFKVKlRzm3ltLHqc.-4ym}
pwn.college{hlhft91fTFMipZU5rz91LG762nL33gDSetq7o4c-zEUzhf-}
pwn.college{39Cw-iuwcnDCcElANwmIMGhWmAaIoe6vhjlPYFuEgz3UMwX}
pwn.college{KMTshNdP3qjwYH8B.zpqtrrQSDWxmyn8HtEEPwRTtUkqDT.}
pwn.college{UTWpqTAnEBg2CVGXrT6-iRjfxuYcH5AwFDQTdIbz6-L5TtO}
pwn.college{OFoAPo.68ELdxMONkQzpkKY1dXQA.fMsa5yKfeCdsSJJljQ}
pwn.college{HiAt0cZBmBSZHLppUXfaXLb1k18mLUKNUtxY3dxBDgw7pm0}
pwn.college{luPSy98hkQHLUFwGcMjhEJMOEBT9aDvMZikiIzQkqsxQ.3b}
pwn.college{NsmvgQZgoBCLQDciDsnrCL8TeuIdzdLPD53cUEHZDpmtsLU}
pwn.college{Cezv0uvnnWBt98n4QOaF1rDdMKCjW0xPz9t4Zj6eaVVJy2p}
pwn.college{88sPR0IIKythOCktFdJruKnVf5JXL9wrgv5n.uNjYwbfG1I}
pwn.college{qN4DG3fcLUTKA0nlUnu99PBTBM4hfkKQUzWRg3ZSAB37yOK}
pwn.college{mp6KllNRU4W6VJ8rkOuuLSvRPtGzz0nMFZbHyEpMU9S.C9e}
pwn.college{CBBufz-R-rVdOANnKivvCvkpRokreoQvPjz-s6amkCUYR3R}
pwn.college{TO9omAEMHr6nN9Jm-DSruT13gX58l56cSkRVck8NtrHI2.w}
pwn.college{D5fYnRQP1YaNyxGn0pK-IvgoVyv7lp0vLlK6Y8U19QyMvqN}
pwn.college{omlDNXBOf16EqWq0mIO5GUiM2CMPHQQjul8g9WGsRPxXkfT}
pwn.college{wkim0nPrbga1G0BDktqC2wyfTW9XXve8K3p5tdrcGKai2fi}
pwn.college{p602VPI7Z5nUerjA5ol33Y374xVQ2tVZxpZE8m1PiYpyOJk}
pwn.college{m08ReZlySy..PH56xBdP4HoYL2fudItKn58d3giRgamYsxI}
pwn.college{1s-Z43FM2iNyYN8Zx0Z8i1elaitLLMWQsO5Q.CTfLXTeV.4}
pwn.college{wEM.WPsHGYBY29XHYA6.nL3EOO0h9mMojF-BoGUDvfZ1at0}
pwn.college{JmbAA0bIQGkI5.ovbRIUUYQIbWoHk2gaaFJRsI9ZxZUtrhV}
pwn.college{OTPwznuWuo5vANK4v2KJfHQpzNlJi76ABE4MmsC9xxWrcw8}
pwn.college{cvb5dRtPGzLMYee-zcLG4HHg.G08F2dzoC7Wb4cJPXYUCfp}
pwn.college{nfiirVzYrTuZLGzuPx4Ls3gWSCx28uZHVr6VkxE7HfOUjt1}
pwn.college{aTHdcEe0n-cWcNkQHF07cSI61X34RbfyLXVKcfewl3YygJn}
pwn.college{-f.MmZpvtEzhvOhvp9NC5jWIs2Wk-8jvEum5a-2.LLjp0i.}
pwn.college{B7eH.e1frqVIl7mveUsBQ-lN1y0-H-ejZrQfI3IJ3p.u5cM}
pwn.college{UG0XF4k45JLTtGjjmUbEyPv267d-amZh-clcWd4ZNO9roIK}
pwn.college{fhLuzuvw8ln19W2gO1vrSrjWCTYmjx3Oq1Pzot8vkzhGsdX}
pwn.college{eAVG6DcL27UymrciglxJsAzk3mW74tj5dz6yJvPS4xE0ZBA}
pwn.college{hUvoF4NGQnZsFF2t-XAPVk-8M8g3tBjAr2UmLJqsF-PbPvQ}
pwn.college{ebeCnNxJK9fKIfG-OqWlSsjCtGgDHehfemYsw3T5xb8Xde-}
pwn.college{ip-.zkN42NMcs1rn4bMuRp0wMigc1vlTzEA5RQyB30lgkAm}
pwn.college{ojSw8rqKuSO9T88GhpPqNRsQ2kpgteyQDZ8ZyBawEYOaZx-}
pwn.college{lFT0ejAUSXZ9g1TYK4LfjHIYXUP5CQS5N4rGL7ZFNZDM3Jc}
pwn.college{wAZWxxbLa.rWLhjoX0N9K8e2tYV220dEYVuz.fVn39-JNjb}
pwn.college{c4seQ8wbW.k8EiZ0pW76XjbWGmn8t.Ky-npgs5x5o.X5mS7}
pwn.college{L2tcFSBck2PpN-650hgOK2IWKgjkf9JffI24dg9AQdsOIaa}
pwn.college{8EktLls75VWGue.rF0TuSHO6dc3P4CJYdEUCefPDl1ATq6e}
pwn.college{Wb220pE0Ii6-RbQjYv.TwFZWGTLAq.bh3kWk3EUX5YT1WDN}
pwn.college{FTksaHZmiQwvri-oeAq2K01tCiRQqVNy9vXlXwQLpdMVpUd}
pwn.college{aDtq872Uvh27x-M8aT-7druq.PcIE-48WAU8uBCNo841nvi}
pwn.college{FLvrUPL3pei4Bw6nk2WaXfzTflPTtYSXg..Y4UyliLpDgJr}
pwn.college{C5oTrh2Vn1AI-XTPkbd.cmzrKxORR3LJAqs5.e6KTfVLkvb}
pwn.college{Ev9Se3cPAqEtnzOCGV1HQZm1FHEJ91huXdv2W8oc5tJuH0u}
pwn.college{wEV-YpLIKKQmx4ZU28xAXh558zOFFHSPrcI-JJEQuRXJfj.}
pwn.college{8.khoVNKN5pcZOiKwNxtJ3ctywjHq.ou8GvTp2AA14img90}
pwn.college{HJdBxzjyWdzve585.w.vY8NJEyG5DRH7FvC-81oQHpw4tid}
pwn.college{Tq4BZjzChIfwU01KT8HyD97I8Fn5ILKsOf8nbSLjBAgCdGT}
pwn.college{S5JcCPerI6WspyzOA-AYA0S0s7pY5i7WGeW6LpQVbG9imdG}
pwn.college{68-24axdN5S4wANlk-kMX5E7pUVOvZ8p0Dk5s91r8nYkHKP}
pwn.college{5up1Jxp80oowlHgOslwWWqX0flvhw.G3b85hMLwllGv8Y.K}
pwn.college{XYZ6c4Nafw3BC1SpS0X39a-3ZP4oJMq6-hoaUc059EpvaQ7}
pwn.college{wpq8eIQjym7aJZ6hfPtYcD21AFEW6NnLmBJqThDg7aK7sIt}
pwn.college{2uBOFbLoZUFkYlNxCmpo9f6VgLDPiG.XQoTqNFvaPa..sup}
pwn.college{U1AWx-pzAYcpOW9yo.9FK3NBZ14rIBrSe207wdwsiZulxJy}
pwn.college{k9xUMrhkUBBMfpNa0VUIFRW60V2YKTnBeq8Cd5T.Fp7GPyP}
pwn.college{JCzQAVmvJWD3XUJs3dl.klwIhXP6O2QjdZrK0lCga2nBfAq}
pwn.college{iNhjeBRDEXbK4YnRulFS81gHpwXdj3bGV0gx7FyrI.e41aY}
pwn.college{X0PW.AYtzgcg5gAj6PulDCd4J8VnDQG7ex7UY3TNHltVDvF}
pwn.college{5XyJIdvv-Y4dKcduiPUE8PdrVxnC9TxVix-CT09i7Puk-HL}
pwn.college{DsZmmDvRdHk-F3J8ZWFdrCDHFgfJQnqJ4k3AST2YQUIn-.e}
pwn.college{J7TV.B6IXru2DxRXg1OEajOanE.KODKau3qw5fgpPBEKZKn}
pwn.college{u7HlDUZDEW0ZWzs3IFwEn1f2NoedNTDnzL9UNWRJvLXZj0d}
pwn.college{5V.0tzjcJ7j9u2wgku5g5Xu-ZCy-lxCX23Gp41yenxlbsBE}
pwn.college{QM4UttIa7i3.ZTGTNAV3XsqVbR6SVd9BjULSqTClDKa3Bou}
pwn.college{IRalfLVNlUErsBXcODCtclvQmWeLauLJWRk32gBOctPtd2d}
pwn.college{Os.TderCb6.Um4DE-eR9eSBFpr1DsRxEHlXB9vH5gK.Woup}
pwn.college{eTKJPGh-GCJY0y-Lcumo2bW7HFl4tMhOlVd7Of02u.CBCCo}
pwn.college{NL5BE.hKFD8f5pCCifFVl3x94DzOtDCRXcqkhXAFywbjQlG}
pwn.college{fvy-FHzkSN9NadXYvuOyp3Qj8qSJ0uS1hFkKewyWtCOewFz}
pwn.college{.4asLaes6MIWownPB1QZ7V7KHwPXs8vax8PS6f7cVLqs.je}
pwn.college{UE4x0zcEv0fxPgM2lUhK6Oh2F9MudAGTN5SPbBHq9YyD.Yk}
pwn.college{AulSQdurVH-6zKPQaJugQI5Zm8k-X7KKdXHXyFMCtVxeQRI}
pwn.college{.0OmlMEK2reBHQM.3NT-thLFCnXKpGsHoPme.GJfgjObLqQ}
pwn.college{pxbEAdgMKG0QcoHSvYPXrdEOnWKHdTX5lVBrO8Xf4DryDAN}
pwn.college{-58CnnSNeNCfPqwP2pV0lgJ.o2fk8EyMlxq3VTYboaHOO.v}
pwn.college{DUVge2q48nSCxvDoVWz63RaCmoa6A9HRPbGv41Z4c-UYpEM}
pwn.college{42kSX9nWZbq-shjFdWQoEzlF43XmuohYLTwODy9ZvRWb56R}
pwn.college{Gv1uXea.2qmJfDvo9-5EG6tuQPVLHsAiEMHh2Jxhalm0BJw}
pwn.college{jjIiV7mmX1lS8DewbSzD2rv3671SK03WzmZsj.l371SM54g}
pwn.college{btGieGarOgqsvPcG66t-kJAZolKDdoquO3BVRmn2rfSqNb0}
pwn.college{gBGNsAL7EsQu1IfTX8QAPgexrx-2hKI63sZyfzuIzQHrbPp}
pwn.college{tBfVRSdGn08DkA-0m5XVvXSsgiq0wZ0MHJo6HXVgkOPu2Q0}
pwn.college{sx6LBB-0xWyGwXgTpsZRIW5IhilL7ZRNR45cdnSw1tF4aN0}
pwn.college{7NwJ8iaUALXf3njt-QluHo-E18EXzJf326XLUnh0zRfxkp-}
pwn.college{J0EkcbDLuj.qV2d4jooEbWEd6QbdeDX20Ma.gdKgw4DD5if}
pwn.college{r1KpQ2NC9HLx7BQgUKPIuG-kdMPYB5xjyylrx5fgCYYp4.x}
pwn.college{PbDmyEc.tU.qyTIUAguwvmsasfC5R7FFuP5WXsD6OQlpqgn}
pwn.college{OD4kixTyp-ufUT1XVb6IHONGZQ1KlFVBa41qpPMt8igMsC4}
pwn.college{Nka85sipeb8acPzPxH7uVQBGBsTCxd8.yc8Y7SOzMf.lueA}
pwn.college{8xpKdjLsNOpALQY01A1VuOVb.3IyPq3teV.-HtiWQLLns6R}
pwn.college{I6bNaASTbyxbLJ9JwRS93IihHiX1BZhJiRzhDkE-Qim1jFT}
pwn.college{sscYgsJzWQYZ5N1gVFlHFplqFvVbTQlLIAG1nPxkNeWBHzg}
pwn.college{bbKmhWNMLo-Rqp81gPnsfiO3Uq2SRHQ6K3FeX4CdBSBSwbn}
pwn.college{bhSpLY2-MZdZ0Lqw7ktWUSdHlMyRHRnA0X5qQU3rzNSmCr-}
pwn.college{d-v0tv1IZi77zI-yOnZlccEnep0rfkCiI.m1atUpm0OwitF}
pwn.college{ltrHn1lO7sT4z6twmjoCVqFzP3AG-LsbTzQ-Ynad5lzv46Y}
pwn.college{v.LnSM5pWyvCUbQ9135vaLk0gqKbnj8HZGL5aY0Rwdrb8qs}
pwn.college{ENbAsqMXlWWCL4xf8f2ZpLCTL5Mg6KqL0g718ClLTgVLsu6}
pwn.college{r.wWiUYYrYuMD-6-cA3HgL5f63YJPZrmrliCixKdZ7BPVLs}
pwn.college{aeN5-r6SxcMLol2J6yvWQxuix0-rOGZsLri.bbEQTB-PJOH}
pwn.college{LSr1K4sft.HPPiaxo33MQGXMR-qolSs1b3C6ez-AxPfFkcU}
pwn.college{TqWzp7dvBeI92n3qU90OOTIXNOmfYtVC-wLswXIZjg5m0t8}
pwn.college{NIoNfPnFY-CPHjka2.HhXgybNn-rQv9QF6unDkK7vQkRFMx}
pwn.college{An375gd4IfqGD9fGwIMHor0Kg7VB7t2xon7.DTr1e.KOoD8}
pwn.college{uweTMa91oatYjvqDN207lnOrfytZ2WXZ69C1eD9.QlqaeWe}
pwn.college{J1yJUeYiDWMkGW8R3b1PpYfsA-AMSp-gnMILR22kSMXYBxv}
pwn.college{2D55U-WdDl7Uee-0XvMRzLwXpUMAOfnMZT858OKlVzERRoU}

^C
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{kdsWntGXiW92RPafNcslns1kZ79.0FNzMDOxwCMxEzNzEzW}
````


## What I learnt
This challenge was just a practice of what we've learnt in the previous challenges.
## References 
No reference was used for this challenge.



# 5. Suspending processes :


 In this challenge, run wants to see another copy of itself running and using the same terminal. 

## MY SOLUTION:

**Flag** :

```
pwn.college{cW57G_T7tTRAssDTDvf8ooF7pZF.QX1QDO0wCMxEzNzEzW}

```

We had to just use ctrl-z in order to suspend the current terminal then I re ran that terminal so indirectly it was another copy of itself running in the same terminal.

````
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         146     136  0 17:21 pts/0    00:00:00 bash /challenge/run
root         148     146  0 17:21 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         146     136  0 17:21 pts/0    00:00:00 bash /challenge/run
root         153     136  0 17:22 pts/0    00:00:00 bash /challenge/run
root         155     153  0 17:22 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{cW57G_T7tTRAssDTDvf8ooF7pZF.QX1QDO0wCMxEzNzEzW}
````


## What I learnt
In this challenge, I learnt about the ctrl z command use case,  basically it suspends processes to the background.
## References 
No reference was used for this challenge.


# 6. Resuming processes :


 In this challenge, we have to first suspend the current terminal and then resume it.

## MY SOLUTION:

**Flag** :

```
pwn.college{ACXZ0S2-LaRhtf9J3wuyhCx_DsM.QX2QDO0wCMxEzNzEzW}

```

Similar to the previous challenge, I first suspended the terminal using ctrl-z. Then I resumed it by using the fg command.

````
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg /challenge/run
/challenge/run
I'm back! Here's your flag:
pwn.college{ACXZ0S2-LaRhtf9J3wuyhCx_DsM.QX2QDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about fg command which is useful in resuming the suspended terminal and putting it on the foreground.
## References 
No reference was used for this challenge.



# 7. Backgrounding processes :


 In this challenge, run wants to see another copy of itself running in the background using the same terminal.

## MY SOLUTION:

**Flag** :

```
pwn.college{AhivepEPm_AB96Kaqd3MjzoaVvk.QX3QDO0wCMxEzNzEzW}

```

First I ran /challenge/run then used ctrl-z command to suspend it and then in order to put it back in the backgorund of the terminal, I used bg /challenge/run and then again wrote /challenge/run to finally get the flag.

````
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         146 S+   bash /challenge/run
root         148 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         146 S    bash /challenge/run
root         156 S    sleep 6h
root         157 S+   bash /challenge/run
root         159 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{AhivepEPm_AB96Kaqd3MjzoaVvk.QX3QDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about the bg command which resumes processes in the background of the terminal. This will allow the process to keep running, while giving the shell back to invoke more commands.
## References 
No reference was used for this challenge.



# 8. Foregrounding processes :


In this challenge, we have to foreground a background process with fg.

## MY SOLUTION:

**Flag** :

```
pwn.college{kthcYxRo77Z4NI_JIHwMxga8Yfn.QX4QDO0wCMxEzNzEzW}

```

Similar to the previous challenge, the first three commands are the same just that we have to further write fg /challenge/run

````
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg /challenge/run
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{kthcYxRo77Z4NI_JIHwMxga8Yfn.QX4QDO0wCMxEzNzEzW}
````


## What I learnt
Through this challenge, I learnt that we can foreground a background process.
## References 
No reference was used for this challenge.


# 9. Starting backgrounded processes :


 In this challenge, we need to launch /challenge/run backgrounded for the flag without suspending the process.

## MY SOLUTION:

**Flag** :

```
pwn.college{wUyKcpzMBD-Cx1ZB5AaECuxEID_.QX5QDO0wCMxEzNzEzW}

```

As the challenge suggests that we need /challenge/run to be backgrounded without suspending the process, we can do this by using & with the /challenge/run. It will start /challenge/run in the background without suspending it.

````
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 161
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{wUyKcpzMBD-Cx1ZB5AaECuxEID_.QX5QDO0wCMxEzNzEzW}
````


## What I learnt
I learnt about & which when used with a command causes it to start in the background..
## References 
No reference was used for this challenge.



# 10. Process exit codes :


In this challenge, we must retrieve the exit code returned by /challenge/get-code and then run /challenge/submit-code with that error code as an argument.

## MY SOLUTION:

**Flag** :

```
pwn.college{MxzF_WiE8gROUSKkqnszkVGHZgc.QX5YDO1wCMxEzNzEzW}
```

So first I wrote /challenge/get-code then I wrote echo $? to get the code. Finally I wrote /challenge/submit-code 247 to get the flag.

````
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
247
hacker@processes~process-exit-codes:~$ /challenge/submit-code 247
CORRECT! Here is your flag:
pwn.college{MxzF_WiE8gROUSKkqnszkVGHZgc.QX5YDO1wCMxEzNzEzW}
````


## What I learnt
I learnt about exit codes which can be accesed by using the ? variable which needs to be prepended with $.
## References 
No reference was used for this challenge.

