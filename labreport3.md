**Lab Report 3**

**Grep command-line options**

**1) `-c`**


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

**2) 

