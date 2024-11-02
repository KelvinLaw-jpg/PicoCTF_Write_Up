# Clitch Cat

```
Level: Easy
Author: Mubarak Mikail

Description:
How about some hide and seek?
Download this file here.
```
Challenge link: [https://play.picoctf.org/practice/challenge/408](https://play.picoctf.org/practice/challenge/408)

## Solution

In computer forensics, it is almost an art to be overly sensitive and paranoid to the data you are looking at. 

The downloaded file is a jpg, lets first look at it's metadata with `exiftool`

```bash
ExifTool Version Number         : 12.40
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.2 MiB
File Modification Date/Time     : 2024:02:15 22:40:17+00:00
File Access Date/Time           : 2024:11:02 17:17:01+00:00
File Inode Change Date/Time     : 2024:11:02 17:16:43+00:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fNGRhYmRkY2J9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
```

Looking at the metadata, everything looks good except Attribution URL which would normally be a company's website or something related. Here, 
it looks like a base64 encoding. So lets plug it into [cyberchef](cyberchef.org) and see what's up.

Bingo, there is the flag.
