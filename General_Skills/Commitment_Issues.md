# Commitment Issues

```
Level: Easy
Author: Jeffery John

Description:
I accidentally wrote the flag down. Good thing I deleted it!
You download the challenge files here:
challenge.zip
```
Challenge link: [https://play.picoctf.org/practice/challenge/411](https://play.picoctf.org/practice/challenge/411)

## Solution

This challenge is to teach us how to roll back to previous version control using git commands. 

like previous, we first have a look at the history of the file by typing `git log message.txt`

```
commit 8dc51806c760dfdbb34b33a2008926d3d8e8ad49 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:17 2024 +0000

    remove sensitive info

commit 87b85d7dfb839b077678611280fa023d76e017b8
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:17 2024 +0000

    create flag
```

Next step is to roll back to previous state by typing `git checkout <the commit hash you what to roll back>`, nano the file and you will see the flag
