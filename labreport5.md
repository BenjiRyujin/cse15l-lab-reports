**Lab Report 5**

**Original student post 1**

I am on MacOs operating system, using VScode. 

<img width="1427" alt="Screenshot 2023-06-05 at 6 33 35 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/89d1bf6c-889b-40e7-8b74-f0afd9200f69">

When trying to run the the checkstyle files to see if my PA was properly formatted using the guide assigned by Professor Cao, it returns a 
message stating that there are no files to process. I expect to see the checkstyle jar file going through each line of the MyMinHeap.java file 
and reporting any violations of the specific formatting but it does not report anything.


The failure-inducing input must be from the file name, as when I enter the checkstyle terminal command without any file name afterwards, it returns the following message:
```
Missing required parameter: '<files>'
Usage: checkstyle [OPTIONS]... FILES...
Try 'checkstyle --help' for more information.
```
I'm pretty sure my checkstyle syntax is right, and the working directory is also right because the terminal line says I am in starter, which is the file that 
MyMinHeap.java is located in.

**TA response 1**

I agree that the problem here lies in the terminal command where you must specify the file you want to be checked. A way for you to see what files in your current directory can be accessed by name is to use the command `ls`. Try typing that out in the terminal to give you a better idea of how to access MyMinHeap.java.

**Student response 2**

Thank you! I didn't realize until I actually used `ls` that MyMinHeap.java and the other files in the "starter" directory were not in my current directory. I mistakenly thought I was already in that directory because the terminal had "starter" inside of it. The bug here was that I was trying to access the MyMinHeap.java file from an unreachable position; to fix this I moved both checkstyle files into the starter directory and then used `cd` to change directories into "starter" to run the command again successfully.

<img width="1417" alt="Screenshot 2023-06-05 at 6 47 20 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/d49faaca-44a0-4da1-9cea-7eb88b4d5a9f">

