## Challenge Description

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: Addadshashanammu.zip

## Solution process
After opening the Linux terminal and getting the file using

`$ wget https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip`

I unzipped the file using 
`unzib Addadshashanammu.zip`

And of course, used `TAB` to make life easier!

Then, I navigated through the directory using `ls` and `cd` and a lot of tabs. At this level, there was only one file, an executable named fang-of-haynekhtnamet, 
which i did execute (using `./`). 

And viola! There's the flag!

