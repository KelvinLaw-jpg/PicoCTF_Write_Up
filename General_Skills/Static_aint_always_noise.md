# Static ain't always noise

```
Level: Easy
Author: LT 'syreal' Jones

Description:
Can you look at the data in this binary: static? This BASH script might help!
```
Challenge link: [https://play.picoctf.org/practice/challenge/163](https://play.picoctf.org/practice/challenge/163)

## Solution

This challenge is trying to introduce objdump to us, and perhaps how a binary files are structured or organised into different sections.

We have 2 files here, a .sh file and a compiled file. Lets look at what is in the .sh with `nano`

```sh
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
```

With a little help of google, it should be easy to understand what `objdumb` does. What is interesting is the `-j` flag which which `.text` is 
needed to follow. [Here](https://stackoverflow.com/questions/42305467/executable-section-headers-meaning-and-use) is a good post on what `.text` holds 
in an executable file. 

Reading through it, it is trying to teach us objdump without using objdump so lets just use this script for now `./ltdis.sh static`

After dumping there are 2 .txt, one is all the strings and one with the assembly of the .text session. Just grep "pico" and you will find the flag

---
Alternatively, we can do it manually, there is a neat little tool call `strings` which we can use (also within the shell script)

Just type `strings static` and it will show all the strings in this binary. to show strings with `objdumb`, we can also use `objdumb -s static`, and pipe it to grep "pico"
