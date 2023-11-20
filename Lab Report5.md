4)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/4411fd54-29df-44d4-88a5-f1b8f34e5508)

Keys Pressed: ssh cs15lfa23bm@ieng6.ucsd.edu, ```<enter>```
The ssh (ieng6 account) was used in order to log into my ucsd ieng6 account.

5)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/698be860-6ddf-4b8b-b448-af7d48d8d61e)
Keys Pressed: git clone git@github.com:Konica-l/lab7.git, ```<enter>```
git clone was used to clone the repository into my ieng6 account. Also note that i used the ssh clone instead of html
in order to push the changes from ieng6 to github.

6)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/ba4703a4-afe2-43db-aa52-79cad4fb4473)
Keys Pressed: cd lab7, ```<enter>```, bash test.sh, ```<enter>```
cd lab7 changes current directory to lab7 since the test files are located in lab7. then bash test.sh runs the test.sh file that tests ListExamples.java.

7)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/46c0aaf7-d332-467c-a319-51c042c4f6cb)
Keys Pressed: vim ListExamples.java, ```<enter>```
vim ListExamples.java takes the terminal into the vim editor where we edit ListExamples.java.

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/e90daf19-2c01-40c0-bc9e-36c119b10626)
Keys Pressed: ```<shift-down>```, ```<down>```, ```<down>```, ```<shift-right>```, ```<left>```, i, ```<backspace>```, 2, ```<escape>```, :wq, ```<enter>```
```<shift-down>``` sends us to line 42 of ListExamples.java. We use ```<down>``` to go one line down two times. ```<shift-right>``` sends us to "+" where we go left with ```<left>``` command. we go into editing mode with "i" where we delete "1" with ```<backspace>``` and replace it with 2 by typing "2". We exit editing mode by pressing ```<escape>``` and saving our edit with ":wq".

8)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/d8ec05e4-d10f-443f-a2d7-5a290dc65823)
Keys Pressed: bash test.sh, ```<enter>```
We run bash test.sh to test ListExamples.java to see if the test runs passed.

9)
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/dc70ebee-09a4-4005-a537-9dafd95c4046)
Keys Pressed: git add ListExamples.java, ```<enter>```, git commit ListExamples.java, ```<enter>```, "changed 2 to 1 in one of the loops in ListExamples.java", ```<escape>```, :wq, git push, ```<enter>```

git add ListExamples.java stages the file to be part of the next commit. git commit creates a commit locally for all added/staged files where we enter editing mode with "I", and add a message to the commit (I used "changed 2 to 1 in one of the loops in ListExamples.java"). We then save and leave the commit stage by exiting the editing mode with ```<escape>``` and typing ":wq". We then send the new commits to our repository in github with git push.

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/1c65817f-2804-41bb-8c1e-259f90ef22d8)
Screenshot to show the commit message in github.
