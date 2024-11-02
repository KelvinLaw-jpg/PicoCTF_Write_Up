# Information

```
Level: Easy
Author: susie

Description:
Files can always be changed in a secret way. Can you find the flag? cat.jpg
```
Challenge link: [https://play.picoctf.org/practice/challenge/186](https://play.picoctf.org/practice/challenge/186)

## Solution

Same as [Can you see](Can_you_see.md), this challenge is to go through the metadata and find out something sus, so lets do a `exiftool`

```
ExifTool Version Number         : 12.40
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 KiB
File Modification Date/Time     : 2024:11:02 17:31:00+00:00
File Access Date/Time           : 2024:11:02 17:34:05+00:00
File Inode Change Date/Time     : 2024:11:02 17:34:05+00:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```

The License field looks very sus, and looks like a base64 encoding.
