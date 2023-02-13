# GREP Command

## Example 1: `-i`

Here, we use the grep command with `-i` to look for "escondido" in the Vallarta-History text in the Berlitz 2 directory within travel guides. In the second example, we use `-i` to look for "korean" in the History of Japan text in the Berlitz1 directory within travel guides. Adding `-i` searches through the text case insensitively. Adding `-i` insures that you can find all of the chosen word in the text, regardless of its capitalization and will be an accurate representation of how many is in the text.

**Source:** [15 Practical Grep Command Examples In Linux / UNIX](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/)

**Command 1**
```console
grep -i "escondido" written_2/travel_guides/berlitz2/Vallarta-History.txt
```

**Output 1**

```
Puerto Escondido and Huatulco
Even though Puerto Escondido is the more mature tourist destination of the two, Huatulco has the deepest historical roots. The Aztecs and Chichimecs (a Nahuatl-speaking warrior community) knew Huatulco as an important trading port long before the arrival of the Spanish conquistadors.
Puerto Escondido was established in 1928 as a port for shipping coffee. Its importance diminished as coffee shipments began to be transported by truck. In the 1960s tourists discovered the town after it was connected to other coastal towns by Highway 200. With its renowned offshore break, Puerto Escondido became the ultimate destination for backpackers, flower children, surfers looking for the perfect wave, and those attracted by natural beauty and the laid-back pace. True escapists preferred to continue south and visit Puerto Angel, a fishing village that was Oaxaca’s busiest port for a brief period in the 1870s, before reverting back to its peaceable ways.
```

**Command 2**
```console
grep -i "korean" written_2/travel_guides/berlitz1/HistoryJapan.txt
```

**Output 2**
```
begins with the arrival of Korean scribes at the Japanese court around
The Japanese were forced out of the Korean peninsula in the
sixth century, but not before the Koreans had bequeathed to the Yamato
War for control of the Korean markets and the strategic region of
outbreak of the Korean War, with Japan ironically becoming the chief
```    

## Example 2: `-c`

Here, we use the grep command with `-c` in Vallarta History and History of Japan text files. Adding `-c` shows the count of how many lines that match the word or pattern given. This command can be used to see how often a word appears throughout the text (not the word count, but how often out of all the lines in the text). Note, grep is searching by case sensitivity. 

**Source:** [15 Practical Grep Command Examples In Linux / UNIX](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/)

**Command 1**
```console
grep -c "the" written_2/travel_guides/berlitz2/Vallarta-History.txt
```

**Output 1**
```
32
```

**Command 2**
```console
grep -c "Japan" written_2/travel_guides/berlitz1/HistoryJapan.txt
```

**Output 2**
```
101
```
