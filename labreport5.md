**Lab Report 5**
**Original student post**

What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

MacOs operating system, using VScode. 


Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

<img width="1427" alt="Screenshot 2023-06-05 at 6 33 35 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/89d1bf6c-889b-40e7-8b74-f0afd9200f69">

When trying to run the the checkstyle files to see if my PA was properly formatted using the guide assigned by Professor Cao, it returns a 
message stating that there are no files to process. I expect to see the checkstyle jar file going through each line of the MyMinHeap.java file 
and reporting any violations of the specific formatting but it does not report anything.

Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

The failure-inducing input must be from the file name, as when I enter the checkstyle terminal command without any file name afterwards, it returns the following message:
```
Missing required parameter: '<files>'
Usage: checkstyle [OPTIONS]... FILES...
Try 'checkstyle --help' for more information.
```
I'm pretty sure my checkstyle syntax is right, and the working directory is also right because the terminal line says I am in starter, which is the file that 
MyMinHeap.java is located in.
