# Collaborative Development

```
Level: Easy
Author: Jeffery John

Description:
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?
You can download the challenge files here:
challenge.zip
```
Challenge link: [https://play.picoctf.org/practice/challenge/410](https://play.picoctf.org/practice/challenge/410)

## Solution

This challenge is to teach us the branch function in git and how to merge them to the main. 

First lets check out the history with `git log` and whats in the py file

log history:
```
commit 6ce09adec311b859780caf89d993c58e34b53fa6 (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:51 2024 +0000

    init flag printer
```

py file
```
print("Printing the flag...")
```

As expected, nothing much. Lets check out if there are any branches with `git branch -a`

```
  feature/part-1
  feature/part-2
  feature/part-3
* main
```
As expected there are something here, `*` means the branch we are currently at.

Lets change it with the `git checkout feature/part-1` command and see what is in the .py file.

```
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
```

Ok, so part 1 of the flat is here. Lets merge them to the main branch.

1. Go back to Main by using `git checkout main`
2. `git merge feature/part-1`, go into the py file and solve the conflict, and commit it using `git commit -am "put your own update comments here"
3. `git merge feature/part-2`, go into the py file and solve the conflict, and commit it using `git commit -am "put your own update comments here"
4. `git merge feature/part-3`, go into the py file and solve the conflict, and commit it using `git commit -am "put your own update comments here"
5. Alternatively you can `git merge feature/part-1 feature/part-2 feature/part-3 --no-ff` to merge all 3 at once and solve the conflict

