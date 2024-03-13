# Lab Report 4: Vim
__________

In this lab, we clone a buggy program from an online GitHub repository, debug the program, and push the changes back to GitHub - all through the command line!

## Logging into ieng6:

Keys Pressed: `<up><ENTER>`

The command to log into ieng6 through ssh is:
'ssh ashapow@ieng6-202.ucsd.edu'

However, because the Bash terminal conveniently saves the most recent commands that were typed, and because the last thing I did on my device's terminal was log into ieng6, I simply had to press `<up>` to access the full command. 

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/2c61e330-7d55-419d-a2e9-b217b2be77fa)

From here, we can log in with `<Enter>`. 

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/21eceaba-4075-489c-8e6b-66e50e26e642)


--- 

## Cloning the repository from GitHub using SSH:

Keys Pressed: `<CTRL>+<R>`, `git cl`, `<Enter>`

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/fa4a1676-0baa-444f-a84b-bfa27500feb1)

When in the Bash Terminal, one can use `<CTRL> + <R>` to search through the command history of the terminal.

Sometime earlier, I had cloned a repository with an identical URL into this repository. As such, the clone command above was within the terminal's command history. After typing `git cl`, the rest of the command showed up, so all I had to do was press `<ENTER>` to run it. 

## Running the tests for the first time:

Keys pressed: `cd l``<Tab><Enter>`, `bash t``<Tab><Enter>`.

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/ef4399ee-0bc2-4db4-bbe4-54e7b5d9a8b7)

The repository contains a Bash Script that compiles the code and runs the tests, called `test.sh`. This script runs the following commands automatically: 
![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/f780fa47-bb93-41d3-abad-7632f11bf7bf)

As such, in order to run these tests, we first need to change directories into the `lab7` directory.
To do this, I typed `cd l`, and used `<Tab>` to autocomplete the command with the `lab7` directory. Then, I pressed `<Enter>` to enter the command.

Then, from within the `lab7` directory, I ran the tests by typing `bash t`, and once again using `<Tab>` to autocomplete the command with the file `test.sh`. Upon pressing `<Enter>`, the script compiled and ran all of the tests on its own. 

## Editing the code:

Keys Pressed: `vim <Shift>+L` `<Tab>` `.` `<Tab>` `<Enter>`, `44 <Shift>+G` `e` `r2`, `:wq` `<Enter>`. 

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/d8a9d279-efb3-4d4a-acb3-17a3ed2c6569)

In order to edit the code from the terminal, I used Vim, a terminal-based text editor. 

In order to access the file, I typed `vim `, followed by `<Shift> + l` in order to type a capital L, and then `<Tab>` in order to complete the name of the ListExamples java file.  

In order to complete the `.java` portion, I typed `.` and then used `<Tab>` to automatically complete the file extension.

Pressing the `<Enter>` key opened vim. 

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/f2659264-420d-45fd-8ea2-7fe294da8dfb)

From within vim, I could see that the bug was present in the final `while` loop of the `merge` method, on the 44th line of the program. Here, the code increments the wrong variable. 

In order to move to line 44, I typed `44 <Shift>+G`. 

Next, I typed `e` to move to the end of the word with the faulty index, and pressed `r2` in order to replace the final character of `index1` with a `2`. 

In doing this, the loop increments the correct variable, and so the code should run correctly.

To save the file and exit vim, I typed `:wq`. 


## Running the tests after debugging:

Keys Pressed: `<up> <up> <Enter>`

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/7553e484-6d5c-4aac-a995-8e1304a720f0)

The Bash terminal saves all recent commands, and pressing the `<up>` arrow allows a user to go through the commands from most recent to least recent. 

Because the last two commands I typed were to run the test script and then open vim, I simply needed to press the `<up>` arrow twice to access the `bash test.sh` command. Then, I typed `<Enter>` to run it. 


## Pushing the changes to GitHub:

Keys Pressed: `git add <Tab>` `<Enter>`, `git commit -m "Fixed Merge Method in ListExamples.java"` `<Enter>`, `git push` `<Enter>`.

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/26a68c1e-648c-45e5-802a-4b547978eae0)

In order to push changes to GitHub, one first needs to commmit the changes to their local repository. 

We begin by staging `ListExamples.java` to be added to the commit. 

In order to do this, I typed `git add ` and then pressed `<Tab>` to automatically complete the name of the altered file. 

After pressing `<Enter>`, it was time to commit to the local repository.

I typed `git commit -m "Fixed Merge Method in ListExamples.java"` in order to do this. Notice that the `-m` flag on the `commit` command allowed me to include the commit message as a part of the command, rather than having to open vim and edit it from there. 

After pressing `<Enter>` to submit the command, I was ready to push the changes. 

This was done through typing the command `git push`, and then pressing `<Enter>`. 

After this, my GitHub page updated to show the following:

![image](https://github.com/503525/cse15l-lab-reports/assets/22303922/800dccad-7d97-496c-959e-16ce37e10ccf)

---

So, in summary: Without opening anything outside of the terminal, we cloned a buggy program from an online GitHub repository, tested the program, debugged and verified the program, and pushed the changes back to GitHub. We were able to do this thanks to the wealth of useful commands available through bash, git, and vim. 
