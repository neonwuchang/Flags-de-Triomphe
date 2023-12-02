## Description
Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.

[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Access checker program: nc saturn.picoctf.net 64605

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/8a135f50-e63c-4bea-b7d6-c8851131502a)

## Solution process
After downloading the file and extracting it using:

- `wget -P /tmp ` (I was using webshell for this challenge, hence, the I downloaded the file in /tmp.)
- and `gunzip` for extraction since the file was a gzip file

we can follow the instruction in the description and use `mmls`. this is what we see:

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/b9850107-aa7c-4a3e-862d-ef05411dfdba)

According to this, the length of the Linux partition is `202752`. 

Next, we connect to the remote checker using `nc`, and input the length when asked and get the flag!
