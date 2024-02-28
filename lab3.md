# Lab 3: Bugs and Commands

[comment]: <> (******************** PART ONE: BUGS ********************)

[comment]: <> (Choose one bug from Week 4's Lab and include the following:)
[comment]: <> (  - A failure inducing input for the buggy program as a JUnit Test, and any associated code)
[comment]: <> (  - An input that doesn't induce a failure as a JUnit test, and any associated code.)
[comment]: <> (  - The symptom, as the output of running the tests - include screenshots running JUnit for each of the above)
[comment]: <> (  - The bug, as the before-and-after code change required to fix it)
[comment]: <> (Describe how the fix addresses the issue)

[comment]: <> (Write all code and tests as code blocks in md)

[comment]: <> (******************** PART ONE: BUGS ********************)


[comment]: <> (******************** PART TWO: RESEARCHING COMMANDS ********************)

[comment]: <> (Find four interesting command line options for less, find, or grep)
[comment]: <> (Find two examples of using each option on files from the docsearch technical directory)
[comment]: <> (Cite your sources!)

---
## Part Two: Researching Commands (Find)

The `find` command is a useful command that allows one to recursively search for files and directories within a given directory.

In this section, we will go over some interesting command line options that can be used to refine a search.

All information for this section was found here: [https://www.geeksforgeeks.org/find-command-in-linux-with-examples/].

### Option 1: `find -type`

The `-type` option for the `find` command allows users to filter the search for a specific type of object. 

#### Example 1: `-type d`

This option will filter the output of the `find` command to directories.

From within the `docsearch` directory, we can search for all of the directories within `./technical`, as shown here:
```bash
$ find ./technical/ -type d
./technical/
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```

Notice that not only does the `find` command output all of the directories immediately within `./technical`, but it also recursively outputs all of the directories that are nested within other directories. In this example, we can see many of the directories that are present within `./technical/government`. 

This can be useful if one wants to perform operations on, or document information about, the directories in a project. 

#### Example 2: `type -f`

This option will filter the output of the `find` command to files.

Notice in the above example that `./technical/government` has many directories. By using the following command, we can recursively search for all of the files in `.technical/government` without outputting any of the directories themselves.

```bash
$ find ./technical/government/ -type f
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/conference_highlights.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/diversity_priorities.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
... [278 more lines]
```

### Option 2: `find -name`

### Option 3: `find -size`

### Option 4: `find -exec`


