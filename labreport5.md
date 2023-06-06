**Lab Report 5**

**Original student post 1**

I am on MacOs operating system, using VScode. 

<img width="1435" alt="Screenshot 2023-06-05 at 8 25 14 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/ce9b790b-28f0-4348-a13d-dd42ed94cf6e">


When trying to run bash script, "checker.sh" to run the checkstyle script see if my PA was properly formatted using the guide assigned by Professor Cao, it returns a 
message stating that there are no files to process. I expect to see the checkstyle jar file going through each line of the MyMinHeap.java file 
and reporting any violations of the specific formatting but it does not report anything.


The failure-inducing input must be from the file name, as when I enter the checkstyle terminal command without any file name afterwards, it returns the following message:
```
Missing required parameter: '<files>'
Usage: checkstyle [OPTIONS]... FILES...
Try 'checkstyle --help' for more information.
```
I'm pretty sure my syntax in "checker.sh" is right, and the working directory is also right because the terminal line says I am in starter, which is the file that 
MyMinHeap.java is located in.

**TA response 1**

I agree that the problem here lies in the terminal command where you must specify the file you want to be checked. The bash script looks correct to me. A way for you to see what files in your current directory can be accessed by name is to use the command `ls`. Try typing that out in the terminal to give you a better idea of how to access MyMinHeap.java.

**Student response 2**

Thank you! I didn't realize until I actually used `ls` that MyMinHeap.java and the other files in the "starter" directory were not in my current directory. I mistakenly thought I was already in that directory because the terminal had "starter" inside of it. The bug here was that I was trying to access the MyMinHeap.java file from an unreachable position; to fix this I moved both checkstyle files and the checker.sh into the starter directory and then used `cd` to change directories into "starter" to run the command again successfully.

<img width="1404" alt="Screenshot 2023-06-05 at 8 28 24 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/2db2ba6b-2feb-4700-85dd-5c9c55bdb8b3">

**Recap**

File and directory structure:

<img width="294" alt="Screenshot 2023-06-05 at 8 30 19 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/b59a9631-9eaf-46a3-b01b-3b989f2cce92">

No files had their contents changed to fix the student's problem. Below are the contents to the checker.sh script. All other java files shown in the directory are fully functional. 

```
set -e
java -jar checkstyle-10.7.0-all.jar -c checkstyle.xml $1
```

When the command `bash checker.sh MyMinHeap.java` was ran, VScode tried to find the file that was called MyMinHeap.java within the active working directory that the student was in. Since that file exists only in a directory within the active directory, the bug was triggered, stating `Files to process must be specified, found 0.`. This bug was trickier to identify the solution, as the problem did not lie in the failure to specify the specific java file name, but rather the location.

While the student resolved their own solution by moving the checkstyle files and bash script into the starter directory and then changing their working directory into starter, a more simple solution would be to simply specify the directory that the desired java file is in instead. The desired command to run Checkstyle on MyMinHeap.java, for example, would be `bash checker.sh starter/MyMinHeap.java`, or `bash checker.sh */MyMinHeap.java`.

**Reflection**
Toward the second half of the quarter, I was glad to understand how to use vim to directly edit files from the terminal. Watching professor Politz travel through file contents in vim so fast made me realize how much more efficient and faster I could be able to code through assignments and get work done through the terminal alone. The various different command line options such as grep or find or less were also very helpful and useful whenever I had assignments for other CSE classes as well.

