# Operations in python 
---
## 🔍 Understanding Filtering in Pandas

Filtering means selecting only the rows that match a condition.

---

### 🧠 Basic Syntax

```python
df[condition]
```
You give a condition, and pandas returns the rows that match it.

---
## Problem statement : Retrieve details of all the cars built in year 72.
```python
df.loc[df['model_year'] == 72 ].head()
```
![image](https://github.com/user-attachments/assets/071c21f5-5edb-478f-984b-5d3095631ff6)

---
## Problem statement : Retrieve details of all the cars built in Japan having 6 cylinders

```python
df.loc[(df['origin'] == 'japan') & (df['cylinders'] == 6)]
```
![image](https://github.com/user-attachments/assets/f26bd7b4-09b7-4733-b7e4-752a9f768cd5)


---


## Masking Operation

The masking operation replaces values where the condition is True.
```python
DataFrame.mask(condition, value_to_put)
```
If cond is true, it replaces the value that we provide, else keeps the original 
value 

### For Example: 
teacher does not want to reveal the marks of the students who have failed.
the cond is that if the marks <33, then marks of stu has to be replaced with 'Fail'
![image](https://github.com/user-attachments/assets/5381b438-3b84-4cae-9428-e2a2110f5800)


### Solution: 

![image](https://github.com/user-attachments/assets/a865486d-0cc4-449e-8c23-b37c267c18bd)

---

## Sorting Data 

```python
df.sort_values(by = 'cylinders')
```
![image](https://github.com/user-attachments/assets/c665d263-fdbb-4683-8137-afcf5cd263e0)

---

## Preserving Index 

Transforming data(Encrypting marks)

![image](https://github.com/user-attachments/assets/d27fc5f2-f4b9-4b2c-a2c8-006a9a2a7122)


Resetting Index 

![image](https://github.com/user-attachments/assets/206971de-8249-40be-9815-9084b43a2650)

---
## Broadcasting operation
If we want to make chagnes to all the values in the data
![image](https://github.com/user-attachments/assets/54ef9a56-31be-4489-9339-ee5121c6161f)

```python
new_marks = marks_df + 5
new_marks
```
![image](https://github.com/user-attachments/assets/797767f3-7e78-4f7d-a0d0-9a4e107c23ac)

## Aggregation Operations in Pandas

Aggregation operation is used to aggregate using one or more operations over the specified axis.

```python
#Using list comprehension to get the numerical columns
list1 = [col for col in df.columns if df[col].dtype in ['float', 'int64']]
df[list1].agg(['min', 'max'])
```


![image](https://github.com/user-attachments/assets/cb62228d-ca84-4fd0-9653-5b360e865cde)


## Grouping operations in Pandas

to know the number of cars manufactured 

```python
df.groupby(['model_year']).count()[['name']]
```
df.groupby(['model_year']).count()[['name']]

---

## Concatinating DataFrames 

Want to combine the marks of students

```python
marks_A = {'Chemistry': [67,90,66,32], 
        'Physics': [45,92,72,40],  
          }
marks_A_df = pd.DataFrame(marks_A, index = ['Subodh', 'Ram', 'Abdul', 'John'])
marks_B = {'Chemistry': [72,45,60,98], 
        'Physics': [78,34,72,95],  
          }
marks_B_df = pd.DataFrame(marks_B, index = ['Nandini', 'Zoya', 'Shivam', 'James'])
```

```python
pd.concat([marks_A_df,marks_B_df], sort = False)
```
![image](https://github.com/user-attachments/assets/8149b95a-eae4-4e41-b37c-d20a35f3eab3)

---

## Pivot Table 

What does the pivot table do?
Imagine you have a big table of cars. Each row is a car, and each car has:

A year

Some numbers like horsepower, weight, mileage, etc.

Now, you want to know:

“For each year, what is the average horsepower, weight, mileage, etc. of all cars in that year?”

✅ That’s exactly what the pivot table does!
You just tell it:

index='Year' → group the cars by year

aggfunc='mean' → and take the average of the numbers

So yes — for each year, you get one row, and in that row you see the average value of each column.

```python
import pandas as pd

# Suppose df is the DataFrame
pd.pivot_table(df, index='Year')

```
![image](https://github.com/user-attachments/assets/70b9a0ed-1011-4e75-9227-008ea3413b5f)

