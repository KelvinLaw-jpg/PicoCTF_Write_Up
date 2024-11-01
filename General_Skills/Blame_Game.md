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
In git, there is a neat command `git bisect` and [here](https://www.metaltoad.com/blog/beginners-guide-git-bisect-process-elimination) is a short tutorial.
In short, you mark the current commit as bad and mark the earliest commit that you know is good, then git will split the number of commits into half
and the let you check the middle commit, if it's good that you mark it good, if bad then mark it bad then git will filter it like how we do it manually.

So, lets start with `git bisect start`. Since we know the latest commit is bad we will mark it as bad `git bisect bad`. 

Then we will go to the oldest commit and check if the message.py is good with `git checkout f3cec26cf7f80f91b5c3d1972f14dd4e9f97ec83` and `nano message.py`

Knowing it is good, we will mark it `git bisect good`

git will show the following massage next
```
Bisecting: 239 revisions left to test after this (roughly 8 steps)
```

Keep bisecting it untill the flag shows
