## Description
Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"?

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/9880c43c-72bb-4e98-985f-78513494c01a)

## Solution process
Refer [file-run1](). 

We could simply follow the "instruction" in the description and use `./run Hello!`
and get the flag!

- Or, we could experiment: 
    - On using `./run`, we receive the message: *Run this file with only one argument.*
    - At this point, we combine this information with the hints from the description and use `./run Hello!`. And we get the flag!

- Or, if we want to experiment some more:
    - We could use the one of the most common arguments `-h` for help, and we get the message: *Won't you say 'Hello!' to me first?*.
    -  Now, the hints are *very very* obvious. Now we can finally use `./run Hello!` and get the flag!
