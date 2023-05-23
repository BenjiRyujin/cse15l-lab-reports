**Lab Report 4**

**Step 4: Log into ieng6**

<img width="780" alt="Screenshot 2023-05-22 at 5 37 16 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/3bf4fe08-cb50-4f5d-b787-6fe3cb267bad">

Keys pressed: 

```
ssh cs15lsp23is@ieng6-202.ucsd.edu <enter>
"password" <enter>
```
I logged into the remote server through `ssh`, typing in my password when prompted.


**Step 5: Cloning fork of repo**

<img width="568" alt="Screenshot 2023-05-22 at 5 38 01 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/3f7b02be-cdc5-4e30-b022-d5bd52e6d722">

Keys pressed: 
```
<Command-C>
git clone <Command-V> <enter>
```
I first used my mouse to click on the `fork` option on the Github website when I was on the desired repo to be forked. Then I used Command-C on mac to copy the ssh URL on the new forked Github repository. I then went back to my terminal that was on the remote server to paste in the link and clone it with `git clone`.

**Step 6: Running tests to see failure**

<img width="619" alt="Screenshot 2023-05-22 at 5 39 06 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/5989cd02-29b3-44c7-8f57-a226e4b086cc">

Keys pressed:
```
cd lab7<tab> <enter>
bash test.sh <enter>
```
In order to run the tests, the bash script requires that your working directory is that of the lab7 directory that you just copied. You must use `cd` to change into the directory to then use bash to run `test.sh` which compiles and runs the testers. 

**Step 7: Editing `ListExamples.java` to fix failing test**

<img width="796" alt="Screenshot 2023-05-22 at 5 43 02 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/61c89966-0cf4-419c-9e17-f72d6a97678a">

Keys pressed:
```
vim ListExamples.java <enter>
/index1 <enter>
nnnnnnnnnexi2<esq><:wq><enter>
```
Vim can be used in order to edit `ListExamples.java` directly from the terminal. From there, `/index1` was typed in as a command to go to the first instance where `index1` was found in the java file. From there, I typed `n` 9 times to go to the 9th instance of `index1`, which was where we needed to fix the error. `e` takes us to the end of the word, and `x` deleted the character. `i` put us into insert mode, which allowed us to type the "2" which we needed to change `index1` to `index2` in the code. `<esc>` took us out of insert mode into normal mode which allows us to save and quit the file by using the `<:wq>` command. 

**Step 8: Running tests to see success**
<img width="398" alt="Screenshot 2023-05-22 at 5 52 11 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/5200898e-bacd-4bc2-b153-185e86d3c4cb">

Keys pressed:
```
<up><up><enter>
```
Since `bash test.sh` was the last command that we ran to see the test, we can access this command again by simply clicking the up arrow key twice and pressing enter.

**Step 9: Commit and push changes to Github**

<img width="602" alt="Screenshot 2023-05-22 at 5 54 25 PM" src="https://github.com/BenjiRyujin/cse15l-lab-reports/assets/55765860/bce28470-18a7-492e-a0c5-64bce8d619a3">

Keys pressed:
```
git add ListExamples.java
git commit -m "updated ListExamples.java"
git push
```
`git add` allows me to put the changes I made to ListExamples.java in a staging area of things ready to be pushed to the main repository. `git commit` allows me to finalize and save those changes into the staging area, which is the file/files that will be now be in the push. `-m` is message sent along with the commit to clarify the purpose of the commit. `git push` then pushes those changes into the repository, changing the code and fixing the error. 

