# Python Lists and Data Science

A **Python List** is used to store a group of elements together in a sequence. It can contain different types of elements (heterogeneous).

## Examples of Lists

```python
item_list = ['Bread', 'Milk', 'Eggs', 'Butter', 'Cocoa']
student_marks = [78, 47, 96, 55, 34]
hetero_list = [1, 2, 3.0, 'text', True, 3+2j]
```

## Performing Operations on List Elements

To perform operations on list elements, you usually iterate through the list.  
For example, if you want to add 5 marks to every student's score in the `student_marks` list, you can do:

```python
student_marks = [78, 47, 96, 55, 34]
for i in range(len(student_marks)):
    student_marks[i] += 5
print(student_marks)
```
**Note:** This uses a loop. The code becomes longer and slower as the list size grows.

## Why Use Better Tools in Data Science?

Data Science uses scientific methods and algorithms to get useful insights from data. These insights can be applied in many areas.

Since Data Science works with large datasets, using plain Python lists and loops for data operations is:

- Time-consuming  
- Computationally expensive

That’s why better tools (like **NumPy** and **Pandas**) are preferred, as they handle large data efficiently without slow loops.
