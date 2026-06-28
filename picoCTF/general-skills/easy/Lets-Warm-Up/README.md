# Lets Warm Up

**Platform:** picoCTF  
**Category:** General skills              
**Difficulty:** Easy  
**Tags:** `hexadecimal` `ASCII` 

---

## Challenge Description

**Author:** Sanjay C/Danny Tunitis

**Description**

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

---

## Reconnaissance

This challenge requires two conversions: hex → decimal, then decimal → ASCII character.

--- 

## Solving the challenge

### 1. Convert hex to decimal**

```
0x70 = (7 × 16) + (0 × 1) = 112
```

### 2. Convert decimal to ASCII**

112 in ASCII is the character `p`.

Using Python:

```python
print(chr(0x70))  # Output: p
```

![Flag](screenshots/flag.png)

--- 

## Flag

```
picoCTF{p}
```
*(Flag redacted)*

---


## Key takeaways

| # | Lesson |
|---|--------|
| 1 | ASCII maps integers 0–127 to characters; the printable range starts at 32 (space) and includes all standard letters, digits, and punctuation |
| 2 | Python's `chr()` function converts any integer directly to its ASCII/Unicode character: `chr(112)` → `'p'` |
| 3 | Combining `int('0x70', 16)` and `chr()` in Python handles the full hex-to-ASCII pipeline in a single line |



---
*← [Back to General skills](../../) | [Back to picoCTF](../../../)*
