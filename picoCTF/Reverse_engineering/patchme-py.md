## Description

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/d796229a-67c6-41d9-978d-12f3a50a2eab)


## Solution process
On inspecting the python code, we see that it is asking the user for a password,
and if the password is contains the password is correct, the decryption function is called
and the decrypted flag is printed. 
```
flag_enc = open('flag.txt.enc', 'rb').read()

def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "ak98" + \
                   "-=90" + \
                   "adfjhgj321" + \
                   "sleuth9000"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), "utilitarian")
        print(decryption)
        return
    print("That password is incorrect")

level_1_pw_check()
```
Additionally, the password is right there!

We run the program with `python` command and input the password `ak98-=90adfjhgj321sleuth9000` when asked.

And we get the flag!
