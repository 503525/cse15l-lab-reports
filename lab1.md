# Lab Report 1 - Remote Access and FileSystem (Week 1)

## Command 1: `cd`

### Example 1: Using the command with no arguments.

In this example, we run the `cd` command from the home directory (Path: `\home`):
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
Notice that nothing happened. The `cd` command is designed to change the working directory to the one specified by the argument (if provided). We did not provide a directory to change to; thus, the command does not change the working directory. 

It's important to note that this is **not** an error. The command is working as intended.

### Example 2: Using the command with a path to a directory as an argument.

In this example, we run the `cd` command from the home directory (Path: `\home`):
```
[user@sahara ~]$ cd lecture1
[user@sahara ~lecture1]$ 
```
The command did not produce any output. However, the prompt has changed; it now contains lecture1, indicating that the current working directory has changed to lecture1. Indeed, printing the working directory with `pwd` returns `\home\lecture1`. 

This reflects the intended behavior of cd, and is not an error.

### Example 3: Using the command with a path to a file as an argument.

In this example, we run the `cd` command from the home directory (Path: `\home\lecture1`):
```
[user@sahara ~]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~lecture1]$ 
```
The cd command is designed to take in a path to a directory as an argument, and then change the working directory to that argument. However, in this example, we supplied a path to a file as the argument instead of a directory. This results in an error, as indicated by the output: "`Not a directory`".


---

## Command 2: `ls`

### Example 1: Using the command with no arguments.

### Example 2: Using the command with a path to a directory as an argument.

### Example 3: Using the command with a path to a file as an argument.



## Command 3: `cat`

### Example 1: Using the command with no arguments.

### Example 2: Using the command with a path to a directory as an argument.

### Example 3: Using the command with a path to a file as an argument.

