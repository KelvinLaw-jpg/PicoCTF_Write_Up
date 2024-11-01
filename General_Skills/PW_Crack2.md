# PW Crack2

```
Level: Easy
Author: LT 'syreal' Jones

Description:
Can you crack the password to get the flag?
Download the password checker here and you'll need the encrypted flag in the same directory too.
```
Challenge link: [https://play.picoctf.org/practice/challenge/246](https://play.picoctf.org/practice/challenge/246)

## Solution

Same as [PW Crack1](PW_Crack1.md), it has the encrypted key and a piece of python code to verify a password

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

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
```

Same as before the password is hardcoded into the verifier. but is using `chr()` function to make it less obvious. The `chr()` function in python 
converts the input hexadecimal to a character, so just google a unicode table and map the numbers then you will get `4ec9`. Enter it and you'll get the flag
