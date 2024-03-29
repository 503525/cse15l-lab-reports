# Lab Report 1 - Remote Access and FileSystem (Week 1)

## Command 1: `cd`

### Example 1: Using the `cd` command with no arguments.

In this example, we run the `cd` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ 
```
Notice that the prompt changed. This is because, without arguments, the `cd` command takes the user to the home directory by default. In fact, using the `pwd` command from here tells us that the current working directory has changed to `/home`, which is the home directory.

It's important to note that this is **not** an error. The command is working as intended.

### Example 2: Using the `cd` command with a path to a directory as an argument.

In this example, we run the `cd` command from the home directory (Path: `/home`):
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
```
The command did not produce any output. However, the prompt has changed; it now contains lecture1, indicating that the current working directory has changed to lecture1. Indeed, printing the working directory with `pwd` returns `/home/lecture1`. 

This reflects the intended behavior of cd, and is not an error.

### Example 3: Using the `cd` command with a path to a file as an argument.

In this example, we run the `cd` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ 
```
The cd command is designed to take in a path to a directory as an argument, and then change the working directory to that argument. However, in this example, we supplied a path to a file as the argument instead of a directory. This results in an error, as indicated by the output: "`Not a directory`".


---

## Command 2: `ls`

### Example 1: Using the `ls` command with no arguments.

In this example, we run the `ls` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
[user@sahara ~/lecture1]$ 
```
The `ls` command is designed to print out the names of everything that is inside a given directory. When we do not provide any arguments to the command, it acts on the current working directory.

In this case, we are using the command from within `/home/lecture1`, which is a directory that contains a java file (`Hello.java`), a java class file (`Hello.class`), a text file (`README`), and a directory (`messages`). Notice that all of these were included in the output after the command was entered. 

Thus, the command executed properly, and no error occurred. 


### Example 2: Using the `ls` command with a path to a directory as an argument.

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

### Example 3: Using the `ls` command with a path to a file as an argument.

In this example, we run the `ls` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$ 
```
When we use the `ls` command with a path to a file as an argument, the command outputs the name of the file. 

This output is not an error.

---

## Command 3: `cat`

### Example 1: Using the `cat` command with no arguments.

In this example, we run the `cat` command from the lecture1 directory (Path: `/home/lecture1`):
```
[user@sahara ~/lecture1]$ cat

```
The `cat` command is used to concatenate and output the contents of files that we include in the arguments. However, in this example, we passed no arguments to the command. 

Notice that the prompt is missing in the line directly after the command. The terminal will now output a copy of anything that is typed, instead of accepting commands. For example, we can type "Hello World!" into the terminal, yielding the following result:
```
[user@sahara ~/lecture1]$ cat
Hello World!
Hello World!

```
It's important to note that no error message is present, and this new input mode can be exited at any time with **[CTRL]+[SHIFT]+D**. This is one indication that this is not an error.

### Example 2: Using the `cat` command with a path to a directory as an argument.

In this example, we run the `cat` command from the home directory (Path: `/home`):
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$
```
The cat command is not designed to operate on a directory. This causes an error. Notice that the output is an error message which indicates what went wrong; "`lecture1: Is a directory`".

### Example 3: Using the `cat` command with a path to a file as an argument.

In this example, we run the `cat` command from the lecture1 directory (Path: `/home/lecture1`).
```
[user@sahara ~/lecture1]$ cat README
To use this program:

javac Hello.java
java Hello messages/en-us.txt
[user@sahara ~/lecture1]$ 
```
In this example, the file `/home/lecture1/README` contains instructions on how to compile and run the Hello.java program included in the lecture1 folder. These instructions make up the output of the cat command shown above.

This reflects the intended use and behavior of this command, and is therefore not an error.
