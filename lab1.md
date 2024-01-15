# Lab Report 1 - Remote Access and FileSystem (Week 1)

## Command 1: `cd`

### Example 1: Using the command with no arguments.

In this example, we run the `cd` command from the home directory (Path: `/home`):
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
Notice that nothing happened. The `cd` command is designed to change the working directory to the one specified by the argument (if provided). We did not provide a directory to change to; thus, the command does not change the working directory. 

It's important to note that this is **not** an error. The command is working as intended.

### Example 2: Using the command with a path to a directory as an argument.

In this example, we run the `cd` command from the home directory (Path: `/home`):
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
```
The command did not produce any output. However, the prompt has changed; it now contains lecture1, indicating that the current working directory has changed to lecture1. Indeed, printing the working directory with `pwd` returns `/home/lecture1`. 

This reflects the intended behavior of cd, and is not an error.

### Example 3: Using the command with a path to a file as an argument.

In this example, we run the `cd` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ 
```
The cd command is designed to take in a path to a directory as an argument, and then change the working directory to that argument. However, in this example, we supplied a path to a file as the argument instead of a directory. This results in an error, as indicated by the output: "`Not a directory`".


---

## Command 2: `ls`

### Example 1: Using the command with no arguments.

In this example, we run the `ls` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
[user@sahara ~/lecture1]$ 
```
The `ls` command is designed to print out the names of everything that is inside a given directory. When we do not provide any arguments to the command, it acts on the current working directory.

In this case, we are using the command from within `/home/lecture1`, which is a directory that contains a java file (`Hello.java`), a java class file (`Hello.class`), a text file (`README`), and a directory (`messages`). Notice that all of these were included in the output after the command was entered. 

Thus, the command executed properly, and no error occurred. 


### Example 2: Using the command with a path to a directory as an argument.

In this example, we run the `ls` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ ls messages
en-us.txt  es-mx.txt  zh-cn.txt
[user@sahara ~/lecture1]$ 
```
Once again, the `ls` command is used to print out names of everything within a specified directory. In this case, we supplied the relative path to `/home/lecture1/messages` as an argument for the command. 

This directory contains three text files: `en-us.txt`, `es-mx.txt` and `zh-cn.txt`. The three can be seen included in the output, directly underneath the command itself.

Also, notice that the prompt remains unchanged; this indicates that the current working directory remains unchanged.

This reflects the intended use and behavior of the `ls` command, and no error has occurred in this case. 

### Example 3: Using the command with a path to a file as an argument.

In this example, we run the `ls` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$ 
```
When we use the `ls` command with a path to a file as an argument, the command outputs the name of the file. 

This output is not an error.



## Command 3: `cat`

### Example 1: Using the command with no arguments.

### Example 2: Using the command with a path to a directory as an argument.

### Example 3: Using the command with a path to a file as an argument.

