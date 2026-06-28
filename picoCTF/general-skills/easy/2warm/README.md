# 2warm

**Platform:** picoCTF  
**Category:** General skills              
**Difficulty:** Easy  
**Tags:** `binary`

---

## Challenge Description

**Author:** Sanjay C/Danny Tunitis

**Description**

Can you convert the number 42 (base 10) to binary (base 2)?

---

## Reconnaissance

Binary (base 2) represents numbers using only 0 and 1. Converting from decimal uses repeated division by 2. Convert the decimal number 42 to binary and submit it as the flag.

--- 

## Solving the challenge

### 1. Apply the division method**

Repeatedly divide by 2 and record the remainders:

```
42 ÷ 2 = 21  remainder 0
21 ÷ 2 = 10  remainder 1
10 ÷ 2 =  5  remainder 0
 5 ÷ 2 =  2  remainder 1
 2 ÷ 2 =  1  remainder 0
 1 ÷ 2 =  0  remainder 1
```

Reading the remainders from bottom to top: **101010**

### 2. Verify with Python**

```python
print(bin(42))  # Output: 0b101010
```

--- 

## Flag

```
picoCTF{101010}
```
*(Flag redacted)*

---


## Key takeaways

| # | Lesson |
|---|--------|
| 1 | To convert decimal to binary by hand: divide by 2 repeatedly, collect remainders, then read them in reverse order |
| 2 | Python's `bin()` function instantly converts any integer to its binary string representation, with a `0b` prefix |
| 3 | Binary is the foundation of all digital computing, every piece of data is ultimately stored and processed in base 2 |
| 4 | 42 in binary is `101010` — famously also "the Answer to the Ultimate Question of Life, the Universe, and Everything" |



---
*← [Back to General skills](../../) | [Back to picoCTF](../../../)*
