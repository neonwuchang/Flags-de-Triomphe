## Description
We found this weird message being passed around on the servers, we think we have a working decryption scheme.
Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.
Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/129bf38d-f565-4b58-a21d-ebd95571373e)


## Solution process
We are given the message: `165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138 ` as well as a decryption
scheme.

Take number >> Do number mod 37 >> USe resultant value for substitution >> We get decrypted value >> Repeat until EOF

A little bit of metaphorical leg work, and we get the content of our flag. 

The legwork *could* be writing a simple and small Python program to automate the legwork. For example,
```enc_msg = [165, 248, 94, 346, 299, 73, 198, 221, 313, 137, 205, 87, 336, 110, 186, 69, 223, 213, 216, 216, 177, 138]
alph = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
num = "0123466789"
und = "_"
dec_msg = ""
for i in enc_msg:
    temp = i % 37
    if temp in range (0, 26):
        dec_msg += alph[temp]
    elif temp in range (26, 36):
        dec_msg += num[temp-26]
    else: # the only option is temp = 37 because we are doing modulus operation
        dec_msg += und
print(dec_msg)
```

Wrap it in picoCTF{...} and all done!

