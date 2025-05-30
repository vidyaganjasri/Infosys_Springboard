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

