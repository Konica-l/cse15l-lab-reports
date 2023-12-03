# Part 1 (Using buggy directory from Skill Demo 4 Practice, focuses on merge method in ListExamples.java)
## Student A:
Hello,
I'm currently implementing a program that is supposed to take a list of strings and a StringChecker that checks if the elements 
are a string and returns the list in the same order as it was given. 
However, I ran into an issue with the testing where I inputted [apple, a] but got [a, apple] instead.

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/2adcc660-2be1-4493-af52-081ae8a7cbef)

Can someone explain why I'm getting this output? 

##TA: Hi Student A! Can you share the contents of the file so that we can see what the problem is? We won't really be able to identify
   what the problem is if we don't see your implementation.

##Student A:

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/3d58277a-8e43-4e24-baeb-a92a8452ef5c)

From what I can tell, it has to do with the way I implemented add since add(0, s) would probably add the elements at the front of the list
for all of my elements.

---
# Setup:
contents of program (before fixing the bug)

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/1c7b54eb-b25d-45ef-bc62-998762169221)

contents of program tester

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/78f6b8a5-ed58-4d3a-95c3-3ad1f5421abb)

test.sh script:

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/d1a20c72-73a8-416d-9a79-02a794af6f66)


Structure (required directory: "buggy", "lib") (required files: ListExamples.java, TestListExamples.java, test.sh, hamcrest-core-1.3.jar, junit-4.14.2.jar):

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/8d642852-bb6d-4038-b07c-2d722be76d11)

hamcrest-core-1.3.jar and junit-4.14.2.jar should be in the lib directory.

## Command lines to trigger bug:
1. "bash test.sh", ```<enter>```

## edits to fix the bug:
delete "0, " in add(0, s) on line 15.

If editing from terminal (starting at buggy directory):
1. "vim ListExamples.java", ```<enter>```
2. :15, ```<enter>```
3. ```<shift-right>```, ```<shift-right>```, ```<shift-right>```,```<right>```,```<right>```,```<right>```
4. i, ```<backspace>```, ```<backspace```, ```<escape>```, :wq

# Reflection

I thought it was interesting that you can edit your code in a terminal rather than an editing software (vim).
Although the only reason I can think of why this is important is that you can edit the file contents of a port
from your remote, it was still an interesting topic to learn about another use of the terminal.
