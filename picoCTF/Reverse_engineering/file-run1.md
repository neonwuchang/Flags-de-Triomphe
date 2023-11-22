## description
A program has been provided to you, what happens if you try to run it on the command line?

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/f223ba8e-baef-4601-bc4c-4fc0eba1f841)

## Solution process
Using `file run`, we see that the given file is an executable. Checking permissions with `ls -l run` we see that execute
permission is not granted. So we use `chmod +x run` to grant that permission, and execute the file by using the command `./run`.

And our flag gets displayed!
