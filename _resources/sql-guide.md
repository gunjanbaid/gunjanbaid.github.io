---
layout: page
title: SQL Guide
---

## SQL Guide

This guide may be updated with more info in the future, keep checking back if you are stuck! Reference to questions are from Lab 8.

# 0. How queries get evaluated

Sample queries below and an explanation of how to think about order of evaluation. General order of evaluation: join specified tables to create new table, filter out rows/groups you don't want from new table, select specified columns from filtered new table. Note, the actual process is much more complex than what I've stated above in order to be efficient. But the explanations below are the level of understanding we want you to have for this class. 
 
Let's work with the following tables:

``` 
students 
name	sid	
Alice	10
Bob	20
Judy	30
 
grades
sid	course	grade	
10	CS88	A
20	CS88	B
30	CS88	B
 
Query 1
SELECT students.name, grades.course, grades.grade
FROM students, grades
WHERE students.sid = grades.sid;
```
 
Explanation for Query 1  
Step 1: Join the two tables to produce the below table.

```
name	sid	sid 	course 	grade
Alice	10	10	CS88	A
Alice	10	20	CS88	B
Alice	10	30	CS88	B
Bob	20	10	CS88	A
Bob	20	20	CS88	B
Bob	20	30	CS88	B
Judy	30	10	CS88	A
Judy	30	20	CS88	B
Judy	30	30	CS88	B
```

Step 2: Go through above table row by row and filter out rows that don't meet the where condition. We want to join based on the sid value. We don't want rows where the sid is not the same. This leaves us with the below table. 

```
name	sid	sid 	course 	grade
Alice	10	10	CS88	A
Bob	20	20	CS88	B
Judy	30	30	CS88	B
```

Step 3: Select the columns you want. I used table names to be clear about which columns I'm referring to. SQL knows which column came from which original table. So it knows the difference between students.sid and grades.sid. The select leaves us with the following table, which is the desired output:

```
name	course 	grade
Alice	CS88	A
Bob	CS88	B
Judy	CS88	B
```

# 1. Renaming columns (Q3)

You can rename columns in the table you create using the as keyword. For example, let's select the names column from the dogs table and rename it to dog_names:

```
select name as dog_names
from dogs;

abraham
barack
clinton
delano
eisenhower
fillmore
grover
herbert
```

# 2. Grouping and aggregate functions (Q6)

SQL allows you to group data by the value of a certain column and then use various functions on those groups. A few examples of aggregate functions you can use:
count(*) - counts the number of rows in the group
min(col_name) - min value of col_name in the group
max(col_name) - max value of col_name in the group

Group by is supposed to be used with an aggregate function. However, aggregate functions can be used without the group by. For example, we can count all the rows in the dogs table:

```
select count(*)
from dogs;

8
```

Let's see how to combine group by and aggregate functions. Here is a sample query for how to obtain the number of children that each parent has:

```
select parent, count(*)
from parents
group by parent;

abraham|2
delano|1
eisenhower|1
fillmore|3
```

Important takeaway: the aggregate function will be applied to each group if group by is used. If group by is not used, the aggregate function will be applied to the whole table.

Another example of grouping and aggregation. Let's create a table of parent name and height of the tallest child of that parent.

```
select parent, max(height)
from parents, dogs
where child = name 
group by parent;

abraham|52
delano|31
eisenhower|32
fillmore|46
```

# 3. Filtering groups (Q6)

`where` clauses allow you to filter out unwanted rows in SQL. having clauses help you filter out unwanted groups. For example, let's create a table of parents that have more than 1 child:

```
select parent
from parents 
group by parent
having count(*) > 1;

abraham
fillmore
```

The having is applied to each group, and only groups that have > 1 row are kept. Only Abraham and Fillmore have > 1 child, hence they are returned in the result. You can have multiple having clauses in a query. 

# 4. Other notes on SQL

Floor division syntax is done using one division bar in SQL. For example, 10/3 will evaluate to 3. (You don't need // as you do in Python.)
Don't forget the semicolon at the end of a query!
Comments in SQL are preceded by "--", not "#" so make sure your comments are formatted correctly, otherwise you will get errors. For example:

```
# not a SQL comment, will error
-- good SQL comment, won't error
```

* Check out my formatting for the queries above. It really helps improve readability with that sort of formatting, as opposed to putting everything in one line.
* Our goal is for CS88 students to be able to write basic queries in SQL. You should definitely have an understanding of how the operators such as select, group by, etc. are used. But don't worry if you don't have a detailed understanding of how these things actually work. (For example, how exactly does sqlite compute the table joins and give you the right values in the output?) Questions like this have very in-depth answers. In fact, there's a whole class dedicated to answering these questions: CS186. If you're interested in learning more, there are tons of resources for SQL online. Feel free to ask me about it in Office Hours as well! 
* SQL is super super useful! You are likely to come across this stuff again at some point (internships, research, etc.) so study up!! :)
