# Blame Game

```
Level: Easy
Author: Jeffery John

Description:
Someone's commits seems to be preventing the program from working. Who is it?
You can download the challenge files here:
challenge.zip
```
Challenge link: [https://play.picoctf.org/practice/challenge/405](https://play.picoctf.org/practice/challenge/405)

## Solution

This challenge is to teach use how to find a bad file in a sea of commit histories. Starting with `git log`

You will see a huge amount of commit history which is not possible to go through manually. Here is where the binary search method comes in handy.
In
