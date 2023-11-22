## Description
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/fe41f61b-8e21-404f-9cc4-ed72e27f488d)

## Solution process
We are given the following encrypted message:

```
ZGSOCXPQUYHMILERVTBWNAFJDK 

Qctcnrel Mcptzlo ztebc, fuwq z ptzac zlo bwzwcmd zut, zlo gtenpqw ic wqc gccwmc xtei z pmzbb szbc ul fqusq uw fzb clsmebco. Uw fzb z gcznwuxnm bsztzgzcnb, zlo, zw
wqzw wuic, nlhlefl we lzwntzmubwb—ex sentbc z ptczw rtukc ul z bsuclwuxus reulw ex aucf. Wqctc fctc wfe tenlo gmzsh brewb lczt elc cjwtciuwd ex wqc gzsh, zlo z
melp elc lczt wqc ewqct. Wqc bszmcb fctc cjsccoulpmd qzto zlo pmebbd, fuwq zmm wqc zrrcztzlsc ex gntlubqco pemo. Wqc fcupqw ex wqc ulbcsw fzb actd tcizthzgmc, zlo,
wzhulp zmm wqulpb ulwe selbuoctzwuel, U senmo qztomd gmzic Ynruwct xet qub eruluel tcbrcswulp uw.

Wqc xmzp ub: ruseSWX{5NG5717N710L_3A0MN710L_357GX9XX}
```

A common technique for breaking a substituion cipher is a frequency attack. But before we get to that, remember that the problem statement mentions that the we have the key at the beginning of the message. This would be the line `ZGSOCXPQUYHMILERVTBWNAFJDK`. Now, observe the last line of the message:
`Wqc xmzp ub: ruseSWX{5NG5717N710L_3A0MN710L_357GX9XX}`

This looks like a flag. We can use it to verify that we have indeed identified the key correctly. We know that `ruseSWX` corresponds to the letters `picoCTF`. Cross-checking against the key, it appears that the key has been identified correctly. Now, we can simply use the key to decrypt the flag!
