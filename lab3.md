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

## Part 1: Bugs




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
[*The output has been cut short for the sake of brevity*]

Notice that the output does not contain any directories. Using `find ./technical/government` without specifying the `-type` option would have output each directory before outputting the files within them. However, in this example, we see files within the directory `./technical/government/About_LSC` without seeing that directory itself in the output.

This can be incredibly useful when performing operations on a large number of files that would not otherwise work as intended on directories. 

For more information, here is the source from which I found out about this command option: [https://www.geeksforgeeks.org/find-command-in-linux-with-examples/]

---
### Option 2: `find -name`

The `-name` option allows a user to search for files or directories with a specific name. It also supports patterns.

#### Example 1: `-name "<full-name>"`

This option will force the `find` command to search for a single file, and then output its relative path. 

For example, we can search for the location of a specific file named `Texas_Lawyer.txt`.

```bash
$ find ./technical/ -name "Texas_Lawyer.txt"
./technical/government/Media/Texas_Lawyer.txt
```

This can be particularly useful if a user needs to access a specific file or directory within a very large project, but does not know where specifically the file is located. 

This option will also return no output if the target file or directory does not exist. Thus, this can be useful for determining existence in a large project.

#### Example 2: `-name "<pattern>"

This option will list all of the files or directories that match the target pattern. 

In this example, we can look for all files or directories that start with `Barnes`:

```bash
$ find ./technical/ -name "Barnes*"
./technical/government/Media/Barnes_new_job.txt
./technical/government/Media/Barnes_pro_bono.txt
./technical/government/Media/Barnes_Volunteers.txt
```

If a project has naming conventions that help identify files, this can be useful for finding all of the files with specific names. 

Perhaps more useful is how this can be used to find files with specific extensions; for example, the pattern `*.java` can be used to find all java files within a directory.

For more information, here is the source from which I found out about this command option: [https://www.geeksforgeeks.org/find-command-in-linux-with-examples/]

---

### Option 3: `find -size`

This option allows a user to search for files based on their size. 

#### Example 1: `-size +n`

The `+n` option searches for files with more than `n` bytes, where `n` is an integer. 

In this example, we can search for all of the files in `./technical` that contain more than 250000 bytes. 

```bash
$ find ./technical/ -size +500
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
```

It may be useful to note that this only works on files; it will not count the total number of characters within files of a directory.

This can be used when attempting to optimize the size of a project, so as to modify or remove large files that could be taking up uneccesary space.

This can also be useful when refactoring the codebase of a project, so as to evaluate large files that can be potentially split into multiple smaller files that are easier to maintain.

#### Example 2: `-size -nc`

The `-n` option searches for files with less than `n` bytes, where `n` is an integer. 

In this example, we can search for all the files in `./technical` that contain less than 1000 bytes.

```bash
$ find technical/ -type f -size -1000c
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020226.txt
```

Note that we were able to combine command options so as to only search for files of a certain size (by default, this would also return directories for any number of bytes greater than 1). 

By combining commands, this could be useful for determining empty files that have been added by a bash script but have not yet been modified.

For more information, here is the source from which I found out about this command option: [https://www.geeksforgeeks.org/find-command-in-linux-with-examples/]

---

### Option 4: `find -exec`

This option allows a user to execute another command for each file found by the `find` command.

#### Example 1: `-exec rm`

By combining the `find` command with the `rm` command like this, we can recursively remove all files that match a specific criteria. 

For example, we go off of the previous example and remove all files in `technical` that are less than 1000 bytes. 

```bash
$ find technical/ -type f -size -1000c -exec rm {} \;
$
```

Notice that there was no output. This is because the output is determined by `rm`, which has no output as it is written. 

However, when we go to search for all files that are less than 1000 bytes, we see nothing returned. 

```bash
$ find technical/ -type f -size -1000c
$
```

This is because there are no files in `technical` that are less than 1000 bytes anymore. 

This can be a useful command for cleaning up a script's working directory if it creates a lot of helper files. 

#### Example 2: `-exec cat`

By combining the `find` command with the `cat` command like this, we can recursively output the contents of all files that match a specific criteria. 

In this case, we will search for a file and output its contents, without specifically knowing where the file is within `technical/`.

```bash
$ find ./technical/ -name "Texas_Lawyer.txt" -exec cat {} \;




Texas Lawyer

GRANT PROVIDES FUNDING TO CONNECT LEGAL AID CALL CENTERS
Mary Alice Robbins September 9, 2002
A $100,000 technology grant awarded to Texas Rural Legal Aid
will fund an Austin call center and connect it with centers in San
Antonio and Corpus Christi to assist the poor with legal problems
in a 68-county area of Southwest Texas. Washington, D.C.-based
... [87 more lines]
```

[_Output shortened for brevity_]

This command option could be very useful for outputting the contents of multiple files into a single file for output by a script. For example, a grader can take all of outputs from all Unit Tests, and then create a single file to be seen by the grader. 
