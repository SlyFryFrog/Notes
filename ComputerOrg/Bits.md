# Binary Basics

## Adding

```
 0011   ->    1+2=3
+0101   ->    1+4=5
-----
 1000   ->    8
```

```
  0101 0011   ->    1+2+16+64=83
+ 0111 1100   ->    4+8+16+32+64=124
-----------
  1100 1111   ->    1+2+4+8+64+128=207
```

### Two's Complement Addition

```
 0111   ->    7
+1000   ->    -8
-----
 1111   ->    -1
```
# Converting Floats to Binary

### 0.75 in Binary

```
0.75 * 2	|	1.5	|	1
0.5 * 2		|	1.0	|	1
0.00 * 2	|	0.0	|	0 -> All will be zero from here on out since there was no remainder
```

### 12.31 in Binary

#### Whole number

- 2^n represents the largest factor that can be taken away.
- W represents the work being done.
- R represents the remainder from the work.
- B represents the binary number at said `n` position.
```
2^n     W             R     B
8	  |	  12 - 8    |   4   | 1
4	  |	  4 - 4	    |   0   | 1
2	  |	  	        |       | 0
1	  |	  	        |       | 0
```

#### Decimal

```
0.31 * 2	|	0.62	|	0
0.62 * 2	|	1.24	|	1
0.24 * 2	|	0.48	|	0
0.48 * 2	|	0.96	|	0
0.96 * 2	|	1.92	|	1
0.92 * 2	|	1.84	|	1
0.84 * 2	|	1.68	|	1
0.68 * 2	|	1.36	|	1
... and so on
```

Therefore 12.31 in binary is
`0000 1100.0100 1111`

Two's complement would work as usual to find -12.31:

Flip: `1111 0011.1011 0000`

Add 1: `1111 0011.1011 0001`

# Hex

## Converting

### Hex to Decimal

## Decimal to Hex

- Divide by 16
- Convert remainders
- Repeat
- Combine

```
124

124 / 16    |   7   |   12
7           |       |       -> less than 16, thus done
```
Answer: `x7C`

```
1203

1203 / 16   |   75  |   3
75 / 16     |   4   |   11
4           |       |
```
Answer: `x4B3`

```
43034

43034 / 16  |   2689    |   10
2689 / 16   |   168     |   1
168 / 16    |   10      |   8
10          |           |
```
Answer: `xA81A`

## Adding

When adding in hex, first add all numbers in a column. If it exceeds 15 (F), subtract in multiples of 16. For each 16 subtracted, carry it to the next column. If less than 16 remains, move the number down.

```
    xFF
  + xFF
------------
```

```
F + F       |   15 + 15     |   30 - 16 |   14 -> E | 1
F + F + 1   |   15 + 15 + 1 |   31 - 16 |   15 -> F | 1
```
Answer: `x1FE`
