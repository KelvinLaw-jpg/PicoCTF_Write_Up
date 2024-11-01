# binhexa

```
Level: Easy
Author: Nana Ama Atombo-Sackey

Description:
How well can you perfom basic binary operations?
```
Challenge link: [https://play.picoctf.org/practice/challenge/404](https://play.picoctf.org/practice/challenge/404)

## Solution

This challenge is to get us familia with binary operators, essentially `*,+,<<,>>,|,&`

For you it might be very different, but here are my solutions

```
Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00001111
Binary Number 2: 10100000
```

`+` operator
```
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10101111
```
Just add them up

---
`<<` operator  
```
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 000011110
```
Left Shift is to add the whole binary to the left and add a 0 at the right (without dropping the Most Significant Bit MSB)

---
`&` operator
```
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00000000
```
only keep it yes(1) when both is yes(1)

---
`|` operator
```
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10101111
```
If 1 person say yes(1) then yes(1)

---
`>>` operator
```
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01010000
```
Right Shift would shift everything to the right with a 0 added to MSB and dropping the Least Significant Bit LSB
