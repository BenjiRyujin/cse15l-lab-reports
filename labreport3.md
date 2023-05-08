**Lab Report 3**

**Grep command-line options**

**1) `-c`**

[Source: Geeksforgeeks.org grep command](https://www.geeksforgeeks.org/grep-command-in-unixlinux/#)

```
benjiryujin@MacBook-Pro-90 biomed % grep -c "average" 1471-2407-3-16.txt      
9
```

The `-c` grep option allows us to get a count of how many times a pattern appears in the specified file. In this case, we use the `-c` option in the "biomed" directory of "technical" to get the count of how many times the word "average" appears in the text file, which is 9. 

```
benjiryujin@MacBook-Pro-90 911report % grep -c "arrest" *
chapter-1.txt:0
chapter-10.txt:3
chapter-11.txt:7
chapter-12.txt:2
chapter-13.1.txt:1
chapter-13.2.txt:0
chapter-13.3.txt:4
chapter-13.4.txt:11
chapter-13.5.txt:5
chapter-2.txt:1
chapter-3.txt:16
chapter-5.txt:3
chapter-6.txt:16
chapter-7.txt:4
chapter-8.txt:6
chapter-9.txt:0
preface.txt:0
```
We can also use grep to take in multiple inputs. In this example, we use the `-c` option in the "911report" directory to get the count of how many times the word "arrest" appears in all of the files in the current "911report" directory, indicated by the `*`.

**2) `-i`**

[Source: Geeksforgeeks.org grep command](https://www.geeksforgeeks.org/grep-command-in-unixlinux/#)

The "biomed" directories contains many references to DNA. However, if you attempt to use grep and wc to find the amount of lines in all the files of "biomed" containing "dna", you will get the following:

```
benjiryujin@MacBook-Pro-90 biomed % grep "dna" * | wc -l
      39
```
39 is a much lower number than we expect! The reason is that grep is also noting whether the characters are uppercase or lowercase, meaning that the word "DNA" in all uppercase is not being searched by grep. If we looked for "DNA" instead, we'd get a much larger number shown below. 

```
benjiryujin@MacBook-Pro-90 biomed % grep "DNA" * | wc -l
    5993
```

What if we wanted to search for all versions of the word "dna", without any regard for uppercase or lowercase? In that case, we can use the `-i` option in grep, which allows us to enable case-insensitive searching, which ignores lowercase or uppercase when matching lines. Let's try the same thing but with `-i`.

```
benjiryujin@MacBook-Pro-90 biomed % grep -i "dna" * | wc -l
    6141
```
```
benjiryujin@MacBook-Pro-90 biomed % grep -i "DNA" * | wc -l
    6141
```

Both of the outputs end with the same high number because the `-i` option allows us to search through all the files in the "biomed" directory and match lines that have "dna", regardless of lowercase or uppercase conditions. 

**3) `-w'**

[Source: Geeksforgeeks.org grep command](https://www.geeksforgeeks.org/grep-command-in-unixlinux/#)


Normally, the pattern that grep takes isn't restrained by the whole word. In other words, if we gave "the" as the specified pattern for grep to match, it would also look for words such as "there" or "then", as long as it contained the letters "the" in that specified order. Below is an example of using -w to find the lines that contained the exact word "abuse" in the specified file of the "Alcohol_Problems" subdirectory of "government".

```
benjiryujin@MacBook-Pro-90 technical % grep -w "abuse" ./government/Alcohol_Problems/Session2-PDF.txt
(ICD-9, -10) have rigorously defined alcohol abuse and alcohol
not for abuse. DSM includes social and legal consequences of abuse
cases of alcohol abuse meet the ICD-10 definition. In general, an
abuse and dependence. CAGE is a mnemonic from four questions, Cut
a screen for alcohol abuse and dependence, has 24 yes/no questions.
developed in 1972 to screen for alcohol abuse and dependence. It
at-risk drinking in addition to alcohol abuse and dependence. AUDIT
screens for alcohol abuse and dependence. It has five questions,
minutes to administer.33 T-ACE also screens for alcohol abuse and
at-risk drinking, alcohol abuse, and dependence. It is a
drinking, or abuse.5,36
For alcohol abuse or dependence, CAGE was found most effective with
disorder.43 In an ED study, BAC was a poor screen for alcohol abuse
alcohol intoxication and chronic alcohol abuse on outcome from
M. Prevalence and recognition of alcohol abuse in a primary care
Objective diagnosis of alcohol abuse: compared values of
62. Bercsi S, Brickner P, Saha D. Alcohol use and abuse in the
68. Burke T. The economic impact of alcohol abuse a
```

We can also use this idea in reference to the commands we did in number 2 above. When we ran the command `grep -i "dna" * | wc -l`, it didn't just pull the counts of the 3 letter words that matched "dna", but rather all the words that contain "dna" in them, such as "DNA-polymerase", or "DNase". If we wanted to use case-insensitive matching to find the number of lines that exactly only had "dna" in them, we could use the command below.

```
benjiryujin@MacBook-Pro-90 biomed % grep -w -i "dna" * | wc -l
    3725
```

In this example, we added `-w` to the command shown above to only find matches to the whole word of "dna" through all the files in the "biomed" subdirectory. Notice that this number is 3725 compared to the 6141 found above due to the stricter searching condition applied.

**4) `--include`**
Source: Chat GPT 

The `--include` grep option allows us to specify a specific file pattern in which to match our specified pattern. 

```
benjiryujin@MacBook-Pro-90 plos % grep --include "*.txt" "teacher" *
journal.pbio.0020145.txt:        Teaching is a lot like raising children. Like parents, teachers provide learning
journal.pbio.0020228.txt:        uses of a paper by prospective researchers, anthologizers, archivists, teachers, patients,
journal.pbio.0020228.txt:        rather than just their abstracts, are searchable—which, as any teacher knows, makes
journal.pbio.0020276.txt:        has yet to be adopted by the majority of our students and teachers. Unless we do more to
journal.pbio.0020394.txt:        without detailed information from a teacher or a supervisor about the actual structure in
pmed.0010022.txt:        wanting to learn about the latest research on their illness, to teachers wanting to use an
```

In this example, before searching through all files in the "plos" directory, `--include` was used to specify ".txt" files, so grep only attempted to match "teacher" with ".txt" files. 

The `--include` option isn't limited to checking file type, though that is one of its common uses. Any specific pattern in a file can also be sorted using `--include`. In the example above, there are 6 different lines in 5 different files that were matched with grep. However, only one of the files started with "pmed", while all the others started with "journal". What if we wanted to only match files that start with "pmed"?

```
benjiryujin@MacBook-Pro-90 plos % grep --include "pmed*" "teacher" * 
pmed.0010022.txt:        wanting to learn about the latest research on their illness, to teachers wanting to use an
```
In this example, only the files that start with "pmed" were matched with grep, resulting in the one line that was output by the terminal. 








