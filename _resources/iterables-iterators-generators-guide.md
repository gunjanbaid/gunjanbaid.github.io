---
layout: page
title: Iterables, Iterators, and Generators Guide
---

## Iterables, Iterators, and Generators Guide

# What's the point of iterators and generators? 
 
* Iterators and generators allow you to generate sequences.
* But we already have tons of ways to generate sequences. For example, we can use a data structure such as a list and append elements to the list. What additional benefit do iterators and generators give us?
* Iterators and generators allow you to generate values only when you need them! If you want to generate the first 100 prime numbers but only need them one at a time, there's no need to calculate all 100 and save them somewhere. You can just generate each one on-the-fly. 
* The 2 benefits of generating values on-the-fly (also called lazy evaluation):
* You only do work when values are needed. 
* You save space on your computer by not storing values you don't currently need. 
* In addition, iterators and generators allow you to generate infinite sequences. This is pretty crazy considering that you only have a finite amount of space on your computer. How can you use a finite amount of space to generate infinite things?! You can do this by only keeping track of one value at a time! When you are done with a value, you can generate the next value in the sequence and forget about the previous one.
 
# Basic Definitions
 
Iterables
* Characterized by an __iter__ method
* The __iter__ method returns some iterator object (for example, in the str class, the __iter__ method returns an object of the str_iterator class)

``` 
>>> x = "hi"		# x is an iterable
>>> type(x)
<class 'str'>
>>> type(iter(x))
<class 'str_iterator'>
>>> x == iter(x)	# x is different from it's iterator
False
```

Iterators 
* Characterized by a __next__ method
* Also have an __iter__ method, but that's not what makes them an iterator
* The __iter__ method just returns self

``` 
>>> x = iter([1, 2, 3])			# x is an iterator
>>> x
<list_iterator object at 0x10123cc88>
>>> type(x)
<class 'list_iterator'>
>>> type(iter(x))
<class 'list_iterator'>
>>> x == iter(x)		# x is the same as it's iterator!
True
```

Generator functions and Generators 
* Generator functions are functions that have a yield in them instead of return
* Generator functions return generators
* Generators are actually just iterators! You can call iter and next on them!
* We use generator functions because they are often easier to write than iterators.
 
``` 
>>> def ones_generator():
...     while True:
...         yield 1
... 
>>> x = ones_generator()
>>> x
<generator object ones_generator at 0x1013db5a0>
>>> type(x)
<class 'generator'>
>>> iter(x) == x
True
>>> next(x)
1
```

* Generator functions usually have some sort of loop (i.e. while True:)
* When next is called, the code goes through some loop until a yield is reached and stops at the yield. When next is called in the future, the code will pick up from the yield, go through some loop again, and stop at the yield again. 

``` 
# an infinite generator that produces 1s

def ones_generator():
	while True:		# loop condition is always True, loop never ends
		yield 1		# start here, go through loop, stop here when next is called 
```

Note on Magic Methods vs. Functions
 
* You may have noticed that I seem to switch back and forth between __iter__ vs. iter and __next__ vs. next in the examples above.
* The two notations are equivalent and produce the same output. This is because when you call iter, python is actually calling the __iter__ method, and same with next and __next__.
 
# How for Loops Work
 
A simple for loop:

``` 
>>> counts = [1, 2, 3]
>>> for item in counts:
	print(item)

1
2
3
```

What's actually going on is shown below. When executing a for statement, __iter__ returns an iterator and __next__ provides each item. 
 
``` 
>>> counts = [1, 2, 3]
>>> items = counts.__iter__()
>>> try:
	while True:
 		item = items.__next__()
 		print(item)
    except StopIteration:
	pass # Do nothing

1
2
3
```
