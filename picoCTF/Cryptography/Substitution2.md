## Description
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there 
isn't any punctuation! Can you still crack the cipher?

![image](https://github.com/neonwuchang/Flags-de-Triomphe/assets/103783716/a762cd4f-d24c-43dc-b803-0d473f3aae6d)

## Solution process
We are given the ciphertext: 
```
isnfnnpctitnznfmxhisnfwnxxntimjxctsnascdstushhxuhgqbinftnubfciruhgqnicichktckuxbackdurjnfqmifchimkabturjnfusmxxnkdnisntnuhgqnicich
ktehubtqfcgmfcxrhktrtingtmagckctifmichkebkamgnkimxtwscusmfnznfrbtnebxmkagmfonimjxntocxxtshwnznfwnjnxcnznisnqfhqnfqbfqhtnhemscdstus
hhxuhgqbinftnubfciruhgqnicichkctkhihkxrihinmuszmxbmjxntocxxtjbimxthihdnitibankitckinfntinackmkanpucinamjhbiuhgqbinftucnkunanenktcz
nuhgqnicichktmfnheinkxmjhfchbtmeemcftmkauhgnahwkihfbkkckdusnuoxctitmkanpnubickduhkecdtufcqitheenktnhkisnhisnfsmkactsnmzcxrehubtnah
knpqxhfmichkmkacgqfhzctmichkmkaheinksmtnxngnkitheqxmrwnjnxcnznmuhgqnicichkihbusckdhkisnheenktcznnxngnkitheuhgqbinftnubfcirctisnfne
hfnmjniinfznscuxnehfinusnzmkdnxctgihtibankitckmgnfcumkscdstushhxtebfisnfwnjnxcnznismimkbkanftimkackdheheenktczninuskcvbntctnttnkic
mxehfghbkickdmkneenuicznanenktnmkaismiisnihhxtmkauhkecdbfmichkehubtnkuhbkinfnackanenktcznuhgqnicichktahntkhixnmatibankitihokhwisnc
fnkngrmtneenuicznxrmtinmusckdisngihmuicznxrisckoxconmkmiimuonfqcuhuiectmkheenktcznxrhfcnkinascdstushhxuhgqbinftnubfciruhgqnicichki
smitnnotihdnknfminckinfntickuhgqbinftucnkunmghkdscdstushhxnftinmusckdisngnkhbdsmjhbiuhgqbinftnubfcirihqcvbnisncfubfchtcirghiczmick
disngihnpqxhfnhkisncfhwkmkankmjxckdisngihjniinfanenkaisncfgmusckntisnexmdctqcuhUIE{K6F4G_4K41R515_15_73A10B5_702E03EU}
```
Unlike the prvious two substitution challenges 
([0](https://github.com/neonwuchang/Flags-de-Triomphe/blob/592984c687f56ab5363f550eb451215ba8ea991f/picoCTF/Cryptography/Substitution0.md) 
& [1](https://github.com/neonwuchang/Flags-de-Triomphe/blob/592984c687f56ab5363f550eb451215ba8ea991f/picoCTF/Cryptography/Substitution1.md)), 
there are no spaces or punctuations in this encrypted message which makes it a little bit harder to decrypt. But once again, we can see the
familiar pattern : 

`qcuhUIE{K6F4G_4K41R515_15_73A10B5_702E03EU}` which corresponds with: `picoCTF{...}`. 

From this, we can get the decrypted 
values of some letters and we also see that the keys for the upper and lower cases are likely the same. We substitute these in the ciphertext, 
make reasonable guesses for words (here, I used the fact that the phrase `The flag is` often preceeds the actual flag), get more decrypted 
values, substitute again, and so on, until we break the cipher.

The plaintext was:
```
thereexistseveralotherwellestablishedhighschoolcomputersecuritycompetitionsincludingcyberpatriotanduscyberchallengethesecompetitions
focusprimarilyonsystemsadministrationfundamentalswhichareveryusefulandmarketableskillshoweverwebelievetheproperpurposeofahighschool
computersecuritycompetitionisnotonlytoteachvaluableskillsbutalsotogetstudentsinterestedinandexcitedaboutcomputersciencedefensive
competitionsareoftenlaboriousaffairsandcomedowntorunningchecklistsandexecutingconfigscriptsoffenseontheotherhandisheavilyfocusedon
explorationandimprovisationandoftenhaselementsofplaywebelieveacompetitiontouchingontheoffensiveelementsofcomputersecurityisthereforea
bettervehiclefortechevangelismtostudentsinamericanhighschoolsfurtherwebelievethatanunderstandingofoffensivetechniquesisessentialfor
mountinganeffectivedefenseandthatthetoolsandconfigurationfocusencounteredindefensivecompetitionsdoesnotleadstudentstoknowtheirenemyas
effectivelyasteachingthemtoactivelythinklikeanattackerpicoctfisanoffensivelyorientedhighschoolcomputersecuritycompetitionthatseeksto
generateinterestincomputerscienceamonghighschoolersteachingthemenoughaboutcomputersecuritytopiquetheircuriositymotivatingthemtoexplore
ontheirownandenablingthemtobetterdefendtheirmachinestheflagispicoCTF{N6R4M_4N41Y515_15_73D10U5_702F03FC}
```

The flag can be seen in the last line of the decrypted message.

**This process seems long, but it took me no more than 6 minutes, especially because I sued a simple svript to the substitution instead of 
doing it manually.*

***There are also several online tools we can use that can break such simple ciphers in less than seconds, for example, 
[this](https://www.guballa.de/substitution-solver), which broke this cipher in less than 0.2 seconds!*
