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

**2) -i**

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







