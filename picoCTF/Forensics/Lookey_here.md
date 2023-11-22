## Description
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.
Download the data here.

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/0711abde-1f01-464d-a526-b60601811ddd)

## Solution process
We have a txt file named `anthem.flag.txt` with, as the description suggests, a lot of data. We need to find the flag
somewhere in there. The flag is usually in the format `picoCTF{}`, so we try searching for this in the file using:

`egrep picoCTF anthem.flag.txt`

And our flag appears! there's nothing more we need to do.
