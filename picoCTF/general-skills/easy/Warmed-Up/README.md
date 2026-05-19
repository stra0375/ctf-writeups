# Warmed Up

**Platform:** picoCTF  
**Category:** General skills              
**Difficulty:** Easy  
**Tags:** `hexadecimal`

---

## Challenge Description

**Author:** Sanjay C/Danny Tunitis

**Description**

What is 0x3D (base 16) in decimal (base 10)?

          
---

## Reconnaissance

`0x3D` is a hexadecimal (base 16) number. The challenge requires converting it to its decimal (base 10) equivalent.

--- 

## Solving the challenge

### 1. Convert hex to decimal

Using Python:

```python
print(int('0x3D', 16))  # Output: 61
```

Or manually:

```
0x3D = (3 × 16) + (13 × 1) = 48 + 13 = 61
```

--- 

## Flag

```
picoCTF{16}
```
*(Flag redacted)*

---

## Key takeaways

| # | Lesson |
|---|--------|
| 1 | Hexadecimal (base 16) uses digits 0–9 and letters A–F, where A=10, B=11, C=12, D=13, E=14, F=15 |
| 2 | To convert hex to decimal: multiply each digit by its power of 16 and sum the results |
| 3 | Python's `int('0x3D', 16)` is the fastest way to convert any hex string to decimal |
| 4 | The `0x` prefix is a standard convention indicating a hexadecimal literal in most programming languages |


---
*← [Back to General skills](../../) | [Back to picoCTF](../../../)*
