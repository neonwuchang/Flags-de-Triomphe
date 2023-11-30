## Description
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/9b5b2452-9bb3-455f-a48c-d804df2cb11d)

## Solution process
There are many online tools available to analyse images; I used [this](https://www.imageforensic.org/) one to analyse the image. (Another tool I like is
[this one](https://fotoforensics.com/).)

Analysis screenshot:

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/25c274cb-9e40-441c-a36f-f2e275ea4fea)

In the XMP metadata, the value for the licence immediately pops as it is quite unlike the usual licence. 

`license: cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`

In fact, it looks like encoded text! So, we try base64, and there we have it: `picoCTF{the_m3tadata_1s_modified}`. That's our flag!
