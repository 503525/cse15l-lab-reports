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

## Running the tests after debugging:

## Pushing the changes to GitHub:
