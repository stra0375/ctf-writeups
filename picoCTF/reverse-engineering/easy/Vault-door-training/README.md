# vault-door-training

**Platform:** picoCTF  
**Category:** Reverse Engineering 
**Difficulty:** Easy  
**Tags:** `cyberchef` `Big Endian`

---

## Challenge Description

**Author:** Mark E. Haase

**Description**
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: VaultDoorTraining.java 

```Java
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
	String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
	if (vaultDoor.checkPassword(input)) {
	    System.out.println("Access granted.");
	} else {
	    System.out.println("Access denied!");
	}
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_eec0716b713");
    }
}

```
---

## Reconnaissance

The program reads user input, passes it to a function, and compares it to a hardcoded password using a standard equality check.

---

## Solving the challenge

### 1. Read the source code directly

The source is provided, so the hardcoded password string can simply be read out of the source file.

---

## Flag

```
picoCTF{w4rm1ng_xx_xxxx_xxxx_xxxxxxxxxxx}
```
*(Flag redacted)*

---

## Key takeaways

| # | Lesson |
|---|--------|
| 1 | **Hardcoded secrets** in source code are never truly hidden` |
| 2 | Secrets should never be embedded in source or binaries. Use environment variables, secure vaults, or challenge-response schemes instead |
| 3 | Even though the check is wrapped ina function, it does not make it secure |
| 4 | You do not always need to run the program to find weaknesses, look for comparison points, validation logic and trace data flow |


---
*← [Back to Reverse Engineering](../../) | [Back to picoCTF](../../../)*
