# Verify

```
Level: Easy
Author: Jeffery John

Description:
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
You can download the challenge files here:
challenge.zip
The same files are accessible via SSH here:
ssh -p 52279 ctf-player@rhea.picoctf.net
Using the password 84b12bae. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
Checksum: 3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4
To decrypt the file once you've verified the hash, run ./decrypt.sh files/<file>.
```
Challenge link: [https://play.picoctf.org/practice/challenge/450](https://play.picoctf.org/practice/challenge/450)

## Solution

This challenge is to teach us the first step and the most basic in digital forensic, which is to verify the integrity of a file by using checksum

After unzipping the downloaded file, there will be 3 files in the directory: checksum.txt decrypt.sh and files

So what is checksum is a hash created using the original file and a hashing algorithm. There are many hashing algorithm in this world, but they all 
share the same goal. That is to generate a unique output which no other file can have the same hash, hasing algorithm is designed in a way so even with
the slightest change in the file, the resulting hash will look very different. In older hashing algorithm such as MD5, it has been proven that collision
is possible, thus MD5 is not widely used now.

To generate a hash you can upload any file to an online hash generator, then change the file and generate a new hash and compare them. [Here](https://emn178.github.io/online-tools/sha256.html)
is a SHA256 online generator.

---
Back to the challenge, lets look into the files dir and see whats inside

```
0agQiFLS  6kPfytcD  Cdje4q5k  HlVWXs9d  NFea6BFS  RXCGKuwy  VUPouqTb  ZfRDLvRe  dVJ9IeAT  jSNCdUA3  q2yrfUO0  wtPMeWzq
0pEkV2ds  6rd0x1aK  CntNA8JK  HouNr2C0  NgY5gymg  RZfcsWcw  Vj67lQyx  ZgC80wUc  dZVnOthw  k2kklNHQ  q7LqCtpM  wtq06VT7
0wWA41ot  6vYE68JA  CxDy3RIy  I7V7Ju5A  NopiZGwa  Ricc6Xgh  WBStW98P  aDSBn4a7  dkV6p1DF  k3AMdGoS  q845iKih  wx3RfP7B
0yVzp2am  7U4dSToL  Cz1ZfreC  IAiKRrWF  O2eRM15N  RuvyhgVU  WET6cnvi  aNhIds5X  dtc6oz6G  k5aiuMj6  qRM9Cugo  xzvNiQwK
12GUEFi0  7cnZoSuo  DHDt0q0q  INu5ULbd  OVCZKr6X  S9jVApXB  Wh09BzOS  aWrHNgwY  e018b574  kLFFhUci  qYpcbIbt  yOEWonka
12R70dbh  83NyszLP  DMo5tbhE  Ic0zhcYV  OX3IlkB9  SA3xkV3Z  WrlAfM9p  aXaKm8w8  e7irOvB1  l4lFl66y  rQP8fnIe  yajqgzPt
1EQhRC4i  8Dw7QTA4  DNZBkTaH  J75ycvyv  OYpH5Rfs  SXltVhZT  WxflVQBr  b47rxTge  exGstYty  lUsUQJ4B  rUOHrSvR  ypsNLNOA
1FjaHS3F  8HwmtNGn  Di7h281J  JBVTXHTa  Opx3E3FO  SbFIvoSj  X4s5LEFG  b7e3VlZ8  exbu4azE  m2KQa1Hp  rfNEgD0l  ytd5LOm1
1cYEYb6L  8cSetvuU  Dj2k48PL  JJxoEHaC  Oq8kRa6b  SkQZlbB2  X8OIdwTY  bDlbvwh8  f3Oy21ek  m5cOAhxS  ruWv5GEU  yzqsPNuQ
1iXLQGXR  8sqe8FVs  DqlYDm8h  JXT0M9Rt  OzUaGPJp  TBQytfqs  XScpq1MB  bIl1SDxK  f7v2BtXe  mVEKZ3oW  rudfRBMm  zH4qslwZ
2hOQXHZC  92q4JPFx  E5vU7ojc  Ji1SbY1i  P0zSZ01H  TSJCXwIT  XW7eedrJ  bf6qqi2j  fKWz0UcF  mcjegRRr  st6t5Khc  zM5KAlbJ
2nsMaCTj  9EMX68VB  EAZMi0dM  K1clcP8Z  PB3Mh3mc  TTjLO7LQ  XeegDb5b  blIGgzh7  fWnAvkyW  n05ZtlwX  t0luWBy8  zMQ1nXew
2zpsEiQJ  9nlUSB5k  EB06dS7k  K9mG0gBB  PBh0NfB8  ThekmVcy  XfZqFKg1  br8OM834  ffM4jxzv  n7C2bpPk  t3YK8diU  zWeRABcB
363nnRwS  A0aXQwRy  EVjQlyVv  KCi7EWrH  PGQBY3gP  TqHFzH54  XjZyXSLg  brRmUfmD  ffw8WXYD  nDjOINiw  tLG9HM3a  zZe9EIdH
3BrlDAbo  AKEjqj8u  EtzUMFMR  KV1QF2CV  PKjcfWRy  Tui6wJfr  XrAdESZl  btZJHGWw  fjdhIY2n  nF6EHta6  uJzNSw96  zhBiEB8c
3PmKbHhH  AeCM4Vvt  FN4tlPPC  KcHrhrZK  PUt9VRoX  TwspwefZ  XrvFYdDg  c3eE4Atp  ftNxaFsY  niz3loOL  uQyUDnOZ
3ckGbZtx  AhVRy5sU  FmmWrIZ7  KfXHVDto  Pf3zlSAC  U14Ody2N  Xw38pYK0  cWvaGe5W  gQQDt3TI  o0R9Vxk8  v6LGqmwI
3eBHvesU  Aqg5GrWn  GhWI4eJh  L4oXILcc  PtEdNKlH  U6YYQ3HK  Xxuckerf  caGexAeh  gY52Y8t0  oGmnMVYP  v8sVJPvD
3kS2W94N  BMBlGtHm  GkM1UPTw  LCeIKlH5  PwyKZRSq  UKi454YR  Y4u4wEGY  cdLJdv1c  gZ9thrVF  oRzmzVaf  vCUbox39
3kYAjtIX  BP14euwo  GoGhbQto  LJckwIQl  PzU12rre  UWQ5qeIb  YCf9VpOR  chaBbXpo  hDyxnGKZ  oZ71cyGG  vTgToTLG
3mKIltIv  BkMRgk48  GodaoG3e  LRXQ5oNw  Q5IWBGXV  UiciI0Fr  YG1pCKDt  ciYQtbBp  hKDw8Cwn  oaOPzO00  vfN94Ek3
3xjxuSOP  BoBiL395  H3rLRpMi  LqUvuW7o  Q8eHpBL9  UinP1H13  YPNiaCgG  coeqJdbu  iRXqo85L  oeq8cWO4  vnr7vUto
49gLh1zo  BvplEv2R  HG1OKGnm  M19EEXCb  QNPhWoha  Ujaf2OwZ  YdulsHwq  covwBpER  imkWZwMa  orc2TmKb  w63X3jh4
49qfB01x  CS66jcDI  HPGHI002  MKg0Y6X7  QjJChAMg  UzFFqfxa  YdxjMT1r  cxKJcozU  j1RDffgK  p2FLQhZe  wVXmJCep
5p13qchp  CXjlF1PS  HRSTilo9  MwfNVxMB  RIjDMPzO  V2CZ7uY0  Za4Oz6eg  dINee6RV  j5Tc1Z62  pyJ5KxZp  wj3JmMau
5r6mt5Iq  CaDiX4Hy  HchfFzCW  MzdMfZHa  RJZglp6X  VHviUe6f  ZaN8BLaN  dS2gaUE4  jNImYWHs  q12b9M6L  wr59gSPm
```
There are a bunch of files, lets look at what is in the first one `cat 0agQiFLS`
```
RliF1vdIPAyu97ed5JRBhtZkNAuMHAEo1lthk9ky87Z6qdpqNhHUQEul2zxx9zY
```
Looks like an encrypted key, lets checkout what's in the decrypt.sh
```sh
        #!/bin/bash

        # Check if the user provided a file name as an argument
        if [ $# -eq 0 ]; then
            echo "Expected usage: decrypt.sh <filename>"
            exit 1
        fi

        # Store the provided filename in a variable
        file_name="$1"

        # Check if the provided argument is a file and not a folder
        if [ ! -f "/home/ctf-player/drop-in/$file_name" ]; then
            echo "Error: '$file_name' is not a valid file. Look inside the 'files' folder with 'ls -R'!"
            exit 1
        fi

        # If there's an error reading the file, print an error message
        if ! openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -salt -in "/home/ctf-player/drop-in/$file_name" -k picoCTF; then
            echo "Error: Failed to decrypt '$file_name'. This flag is fake! Keep looking!"
        fi
```
Right, so basically we have to find the correct file and plug it into the decrypt.sh script.

Lets first find the file with the same given hash by generate hashes for all the files with `sha256sum  ./files/*` and pipe it into `grep "your own hash"`

For me the full command will be `sha256sum ./files/* | grep "3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4"`

```bash
3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4  ./files/e018b574
```

Bingo! so now just run `./decrypt.sh ./files/e018b574` and will see the flag.
