# Static ain't always noise

**Platform:** picoCTF  
**Category:** General skills              
**Difficulty:** Easy  
**Tags:** `binary` `objdump` `chmod` `bash`

---

## Challenge Description

**Author:** syreal

**Description**

Can you look at the data in this binary? The bash script might help!

static, ltdis.sh

```bash
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
	echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

	echo "Ripping strings from binary with file offsets..."
	strings -a -t x $1 > $1.ltdis.strings.txt
	echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
	echo "Disassembly failed!"
	echo "Usage: ltdis.sh <program-file>"
	echo "Bye!"
fi
```

---

## Reconnaissance

A binary file and a shell script (`ltdis.sh`) are provided. Use the script to analyse the binary and find the flag.

Inspecting `ltdis.sh` reveals two key lines. First, `$1` is used as a placeholder for the binary filename passed as an argument. Second, `objdump` is called with `-D` (disassemble all sections) and `-j .text` (focus on the text/code section), and the output is written to a `.txt` file.

--- 

## Solving the challenge

### 1. Read the script source

The script uses `$1` as the filename argument and calls `objdump` to disassemble the binary, writing the result to disk.

--- 

### 2. Make the script executable

```bash
chmod +x ltdis.sh
```

--- 

### 3. Run the script against the binary

```bash
bash ltdis.sh static
```

![Run Program](screenshots/run-program.png)

--- 

### 4. Inspect the output files

Three files are created. Open each one and search for the flag string:

```bash
grep -i 'pico' static.ltdis.strings.txt
```

The flag will appear in one of the output files.

![Flag](screenshots/flag.png)

--- 

## Flag

```
picoCTF{d15a5m_xxxxxx_xxxxxxxx}
```
*(Flag redacted)*

---

> **Alternative approach:** A Python script (as that used in challenge: Wave a flag) that opens the binary in `rb` mode and prints its contents can also reveal the flag. Use `Shift + Ctrl + F` in your editor to search for `pico` across all open files.


```python
file = open("static", "rb")

binaryf = file.read()
print(binaryf)

file.close()
```

## Key takeaways

| # | Lesson |
|---|--------|
| 1 | `objdump -D -j .text <binary>` disassembles the code section of a binary into human-readable assembly instructions and can expose embedded strings |
| 2 | Shell scripts use `$1`, `$2`, etc. as positional parameters. `$1` is always the first argument passed on the command line |
| 3 | `grep` is indispensable when hunting for a known string across large output files: `grep -i 'pico' file.txt` performs a case-insensitive search |
| 4 | Multiple approaches often solve the same challenge, `strings`, `objdump`, a hex editor, and custom Python scripts are all valid tools for binary analysis |



---
*← [Back to General skills](../../) | [Back to picoCTF](../../../)*
