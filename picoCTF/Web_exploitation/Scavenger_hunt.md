## Description
There is some interesting information hidden around this site http://mercury.picoctf.net:5080/. Can you find it?

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/7aed25a2-b178-44d4-9b71-fe0f7591520e)

## Solution process
From the name of the challenge, we know we can expect some kind of scavenger hunt. We open the website and we see a simple webpage with
not much content. So, we examine the source code and discover that the file named `index.html` has the beginning part of the flag:
```
<!-- Here's the first part of the flag: picoCTF{t -->
```
Navigating through the code, we find that `mycss.css` contains the second part of the flag:
```
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```
But where's the rest of the flag?!

Observing the previous patter, we notice that what we need has been hidden in the comments. Going by this, we notice
a comment in the `myjs.js` file that says: 
```
/* How can I keep Google from indexing my website? */
```
*Hint. Hint.*

If we know about this, that's enough of a hint. If we don't, we ask our BFF Google. A simple Google search reveals several methods of
doing that. A <meta> tag in the HTML? Not in this case. Well, how about robots.txt? So, we open it using `http://mercury.picoctf.net:5080/robots.txt`
and there's the next part of the flag as well as another clue!
```
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
Apache...a [hint](https://www.digitalocean.com/community/tutorials/how-to-use-the-htaccess-file): 

*"An .htaccess file is used for an Apache web server as a way to configure the details of your website without altering the server configuration files."*

So, we open `http://mercury.picoctf.net:5080/.htaccess` and get this:
```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```

The two hints we have here are `Mac` and `Store`. I'm not familiar with these, so I ran a Google search. It took a couple of iterations but `Mac Store file` led me
to something called a .DS_Store. Reading up about this, this seems like a solid lead, so we go to `http://mercury.picoctf.net:5080/.DS_Store` and we get:
```
Congrats! You completed the scavenger hunt. Part 5: _35844447}
```

Putting all parts together, the flag is ready!
