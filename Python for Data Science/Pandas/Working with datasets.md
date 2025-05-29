## Extracting from dataset 
```python
import pandas as pd
import numpy as np
df = pd.read_csv('auto_mpg.csv')
df
```

![image](https://github.com/user-attachments/assets/a81da85b-8c92-4bc9-badc-0067823abf0a)

---
### Head & Tail 
To view the first or the last  few rows 
```python
df.head()
```
![image](https://github.com/user-attachments/assets/2074def3-2789-41b7-a619-c87e327006ab)

---
```python
df.tail()
```
![image](https://github.com/user-attachments/assets/a2433dd9-14f7-4d84-a9fc-266668678b94)

---

### Describe
To genearte a summary of data statistics
```python
df.describe()
```
![image](https://github.com/user-attachments/assets/0ec2cbc6-f412-4be8-9082-ded318980646)

### Info 
To know about the data types and about the count of null values 
```python
df.info()
```
![image](https://github.com/user-attachments/assets/5b407771-65b3-4b91-8104-6f4f929fcd4e)

----
### Dropping Null Values 
If observed horsepower has some null values, hence might affect the analysis process, so the easiset solutoin would be getting rid of it, using **dropna()**
inplace means make changes to original data frame 
```python
df.dropna(inplace=True)
df.info()
```
![image](https://github.com/user-attachments/assets/8c38e793-6c77-43c6-a8db-ccdcdf58e922)
---
### Selecting 

- Passing the col name as shown
- ```python
  df['name']
  ```
  ![image](https://github.com/user-attachments/assets/512210a8-c2fa-47e3-87f9-ffda160b93d8)

- passing the col name as list
- ```python
  df[['name']]
  ![image](https://github.com/user-attachments/assets/6d4672c9-7b33-488b-ab19-db734f131ad8)

- To extract a subset, we pass the col names as list
- ```python
  df[['name','origin','horsepower']]
  ```
  ![image](https://github.com/user-attachments/assets/d35a263e-d1ac-4460-9a26-c73f40857cd9)


---
## Setting Custom Index 
```python
df_head = df.head()
df_head.set_index('name',inplace=True)
df_head
```
![image](https://github.com/user-attachments/assets/902c0d59-60b0-4555-8f08-4a9f17099e76)

---
## iloc:
Accessing elements in the 2d list  using row and col 
**df.iloc[rows,col]**

![image](https://github.com/user-attachments/assets/485d9c05-dd61-4280-bed7-f3f30c9214d3)
get the 3rd row(2) 2nd col(1) ind
```python
df.iloc[2,1]
```
```
8
```
---
![image](https://github.com/user-attachments/assets/50c536d8-3806-42d8-b5be-477c7686d941)

get the 3rd row (2) last element(-1)
```python
df.iloc[2,-1]
```
```
'plymouth satellite'
```

---
rows from 1 to 4 and col from 4 and 5 
```python
df.iloc[1:5, 4:6]
```
![image](https://github.com/user-attachments/assets/805ba2a9-dba7-4971-8621-2b7b198ec5fb)
---
## Label based indexing 
Selects all rows from 'buick skylark 320' to 'amc rebel sst' (inclusive).

This is label-based slicing.

Unlike iloc, the end value is included.

```python
df_head.loc['buick skylark 320': 'amc rebel sst']
```
![image](https://github.com/user-attachments/assets/b9d3e6f8-97df-4955-97f1-0266846b4be2)

---
## Selecting Specific Columns with loc
Select rows 0 to 5 (inclusive).

From each row, select only these columns:

- 'cylinders'

- 'horsepower'

- 'name'
```python
df.loc[0:5, ['cylinders', 'horsepower', 'name']]
```
![image](https://github.com/user-attachments/assets/b32a1159-3694-434f-a065-1470db224474)

---
## Add/Delete col
### Create a data frame 
```python
marks = {
    'Chemistry': [67,90,66],
    'English':[89,99,87]
}
marks_df = pd.DataFrame(marks,index = ['Virat','Vihan','Varahi'])
marks_df
```
```
|         | Chemistry | English |
|---------|-----------|---------|
| Virat   | 67        | 89      |
| Vihan   | 90        | 99      |
| Varahi  | 66        | 87      |
```

### Creating a new col 
```python
marks_df['Total'] = marks_df['Chemistry'] + marks_df['English']
marks_df
```
```
|         | Chemistry | English | Total |
|---------|-----------|---------|--------|
| Virat   | 67        | 89      | 156    |
| Vihan   | 90        | 99      | 189    |
| Varahi  | 66        | 87      | 153    |
```

### Deleting a col 
```python
marks_df.drop(columns='Total', inplace=True)
marks_df
```
```
|         | Chemistry | English |
|---------|-----------|---------|
| Virat   | 67        | 89      |
| Vihan   | 90        | 99      |
| Varahi  | 66        | 87      |
```
