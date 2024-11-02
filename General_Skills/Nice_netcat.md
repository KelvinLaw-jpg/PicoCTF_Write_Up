# Nice netcat

```
Level: Easy
Author: LT 'syreal' Jones

Description:
There is a nice program that you can talk to by using this command in a shell: $ nc mercury.picoctf.net 22902, but it doesn't speak English...
```
Challenge link: [https://play.picoctf.org/practice/challenge/156](https://play.picoctf.org/practice/challenge/156)

## Solution
Prior to this challenge, it is adviced that you finish the challenges first:[what's a netcat](https://play.picoctf.org/practice/challenge/34?category=5&difficulty=1&page=3), [warmed up](https://play.picoctf.org/practice/challenge/58?category=5&difficulty=1&page=3), [Let's warm up](https://play.picoctf.org/practice/challenge/22?category=5&difficulty=1&page=3) and [2warm](https://play.picoctf.org/practice/challenge/86?category=5&difficulty=1&page=3)
to understand how to use netcat and what is required for this challenge

So, lets connect to `$ nc mercury.picoctf.net 22902` and below is what's being shown

```
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
100
51
100
102
100
54
100
102
125
10
```
This is clearly all decimal, lets convert it to Hex. [Here](https://www.convzone.com/decimal-to-hex/) is a good online convertor

```
70
69
63
6f
43
54
46
7b
67
30
30
64
5f
6b
31
74
74
79
21
5f
6e
31
63
33
5f
6b
31
74
74
79
21
5f
64
33
64
66
64
36
64
66
7d
a
```

All left is to Map the Hex to Ascii table. I like to use the unicode table [here](https://symbl.cc/en/unicode-table/)
