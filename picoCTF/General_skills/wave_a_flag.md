## Description

Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...


## Solution process

Get the program file using `wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm`

`file warm` shows that warm is an executable but trying to execute using `./warm` gives a **Permission Denied** message.
So, we check the permissions with `ls -l` and find that the permissions are `-rw-rw-r--`. After granting execute permission
with `chmod +x warm`, it can now be executed (`ls` will show that warm has now become *green*) using `./warm`. We get the 
message:

*Hello user! Pass me a -h to learn what I can do!*

So, we ask for help: `./warm -h` and we get the following message:

*Oh, help? I actually don't do much, but I do have this flag here: picoCTF{...}*
