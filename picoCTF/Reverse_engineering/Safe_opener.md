## Description
Can you open this safe?
I forgot the key to my safe but this program is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
Put the password you recover into the picoCTF flag format like:
picoCTF{password}

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/d9a2d41e-7176-48e0-b588-1cd0015e8e7e)

## Solution process
On examiming the Java code, we see the following code in the `SafeOpener` class:
```
public static void main(String args[]) throws IOException {
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        int i = 0;
        boolean isOpen;


        while (i < 3) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();

            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);

            isOpen = openSafe(encodedkey);
            if (!isOpen) {
                System.out.println("You have  " + (2 - i) + " attempt(s) left");
                i++;
                continue;
            }
            break;
        }
    }
    
    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";

        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        else {
            System.out.println("Password is incorrect\n");
            return false;
        }
    }
```

The password is clearly present in the `openSafe` method. The only thing is, it is base64 encoded. 
(The program is base64 encoding the user input password and comparing it to a string called `encodedkey`...good ;) variable naming practices.)
We simply decode the string and input the decoded value as the password to get the flag.
