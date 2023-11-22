## Description
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around!
The first word seems to be three letters long, maybe you can use that to recover the rest of the message.

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/f208f4d9-3ac2-4149-832c-8eaa92037180)


## Solution process
We are given a scrambled message: `heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4`

The first word (obviously) 'The' makes a 3 letter block so we can use it to get a sense of the pattern used.
We see that 'The' has been scrambled by taking the first letter of the block and lacing it at the end of the block.
To unscramble, simply take the last character of the block and put it in front.

Looking at the scrambled message, its beginning should be 'The flag is'. Keeping this guess in mind, we can verify the 
scrambling and unscrambling patterns we found. The pattern holds!

Now, we can safely use it to unscrable the flag!
