# Endianness

```
Level: Easy
Author: Nana Ama Atombo-Sackey

Description:
Know of little and big endian?
Source
```
Challenge link: [https://play.picoctf.org/practice/challenge/414](https://play.picoctf.org/practice/challenge/414)

## Solution

The challenge is to teach use little and big endianness, basically how different systems will store data in different order. For example,
all x86 uses little endianness.

So with the downloaded executable, it asks us to give both the little and big endianness of the string `cqfqv`

To get the endianness, we will first convert it to Hex representation through the ASCII Table


|Character	|ASCII Value	|Hexadecimal|
|---|---|---|
|c	|99	|0x63|
|q	|113	|0x71|
|f	|102	|0x66|
|q	|113	|0x71|
|v	|118	|0x76|

The little endianness is vqfqc which is 0x76 0x71 0x66 0x71 0x63, thus 7671667163

The big endianness is cqfqv which is 0x63 0x71 0x66 0x71 0x76, thus 6371667176

In the real thing you would get a different text, but the principle is the same: convert the char to hex value and type it according to it's endianness order.

