# Mod 26

**Platform:** picoCTF  
**Category:** Cryptography 
**Difficulty:** Easy  
**Tags:** `ROT13` `cyberchef` 

---

## Challenge Description

**Author:** Pandu

**Description**

Cryptography can be easy, do you know what ROT13 is? values.txt

---

## Solving the challenge

**ROT13** (rotate by 13) is one of the most common simple substitution ciphers in CTFs. 

**Steps:**
1. Copy the encoded string from the text file
2. Open [CyberChef](https://gchq.github.io/CyberChef/)
3. Apply the **"ROT13"** operation (rotation = 13)
4. The output is the flag

![Flag](screenshots/flag.png)

---

## Flag

```
picoCTF{next_xxxx_xxxx_xxx_x_xxxxxx_xx_xxxxx_xxxxxxxx}
```
*(Flag redacted)*

---

## Key takeaways

| # | Lesson |
|---|--------|
| 1 | **ROT13** shifts each letter by 13 positions — applying it twice returns the original, making it its own inverse |
| 2 | "Mod 26" refers to modular arithmetic over the 26-letter alphabet, which underpins all Caesar-style ciphers |
| 3 | CyberChef makes ROT13 (and arbitrary ROT-N) fast to apply |


---
*← [Back to Cryptography](../../) | [Back to picoCTF](../../../)*
