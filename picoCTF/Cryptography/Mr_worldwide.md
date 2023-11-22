## Description
A musician left us a message. What's it mean?

![image](https://github.com/neonwuchang/don-t_set_up_flags/assets/103783716/6598b778-d566-4569-a63e-0d2a021610c5)

## Solution process
We are given a file message.txt which contains the following data:

`picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 
54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, 
-73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}`

It is evident that this is the flag we are looking for, and each character of the flag is represented by a pair
of numbers (excluding the '_' character, which is given as is). Each pair of numbers looks like a pair of coordinates,
and taking a clue from the name of the cghallenge *Mr. Worldwide*, if we search for each pair of coordinates we get the 
following places: 

- `(35.028309, 135.753082): Nakanocho, Kamigyo Ward, Kyoto, 602-0958, Japan `
- `(46.469391, 30.740883): Odesa, Odesa Oblast, Ukraine, 65000 `
- `(39.758949, -84.191605): Dayton, OH 45402 `
- `(41.015137, 28.979530): Hoca Paşa, 34110 Fatih/İstanbul, Türkiye `
- `(24.466667, 54.366669): Hazza ' Bin Zayed The First St - Al Manhal - Abu Dhabi - United Arab Emirates `
- `(3.140853, 101.693207): Room 11, Level 2, Bangunan Sulaiman, Jalan Sultan Hishamuddin, 50000 Kuala Lumpur, Malaysia `
- `(9.005401, 38.763611): Kirkos, Addis Ababa, Ethiopia `
- `(-3.989038, -79.203560): Av. Nueva Loja, Loja, Ecuador `
- `(52.377956, 4.897070): Martelaarsgracht 5, 1012 TM Amsterdam, Netherlands `
- `(41.085651,-73.858467): Sleepy Hollow, NY 10591 `
- `(57.790001, -152.407227): Tewa dr, Kodiak, AK 99615 `
- `(31.205753, 29.924526): Faculty Of Engineering, Al Azaritah WA Ash Shatebi, Bab Sharqi, Alexandria Governorate 5423021, Egypt `

Having obtained this information, it is a reasonable guess that the flag is some combination of some initial letter of each of
these places. 

The question now is, which letter to pick? 

The name of the country or state or city? These are all reasonable options; however,
observing these addresses carefully, we can see that there is a lack of consistency if we try to separate according to the
above-mentioned (and similar) categories, and it's not even about finding equivalents and finding a comparable value across
the locations. It is unlikely that something inconsistent would be used to create a cipher.

The next categorisation we can try is grouping by the first word in the address (the bottom level). Or perhaps by the last word 
in the address (the top level). After trying a couple of these options, we see that if we group by the second to last word in the
address, we start getting something meaningful. 

Taking the values of the level just belowthe top in the address, we get the following words:
- Kyoto
- Odesa Oblast
- Dayton
- Istanbul
- Abu Dhabi
- Kuala Lumpur
- Addis Ababa
- Loja
- Amsterdam
- Sleepy Hollow
- Kodiak
- Alexandria Governorate

Putting the first letters of these together, and inserting the '_' characters as given in the flag, we get:

`KODIAK_ALASKA`

which is the value in our flag!
