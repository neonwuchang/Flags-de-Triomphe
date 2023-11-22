## Description
Morse code is well known. Can you decrypt this?
Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/b6bafa62-c8e6-4875-b0fe-4c35e6091307)

## Solution process
We are given an audio file. The file contains some morse code audio. Passing it through an Audio Morse Code Decoder
(many are available online), we get the flag. The only thing that needs to be done is to insert '_' characters in the
appropriate places, change everything to lowercase, and wrap it in the picoCTF{...} format.
