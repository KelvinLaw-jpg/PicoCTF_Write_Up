# binhexa

```
Level: Easy
Author: LT 'syreal' Jones

Description:
Unzip this archive and find the file named 'uber-secret.txt'
Download zip file
```
Challenge link: [https://play.picoctf.org/practice/challenge/320](https://play.picoctf.org/practice/challenge/320)

## Solution
Like the previous challenge, we can just use `grep` to find the flag straight away, but since the challenge wants use to use `find` to find a specific
file, we will do that

The command is `find . -iname "uber-secret.txt"` where i means case non sensitive

the result is `./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt`

so we can use `cd /adequate_books/more_books/.secret/deeper_secrets/deepest_secrets` and go straight to the directory. The flag will be inside
