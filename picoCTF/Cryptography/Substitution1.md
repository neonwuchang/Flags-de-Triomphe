## Description
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/14dda2d8-6f56-4a93-ba77-73f578cac0b5)

## Solution process
We are given the following message encrypted using a substituion cipher:

`SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}`

A common technioque for breaking a substitution cipher frequency attack. But before we attempt that, observe the last sentence in the message:

`Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}`. 

This seems to be in the pattern `... the flag is: picoCTF{...}`.

Although the phrase that we can be really sure about is 'picoCTF', the phrase 'the flag is' occurs very commonly as well and corresponds very well with what we have.
Coincidence? I think not. Thus, it is relatively safe to move forward with the assumption that `yar thjm ze: bzskSYT{` corresponds to `the flag is: picoCTF{`.

Using a combination of such association based on educated guesses and common sense, we can decrypt the flag.

As a fun activity, I constructed the substitution key: `JLSQRTMAZ_VHXCKBUDEYN_G_O_`, where the '_'s are used as placeholders for characters that I did not decrypt.
