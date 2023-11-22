## Description
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project.
The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and 
requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret 
passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer!
You will need to read the source code for each level to figure out what the password is for that vault door.
As a warmup, we have created a replica vault in our training facility. The source code for the training vault 
is here: VaultDoorTraining.java

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/57f6b743-7d81-40a6-981c-6f48e5202d94)

## Solution process
We are given the following java code:
```
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
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
    }
}
```
We notice that the correct passWord is actually hard coded in the `checkPassword()` function! That's the flag!
We just need to put it in the picoCTF{} format. 

Also, check [vault-door-1](https://github.com/neonwuchang/don-t_set_up_flags/blob/0df7ff307555b47bf2bf6306c7af81b147616ff4/picoCTF/Reverse_engineering/vault-door-1.md)
