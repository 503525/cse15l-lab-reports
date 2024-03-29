# Lab Report 5: Putting It All Together
__________

## Part 1 - Debugging Scenario

### Student Post:

Hello, 

I was working on my submission for ListExamples.java when I came across a bug in my program, which I am not sure how to fix. 

When I run my unit tests through the script, it gives me this symptom:

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/5af072da-83ef-4070-9f13-2b41fa667ff9)

The test that failed was the one for testing the Merge Command. It says that the test timed out at Line 44, which is inside of a while loop in the Merge method of my ListExamples.java file. Because of this, I think that there's an infinite loop happening in my code. 

How can I go about fixing this issue?

Thank you, 
- A Student.

### Ta Response:

Hello Student, 

It could be the case that you have an infinite loop in your program. Try using the Java Debugger (JDB) in order to see precisely what is going on. 

To run the JDB, you can run the following commands: 

```
javac -g .:lib/* *.java
jdb -classpath .:lib/* org.junit.runner.JUnitCore TestListExamples
```



### Student's Implementation of TA Advice:

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/c7669796-1676-496f-9e30-295fc1188f43)



### The Setup of the Problem:

```
- lab7
    - lib
        - hamcrest-core-1.3.jar
        - junit-4.13.2.jar
    - ListExamples.java
    - ListExamplesTests.java
    - test.sh
```

The contents of each file:
`ListExamples.java`
![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/4d2cc406-7824-4fae-8e74-dcadb04e94b7)


`ListExamplesTests.java`
![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/b1f2dc32-f6c2-4e86-ad30-ea1f6a8e1f17)

`test.sh`
![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/c673bcec-059d-4daa-8389-31aefc6ef14e)




To trigger the bug: 
![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/f18a6308-5724-4872-a896-c1f05ff67f2f)


In order to fix the bug, the incremented variable in Line 44 needs to be changed from index1 to index2. 


## Part 2 - Reflection

One of the most important technical skills I learned throughout the latter half of the quarter was how to properly use vim. I had a small amount of exposure to vim through a previous course, and all that stayed with me was how cumbersome it was to use. Now, however, as I am beginning to grow comfortable with it, I've started to appreciate all of the commands available at the literal press of a buttom. I've even started to use Vim Shortcuts from whithin IDEs in order to work on assignments for other classes. 

Something concrete that I learned from the labs during the second half of the quarter was how to set up SSH keys from GitHub. I have spent more time than I'd like to admit failing to properly set up remotes within Git repositories, and yet until this class I did not see why SSH would be any easier than the standard HTTPS clone. Now, I can say that cloning from SSH has been monumental for me. I cannot stress enough how grateful I am for learning how to this, regardless of how simple it may be.

Finally, I learned a great deal from tutors and TAs regarding how to navigate Computer Science as an undergrad. I learned how to effectively get in touch with faculty, how to get started reading papers in CS, and how to find a passion project. As a transfer student with only a few more quarters left at UCSD, I feel much more confident in my ability to move forwards and succeed in the time I have left.
