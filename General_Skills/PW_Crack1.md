# PW Crack 1

```
Level: Easy
Author: LT 'syreal' Jones

Description:
Can you crack the password to get the flag?
Download the password checker here and you'll need the encrypted flag in the same directory too.
```
Challenge link: [https://play.picoctf.org/practice/challenge/245](https://play.picoctf.org/practice/challenge/245)

## Solution

The challenge is basically just to teach us how to read python. Opening the code level1.py, it shows

```python
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "1e1a"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()
```

When executed, it will ask you input a password. The password is hardcored into the code which is the worst practice. 
