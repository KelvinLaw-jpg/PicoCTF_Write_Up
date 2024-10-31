## Interencdec
```
Author: NGIRIMANA Schadrack

Description:
Can you get the real meaning from this file.
Download the file here.

```
Challenge link: [https://play.picoctf.org/playlists/17?m=135](https://play.picoctf.org/playlists/17?m=135)

## Solution

Open the downloaded file, it shows `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg==`

The previous slide is on teaching us base64 so this has to have something to do with it. [Here](https://www.youtube.com/watch?v=aUdKd0IFl34) 
is a short video on base64 encoding. You can convert eh string using [cyberchef](https://cyberchef.org/)

After convertion the string became  `b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ=='`

Looks nothing like a flag...however...

The `b'` at the start and the `'` at the end means the string in between means it is a bytes literal in Python.
Seems the Author would like us to learn about unicode, code point and what byte text vs string text is so here are some good videos:

[Bytes and encodings in Python](https://www.youtube.com/watch?v=ls-177DIGao)

[Python String and Byte Literals (Theory of Python)](https://www.youtube.com/watch?v=i98ndhZ1-kc)

[Unicode, in friendly terms](https://www.youtube.com/watch?v=ut74oHojxqo)

And within the `b''` is the text string, which still looks like a base64 string to me

The characteristic of a base64 string is to have the following characer set:
- Uppercase Letters: A-Z
- Lowercase Letters: a-z
- Digits: 0-9
- Special Characters: + and /
- Padding Character: = (may appear at the end)

Therefore, it is likely that a double encoding has applied to the original string, lets do a second layer of decoding, and we get `wpjvJAM{jhlzhy_k3jy9wa3k_78250hmj}`. 

Close, but not there yet. Since it is all english letters with the correct symbols `{}`, it is reasonable to say it is encoded with caesar cipher here.
You can decode it with [https://cryptii.com/pipes/caesar-cipher](https://cryptii.com/pipes/caesar-cipher)
