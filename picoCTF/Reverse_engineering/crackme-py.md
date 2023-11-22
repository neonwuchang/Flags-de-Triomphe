## Description
![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/96343494-f3a2-45e7-aa71-fcdb19855f82)

## Solution process
On examining the code, we motice that this ```bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE0d_a3hgc3N"``` is our encrypted flag,
and that we have the encryption+decryption function `decode_secret(secrets)`. We do not need to reverse engineer this because, as noted 
on the comments in the code `ROT47 decode  NOTE: encode and decode are the same operation in the ROT cipher family.`

So, we simply call `decode_secret()` and pass the encrypted flag as an argument. The program returns the decrypted flag when run!

