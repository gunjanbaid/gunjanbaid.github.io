---
layout: page
title: Trees Guide
---

## Trees Guide

The pseudocode examples below are designed to show you how to approach tree problems that are on Lab 3. 
 
NOTE: This is not real code, this is pseudocode, it's just to give you an idea of how to structure your own code. All examples below are a basic structure, you will need to add additional base cases/conditions/etc. depending on the problem. 
 
 
# 1. If you want to return a new tree:

```
function(tree)
	new root = some computation on root
	new branches = []
	for each branch:
		new branches += [function(branch)]
	return tree(new root, new branches)
 ```

Alternative solution for returning a new tree, using list comprehension:

```
function(tree)
	return tree(some computation on root, [function(branch) for each branch])
```

# 2. If you want to mutate a tree:

```
function(tree)
	some computation on root
	for each branch:
		function(branch)
```
