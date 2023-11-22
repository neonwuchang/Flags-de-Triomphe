## Description
We found a leak of a blackmarket website's login credentials. Can you find the password of the user cultiris and successfully decrypt it?
Download the leak here.
The first user in usernames.txt corresponds to the first password in passwords.txt. The second user corresponds to the second password, and so on.

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/258adfe2-27ea-40fb-b1ed-412d716eb9ec)

## Solution process
We are given a file `leak.tar`. The contents of the file can be extracted using `tar -xvf leak.tar`. 

To avoid verbosity, the `v` option can be
excluded. I like using `v` to see the details of the extraction. For example, here, usimg `v` shows that we have a directory named `leak/` and two files 
`leak/usernames.txt` and `leak/passwords.txt`.

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/b9604157-286e-4afc-baa7-145ffed7b2b1)

We know that the rows in the files hold corresponding usernames and data. So, we need to look for the username `cultiris` in usernames.txt, but more
specifically, we need to find its line number. Then, we can find the value that is in the same line in passwords.txt to get the password of the user cultiris.

The row number of the username cultiris can be found by using: `egrep -n cultiris leak/usernames.txt`

We get the result: `378:cultiris`

We read the data in line 378 in passwords.txt using: `sed -n 378p leak/passwords.txt`

And there's the flag! 

But! 

It's encrypted!

Observing the flag, `cvpbPGS{` corresponds with the known value `picoCTF{`. Comparing these, it is evident that this is a simple shift cipher where each
letter has been shifted by 13 places. We easily decrypt this to get our flag and we're done!
