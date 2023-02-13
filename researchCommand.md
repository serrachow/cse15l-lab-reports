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

## Example 3: `-v`

Here, we use the grep command with `-v` in Vallarta History and History of Japan text files. Adding `-v` to display the lines in a text file that do not match the chosen word. This command can be used quickly to eliminate text that has your chosen word, especially if your word is common. Note, grep is searching by case sensitivity.

**Source:** [grep command in UNIX/Linux](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

**Command 1**
```console
grep -v "the" written_2/travel_guides/berlitz2/Vallarta-History.txt
```

**Output 1**
```
A Brief History
Puerto Vallarta
Puerto Vallarta has continued to grow, and has become an important art center. It attracts an increasing number of visitors to its true Mexican ambiance, coupled with a modern resort environment.   
Ixtapa–Zihuatanejo: From Pre-Hispanic Resort to Modern Paradise   
Puerto Escondido and Huatulco
```

**Command 2**
```console
grep -v "a" written_2/travel_guides/berlitz1/HistoryJapan.txt
```

**Output 2**
```
A Brief History
The oldest Stone Age settlements to be discovered (10,000 
Chinese Influences
Buddhism.
century.
indeed — until 1869.
improvised verse.
Enter the Shoguns
out.
to bolster their government.
30 million.
enforce the (short-lived) new rules.
time.
structures.
symbolic role of the emperor, still considered the embodiment of
“self-defense” force.
government’s blessing, consumers were left to foot the bill.
world.
efficiency in order to survive.
existed.
end up confounding the pessimists. It will likely emerge in the 21st
```

## Example 4: `-l`

Here, we use the grep command `-l` in the travel guides directory to look for specific words. Adding -l displays the file path that contains the word or pattern. This is useful because you can quickly search through texts and also are given their file paths from a chosen word. Note, we add `-i` along with `-l` to form `-li` to ignore case sensitivity. 

**Source:** [grep command in UNIX/Linux](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

**Command 1**
```console
grep -li "escondido" ./written_2/travel_guides/*/*
```

**Output 1**
```
./written_2/travel_guides/berlitz2/California-WhereToGo.txt       
./written_2/travel_guides/berlitz2/Vallarta-History.txt
./written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

**Command 2**
```console
grep -li "stagnation" ./written_2/travel_guides/*/*
```

**Output 2**
```
./written_2/travel_guides/berlitz1/HistoryJapan.txt
./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt        
./written_2/travel_guides/berlitz2/Crete-History.txt
```
