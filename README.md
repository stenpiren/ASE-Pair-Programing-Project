
# Title: The ASE Pair Project

-----
How is the 26-letter frequency of English distributed in a novel? What are the words that often appear in a type of article? What is the most commonly used term for a writer? What is the most commonly used phrase in Harry Potter, and so on. We will write some procedures to solve this problem and satisfy our curiosity.
## STEP-0: Output the character frenquency
Function: A console program used to count the frequency of 26 characters(a,b,c,...) in a text file

Let's Count the occurrences of 26 characters(a,b,c,...) in a text file.
### Usage:
The Arguements

	usage: main.py [-h] [-f F_FILE_NAME] [-c C_FILE_NAME] [-p P_FILE_NAME]
	               [-q Q_FILE_NAME]
	
	optional arguments:
	  -h, --help            show this help message and exit
	  -f F_FILE_NAME, --f_file_name F_FILE_NAME
	                        Output word frequencies
	  -c C_FILE_NAME, --c_file_name C_FILE_NAME
	                        Output character frequencies
	  -p P_FILE_NAME, --p_file_name P_FILE_NAME
	                        Output phrase frequencies
	  -q Q_FILE_NAME, --q_file_name Q_FILE_NAME
	                        Output PREPOSITION pair frequencies
 Count the occurrences of 26 characters(a,b,c,...) in <file name\>

```
python mian.py -c <file name>
```

The output example:
here we use 'gone with the wind' as an exmaple:
```
python mian.py -c gone_with_the_wind.txt
``` 

Then we can get:

	--------------------------
	|     The rank list      |
	|   Letter   | Frequency |
	|          e | 0.13      |
	|          t | 0.09      |
	|          a | 0.08      |
	|          o | 0.07      |
	|          n | 0.07      |
	|          h | 0.07      |
	|          s | 0.06      |
	|          r | 0.06      |
	|          i | 0.06      |
	|          d | 0.05      |
	|          l | 0.04      |
	|          u | 0.03      |
	|          w | 0.02      |
	|          m | 0.02      |
	|          g | 0.02      |
	|          y | 0.02      |
	|          c | 0.02      |
	|          f | 0.02      |
	|          b | 0.01      |
	|          p | 0.01      |
	|          k | 0.01      |
	|          v | 0.01      |
	|          I | 0.00      |
	|          S | 0.00      |
	|          A | 0.00      |
	|          T | 0.00      |
	|          M | 0.00      |
	|          H | 0.00      |
	|          W | 0.00      |
	|          B | 0.00      |
	|          Y | 0.00      |
	|          C | 0.00      |
	|          x | 0.00      |
	|          P | 0.00      |
	|          O | 0.00      |
	|          G | 0.00      |
	|          j | 0.00      |
	|          R | 0.00      |
	|          N | 0.00      |
	|          q | 0.00      |
	|          E | 0.00      |
	|          D | 0.00      |
	|          F | 0.00      |
	|          z | 0.00      |
	|          L | 0.00      |
	|          J | 0.00      |
	|          U | 0.00      |
	|          K | 0.00      |
	|          V | 0.00      |
	|          X | 0.00      |
	|          Q | 0.00      |
	|          Z | 0.00      |
	--------------------------
## STEP-1: Output the most commen N words frenquency
Function: A console program used to count the frequency of English words in a text file.Let's define what is a word first:

Word: A string of letters and alphanumeric symbols that begin with an English letter as a word. Words are separated by delimiters and are not case-sensitive. In the output, all words are denoted by lowercase characters.

**Notice**:  
English alphabet: A-Z,a-z  
Alphanumeric symbol: a-z,a-z,0-9  
Delimiters: spaces, non-alphanumeric symbols example: good123 is a word, 123good is not a word. Good,good and good are the same word


### Usage:
The Arguements

	usage: main.py [-h] [-f | -c] [-d] [-s] [-n NUM] path
	
	positional arguments:
	  path               The file/directory to be operated with
	
	optional arguments:
	  -h, --help         show this help message and exit
	  -f, --countWords   Output word frequencies
	  -c, --countChar    Output character frequencies
	  -d, --dirFlag      Treat the <file name> as an directory
	  -s, --reFlag       Verb file to normalize the veb tenses
	  -n NUM, --num NUM  Output only the top <num> iterms
 Count the occurrences of 26 words in <file name\>

```
python mian.py -f <file name>
```

The output example:
here we use 'gone with the wind' as an exmaple:
```
python mian.py -f gone_with_the_wind.txt
``` 

Then we can get:

	File name:gone_with_the_wind.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |4.53%    |
	|and      |3.75%    |
	|to       |2.36%    |
	|of       |2.03%    |
	|she      |1.99%    |
	|her      |1.96%    |
	|a        |1.81%    |
	|in       |1.42%    |
	|was      |1.41%    |
	|i        |1.27%    |
	-------------------
	Time Consuming:0.395534

Specify the file directory to perform wf.exe-f <file> operations on each file in the <directory>:

```
python mian.py -f -d <directory>
``` 

If you need to recursively traverse all subdirectories under <directory>:

```
python mian.py -f -d -s <directory>
``` 

The output example: here we use directory "examples" as an exmaple:

	C:\Users\lenovo\Desktop\ASE\project>python main.py -f gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |4.53%    |
	|and      |3.75%    |
	|to       |2.36%    |
	|of       |2.03%    |
	|she      |1.99%    |
	|her      |1.96%    |
	|a        |1.81%    |
	|in       |1.42%    |
	|was      |1.41%    |
	|i        |1.27%    |
	-------------------
	Time Consuming:0.395534
	
	C:\Users\lenovo\Desktop\ASE\project>python main.py -f -d examples
	File name:examples\gone_with_the_wind.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |4.53%    |
	|and      |3.75%    |
	|to       |2.36%    |
	|of       |2.03%    |
	|she      |1.99%    |
	|her      |1.96%    |
	|a        |1.81%    |
	|in       |1.42%    |
	|was      |1.41%    |
	|i        |1.27%    |
	-------------------
	Time Consuming:0.458138
	File name:examples\The Count of Monte Cristo - Alexandre Dumas père.txt
	--------------------------
	|      The Rank List      |
	|words       |Frequency   |
	|the         |5.44%       |
	|to          |2.61%       |
	|and         |2.55%       |
	|of          |2.52%       |
	|a           |1.87%       |
	|i           |1.78%       |
	|you         |1.72%       |
	|he          |1.42%       |
	|in          |1.32%       |
	|that        |1.13%       |
	--------------------------
	Time Consuming:0.451791
	File name:examples\The Old Man and the Sea.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |8.62%    |
	|and      |4.69%    |
	|he       |4.34%    |
	|of       |2.03%    |
	|i        |1.89%    |
	|it       |1.84%    |
	|to       |1.70%    |
	|his      |1.66%    |
	|was      |1.62%    |
	|a        |1.48%    |
	-------------------
	Time Consuming:0.026155
If we recursively traverse all subdirectories under examples:

	C:\Users\lenovo\Desktop\ASE\project>python main.py -f -d -s examples
	File name:examples\gone_with_the_wind.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |4.53%    |
	|and      |3.75%    |
	|to       |2.36%    |
	|of       |2.03%    |
	|she      |1.99%    |
	|her      |1.96%    |
	|a        |1.81%    |
	|in       |1.42%    |
	|was      |1.41%    |
	|i        |1.27%    |
	-------------------
	Time Consuming:0.357057
	File name:examples\The Count of Monte Cristo - Alexandre Dumas père.txt
	--------------------------
	|      The Rank List      |
	|words       |Frequency   |
	|the         |5.44%       |
	|to          |2.61%       |
	|and         |2.55%       |
	|of          |2.52%       |
	|a           |1.87%       |
	|i           |1.78%       |
	|you         |1.72%       |
	|he          |1.42%       |
	|in          |1.32%       |
	|that        |1.13%       |
	--------------------------
	Time Consuming:0.418235
	File name:examples\The Old Man and the Sea.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |8.62%    |
	|and      |4.69%    |
	|he       |4.34%    |
	|of       |2.03%    |
	|i        |1.89%    |
	|it       |1.84%    |
	|to       |1.70%    |
	|his      |1.66%    |
	|was      |1.62%    |
	|a        |1.48%    |
	-------------------
	Time Consuming:0.020366
	File name:examples\sub_dir\The Odyssey - Homer.txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |4.45%    |
	|and      |4.08%    |
	|to       |2.54%    |
	|of       |2.46%    |
	|i        |1.55%    |
	|you      |1.54%    |
	|he       |1.48%    |
	|a        |1.46%    |
	|in       |1.30%    |
	|for      |1.05%    |
	-------------------
	Time Consuming:0.086521
	File name:examples\sub_dir\subsubdir\Jane Eyre(简·爱).txt
	-------------------
	|   The Rank List   |
	|words    |Frequency|
	|the      |4.06%    |
	|i        |3.75%    |
	|and      |3.43%    |
	|to       |2.70%    |
	|a        |2.31%    |
	|of       |2.26%    |
	|you      |1.55%    |
	|in       |1.43%    |
	|was      |1.31%    |
	|it       |1.25%    |
	-------------------
	Time Consuming:0.210071
	File name:examples\sub_dir\subsubdir\The Further Adventures of Robinson Crusoe - Daniel Defoe.txt
	--------------------------
	|      The Rank List      |
	|words       |Frequency   |
	|the         |4.41%       |
	|and         |3.95%       |
	|to          |3.32%       |
	|of          |2.60%       |
	|i           |1.89%       |
	|they        |1.67%       |
	|a           |1.66%       |
	|that        |1.57%       |
	|in          |1.54%       |
	|was         |1.26%       |
	--------------------------
	Time Consuming:0.104499
Supports the-n parameter to output the top N words with the most occurrences:

```
python mian.py -f -n N <file name>
``` 

The output example: here we use file "gone_with_the_wind.txt" as an exmaple:

	C:\Users\lenovo\Desktop\ASE\project>python main.py -f -n 20 gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	--------------------------
	|      The Rank List      |
	|words       |Frequency   |
	|the         |4.53%       |
	|and         |3.75%       |
	|to          |2.36%       |
	|of          |2.03%       |
	|she         |1.99%       |
	|her         |1.96%       |
	|a           |1.81%       |
	|in          |1.42%       |
	|was         |1.41%       |
	|i           |1.27%       |
	|you         |1.24%       |
	|he          |1.16%       |
	|that        |1.08%       |
	|had         |1.06%       |
	|it          |1.06%       |
	|s           |0.89%       |
	|with        |0.78%       |
	|for         |0.78%       |
	|t           |0.75%       |
	|his         |0.74%       |
	--------------------------
	Time Consuming:0.420848

## STEP2:  Support stop words

We see from the results of the first step, in a novel, the highest frequency of the word is generally "a",  "it",  "The", "and",  "This", these words, we are not interested.  We can do a stop Word file (the word stop), and in statistical terms, skip these words. We call this file  "stopwords.txt" files.

### Usage:
The Arguements

	usage: main.py [-h] [-f | -c] [-d] [-s] [-n NUM] [-x STOPFILE] path
	
	positional arguments:
	  path                  The file/directory to be operated with
	
	optional arguments:
	  -h, --help            show this help message and exit
	  -f, --countWords      Output word frequencies
	  -c, --countChar       Output character frequencies
	  -d, --dirFlag         Treat the <file name> as an directory
	  -s, --reFlag          Verb file to normalize the veb tenses
	  -n NUM, --num NUM     Output only the top <num> iterms
	  -x STOPFILE, --stopFile STOPFILE
	                        Use <stop word> as a list of stop words, which are
	                        ignored in the count

Output the words frenquency of file name with ignoring the words in <STOPFILE>:

```
python main.py -x <stopfile> -f <file name>
```

he output example: here we use file "gone with the wind" as an exmaple:

	C:\Users\lenovo\Desktop\ASE\project>python main.py -x stopwords.txt -f gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	--------------------------
	|      The Rank List      |
	|words       |Frequency   |
	|a           |1.81%       |
	|in          |1.42%       |
	|was         |1.41%       |
	|i           |1.27%       |
	|you         |1.24%       |
	|he          |1.16%       |
	|that        |1.08%       |
	|had         |1.06%       |
	|it          |1.06%       |
	|s           |0.89%       |
	--------------------------
	Time Consuming:0.413195

The words in the <STOP FILE\>:  
the, and, to, of, she, her

## STEP-3: Output the phrase's frequency
Let's see what is a phrase:  
Two or more English words, with only a space separating. Take a look at the following example:

	Hello World//This is a phrase  
	Hello, World//This is not a phrase

### Usage
The Arguements

	usage: main.py [-h] [-f | -c | -p PHRASENUM] [-d] [-s] [-n NUM] [-x STOPFILE]
	               path
	
	positional arguments:
	  path                  The file/directory to be operated with
	
	optional arguments:
	  -h, --help            show this help message and exit
	  -f, --countWords      Output word frequencies
	  -c, --countChar       Output character frequencies
	  -p PHRASENUM, --phraseNum PHRASENUM
	                        Output phrase frequencies
	  -d, --dirFlag         Treat the <file name> as an directory
	  -s, --reFlag          Verb file to normalize the veb tenses
	  -n NUM, --num NUM     Output only the top <num> iterms
	  -x STOPFILE, --stopFile STOPFILE
	                        Use <stop word> as a list of stop words, which are
	                        ignored in the count
Count the occurrences of <k\> words phrases in <file name>:

```
python mian.py -p k <file name>
```

here output example: here we use file "gone with the wind" as an exmaple:
	
	C:\Users\lenovo\Desktop\ASE\project>python main.py -p 2 gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	---------------------------------------------
	|               The Rank List               |
	|Phrases              |Frequency            |
	|of the               |0.48%                |
	|in the               |0.47%                |
	|and the              |0.32%                |
	|she had              |0.30%                |
	|to the               |0.23%                |
	|it was               |0.22%                |
	|she was              |0.21%                |
	|on the               |0.21%                |
	|he was               |0.18%                |
	|and she              |0.18%                |
	---------------------------------------------
	Time Consuming:1.742989

## STEP-4: The verb form is unified before counting.

We want to find commonly used words and phrases, but found that English verbs often change in the state and voice, resulting in the same word, the same phrase is considered different. Therefore, we need to unify the verb forms and count them.

**e.g.**Verb take has a variety of the following variants  
**Take** takes took taken taking 

We hope that in implementing the various functions above, there is an option, that is, the various variants of the verb are attributed to its prototype to count.

### Usage
The Arguements
	usage: main.py [-h] [-f | -c | -p PHRASENUM] [-v VERBFILE] [-d] [-s] [-n NUM]
	               [-x STOPFILE]
	               path
	
	positional arguments:
	  path                  The file/directory to be operated with
	
	optional arguments:
	  -h, --help            show this help message and exit
	  -f, --countWords      Output word frequencies
	  -c, --countChar       Output character frequencies
	  -p PHRASENUM, --phraseNum PHRASENUM
	                        Output phrase frequencies
	  -v VERBFILE, --verbFile VERBFILE
	                        Verb file to normalize the veb tenses
	  -d, --dirFlag         Treat the <file name> as an directory
	  -s, --reFlag          Verb file to normalize the veb tenses
	  -n NUM, --num NUM     Output only the top <num> iterms
	  -x STOPFILE, --stopFile STOPFILE
	                        Use <stop word> as a list of stop words, which are
	                        ignored in the count

Count the occurrences of words in <file name> after the verb form unified:

```
python main.py -f -v <verb file> <file name>
```


Count the occurrences of <k\> words phrases in <file name> after the verb form unified:

```
python main.py -p k -v <verb file> <file name>
```

here output example: here we use file "gone with the wind" as an exmaple:

	C:\Users\lenovo\Desktop\ASE\project>python main.py -f -v verbs.txt gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	--------------------------------
	|         The Rank List         |
	|words          |Frequency      |
	|be             |10.72%         |
	|have           |5.73%          |
	|do             |1.97%          |
	|say            |1.58%          |
	|go             |1.48%          |
	|know           |1.33%          |
	|think          |1.17%          |
	|come           |1.03%          |
	|like           |0.90%          |
	|see            |0.88%          |
	--------------------------------
	Time Consuming:0.528598
	C:\Users\lenovo\Desktop\ASE\project>python main.py -p 2 -v verbs.txt gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	----------------------------------------------------
	|                  The Rank List                  |
	|Phrases                 |Frequency               |
	|she have                |0.85%                   |
	|have be                 |0.72%                   |
	|it be                   |0.69%                   |
	|she be                  |0.65%                   |
	|be a                    |0.63%                   |
	|there be                |0.58%                   |
	|he be                   |0.57%                   |
	|do not                  |0.45%                   |
	|to be                   |0.45%                   |
	|go to                   |0.45%                   |
	----------------------------------------------------
	Time Consuming:1.975673

## STEP-5: Counting "Verb Phrases" (v-siyual)

Here is the specification for Step 5.
Let's implement a new feature: counting verb phrases.
```
Usage: wf -q <preposition-list> -v <verb-dict> <path>
```

We'll count only "Verb Phrases", the definition of which is as follows:
```
VerbPhrase := Verb + Spaces + Preposition
Spaces := Space+
Space := ' ' | '\t' | '\r' | '\n'
Preposition := <any one from the list of prepositions>
Verb := <any one in any tense FROM THE DICTIONARY>
```
Read the two sections above to get the list of prepositions and the verb dictionary.

### Usage
The Arguements

	usage: main.py [-h] [-f | -c | -p PHRASENUM | -q PRENAME] [-v VERBFILE] [-d]
	               [-s] [-n NUM] [-x STOPFILE]
	               path
	
	positional arguments:
	  path                  The file/directory to be operated with
	
	optional arguments:
	  -h, --help            show this help message and exit
	  -f, --countWords      Output word frequencies
	  -c, --countChar       Output character frequencies
	  -p PHRASENUM, --phraseNum PHRASENUM
	                        Output phrase frequencies
	  -q PRENAME, --preName PRENAME
	                        Output PREPOSITION pair frequencies
	  -v VERBFILE, --verbFile VERBFILE
	                        Verb file to normalize the veb tenses
	  -d, --dirFlag         Treat the <file name> as an directory
	  -s, --reFlag          Verb file to normalize the veb tenses
	  -n NUM, --num NUM     Output only the top <num> iterms
	  -x STOPFILE, --stopFile STOPFILE
	                        Use <stop word> as a list of stop words, which are
	                        ignored in the count

Count the occurrences of verb + prepostion in <file name> after the verb form unified:

```
python main.py -f -v <verb file> <file name>
```

Here we take "gone with the wind" as an example:

	C:\Users\lenovo\Desktop\ASE\project>python main.py -q prepositions.txt -v verbs.txt gone_with_the_wind.txt
	File name:gone_with_the_wind.txt
	----------------------------------------------------
	|                  The Rank List                  |
	|VerbPre                 |Frequency               |
	|go to                   |0.45%                   |
	|want to                 |0.27%                   |
	|be in                   |0.25%                   |
	|think of                |0.23%                   |
	|try to                  |0.23%                   |
	|have to                 |0.23%                   |
	|look at                 |0.17%                   |
	|come to                 |0.16%                   |
	|back to                 |0.11%                   |
	|be as                   |0.11%                   |
	----------------------------------------------------
	Time Consuming:1.318331