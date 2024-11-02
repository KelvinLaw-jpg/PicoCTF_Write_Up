# Scan Surprise

```
Level: Easy
Author:  Jeffery John

Description:
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
challenge.zip
The same files are accessible via SSH here:
ssh -p 61415 ctf-player@atlas.picoctf.net
Using the password 1ad5be0d. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
```
Challenge link: [https://play.picoctf.org/practice/challenge/444](https://play.picoctf.org/practice/challenge/444)

## Solution

this challenge is to teach us how QR code works. In shell, we can use `zbarimg flag.png` from zbar-tools to check it out
