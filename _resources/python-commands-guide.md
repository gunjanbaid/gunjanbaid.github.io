---
layout: page
title: Python Commands Guide
---

## Python Commands Guide

There are two different modes that you will work with in terminal: outside of python and in the python interpreter. When you are outside of python, you will see your username and the directory you are in, followed by "$" on each line. When you are in the python interpreter, you will see ">>>" on each line. Unix commands (such as ls, cd, etc.) and commands that start with "python" (such as "python ok --local") can only be run when you see the "$." Python code (such as twenty_sixteen( ) from lab) can only be run when you see ">>>."
 
# Info on common commands 

``` 
gunjan_baid@111:~$ python 
```
This will start the python interpreter and can be used from any folder.
 
```
gunjan_baid@111:~$ python ok --local
```
This will run the ok autograder on the assignment you are currently working on. You must run this command from inside the assignment folder.
 
```
gunjan_baid@111:~$ python  -i lab00.py
```
This is interactive mode (note the -i) and will start python and load the code in lab00.py. This must be used from the folder in which lab00.py is located.
 
```
gunjan_baid@111:~$ python lab00.py
```
This will run the code in lab00.py and must be run from the folder in which lab00.py is located. The code that is run must be located in a special function called main (we haven't learned this yet). If there is no main function, this command will not do anything. 
 
``` 
>>>
```
This is not actually a command. The three arrows mean you are in the python interpreter and can type in python code. 
 
# How to tell which directory (aka folder) you are in

Look before the "$."
 
```
gunjan_baid@111:~$ 
```
We are in ~, which is the home folder. 

``` 
gunjan_baid@111:~/cs88$
```
We are in the cs88 folder, which is located in the home folder. 

```
gunjan_baid@111:~/cs88/labs/lab00$ 
```
We are in the lab00 folder. 
