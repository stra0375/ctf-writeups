# DISKO 1

**Platform:** picoCTF  
**Category:** Forensics 
**Difficulty:** Easy  
**Tags:** `strings` `grep` `disk image`

---

## Challenge Description

**Author:** Darkraicg492

**Description**

Can you find the flag in this disk image?

Download the disk image here.


---

## Reconnaissance

Downloading and extract the file to reveal a disk image file which contains the hidden flag.

--- 

## Solving the challenge

### 1. Extract the Flag with strings and grep

Use the following command to print the flag directly to the terminal: 

```bash
strings disko-1.dd | grep picoCTF
```

![Flag](screenshots/flag.png)

--- 

## Flag

```
picoCTF{1t5_xxxx_x_xxxxxx_xxxxxxxx}
```
*(Flag redacted)*

---

## Key takeaways

| # | Lesson |
|---|--------|
| 1 | `strings` extracts human-readable text sequences from **binary files** such as executables, libraries, and disk images. It looks for readable text sequences that may give clues about the file’s content or behaviour |
| 2 | A **disk image** (`.dd`) is a binary copy of a storage device |
| 3 | Disk images are widely used in **digital forensics** (analysis without altering the original), backup/recovery (exact copies of drives for disaster recovery), data extraction (recover deletes files or metadata), and reverse engineering (analyse embedded devices or firmware stored on storage media) |
| 4 | Piping `strings` output into `grep` is a fast way to search large binary files for known patterns |



---
*← [Back to Forensics](../../) | [Back to picoCTF](../../../)*
