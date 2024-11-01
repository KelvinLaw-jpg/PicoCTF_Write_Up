# Big Zip

```
Level: Easy
Author: LT 'syreal' Jones

Description:
Unzip this archive and find the flag.
Download zip file
```
Challenge link: [https://play.picoctf.org/practice/challenge/322](https://play.picoctf.org/practice/challenge/322)

## Solution

This challenge wants to teach us how to search through a sea of directories to find a certain pattern that we are looking for with the command `grep`

The command will be use is `grep -ri "pico" .`, whereas r = recursive meaning search through all sub directories as well, and i means non case sensitive the pattern we are after is anything with pico
and the `.` means current directory. Since I am inside already, if not you can just type the full path. and the flag will show itself.
