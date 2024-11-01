# Repetitions

```
Level: Easy
Author: Theoneste Byagutangaza

Description:
Can you make sense of this file?
Download the file here.
```
Challenge link: [https://play.picoctf.org/practice/challenge/371](https://play.picoctf.org/practice/challenge/371)

## Solution
The downloaded file is called enc_flag, using the `file` command we can see that it is a ASCII text

```
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZhTTBKUFdXdGtlbVF4V2tkWGJYUllDbUY2UWpSWmEyaFRWakpHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```

Looking at it and the hint from the file name, this is clearly a base64 encoding with multiple rounds. Thus, the length is so long
lets decode it with [cyber chef](cyberchef.org). After 6 layers of base64 decoding, the flag showed itself
`picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_3f81f7be}`
