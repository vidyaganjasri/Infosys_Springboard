## Importing numpy and pandas
To get started with it, we first import it 

```python
import numpy as np
import pandas as pd
```
Basic data structures of pandas are **Series** and **Data Frames**

---
## SERIES AS LISTS 
- It is one dimensional array,supports datatypes like int,float,string etc

```
pd.series(data,index,dtype)

data- list/dict
index - index can be explicitly defined for diff values
dtype - Represents the data type used in series
```

### Initializing
```python
series = pd.Series(data=[1,2,3])
series
```
```
0    3
1    4
2    5
dtype: int64
```

***Printing values***
```python
series.values
```
```
array([3, 4, 5], dtype=int64)
```
***Printing Indexes***
```python
series.index
```
```
RangeIndex(start=0, stop=3, step=1)
```

### Accessing
***Using Index***

```python
series[1]
```
```
4
```
### Sclicing
```python
series[0:2]
```
```
0    3
1    4
dtype: int64
```

### Custom Index 
```python
data = pd.Series(data=[100,200,300],index=['Vidya','Tara','Mira'])
data
```
```
Vidya    100
Tara     200
Mira     300
dtype: int64
```
---
```python
data.values
```
```
array([100, 200, 300], dtype=int64)
```
---
```python
data.index
```
```
Index(['Vidya', 'Tara', 'Mira'], dtype='object')
```
***Accessing using the custom index***
```python
data['Vidya']
```
```
100
```
---
## SERIES AS DICT 
they can also be created from dictionary 
```python
data = {
    't':21,
    'v':34,
    'm':53
}
series = pd.Series(data)
series
```
```
t    21
v    34
m    53
dtype: int64
```

---

## DATA FRAMES

- while series is a one dimensional array like object
- Data frame is a 2d table of data, where consist of rows and col, each col is a series

```python
stu_roll = {
    'vidya':147,
    'tara':187,
    'lara':164
}
stu_marks = {
    'vidya':89,
    'tara':90,
    'lara':88
}
stu_roll_series = pd.Series(stu_roll)
stu_marks_series = pd.Series(stu_marks)
stu_record = pd.DataFrame({'Roll_NO':stu_roll_series,'Marks':stu_marks_series})
stu_record
```
```
| Name  | Roll_NO | Marks |
|-------|---------|-------|
| Vidya | 147     | 89    |
| Tara  | 187     | 90    |
| Lara  | 164     | 88    |
```

---
```python
stu_record['Marks']
```
```
vidya    89
tara     90
lara     88
Name: Marks, dtype: int64
```

---

## Ways to Create Data Frames 
***Series***
```python
stu_age = {
    'vidya': 20,
    'Vihan':21,
    'vara':24
}
stu_age_series = pd.Series(stu_age)
age = pd.DataFrame(stu_age_series,columns=['Age'])
age
```
```
|       | Age |
|-------|-----|
| Vidya | 20  |
| Vihan | 21  |
| Vara  | 24  |
```

---
***From list of Dict***
```python
data = [
    {'Name':'Vihari','Age':20},
    {'Name':'Vidya','Age':23},
    {'Name':'Veka','Age':24},
]
pd.DataFrame(data)
```
```
|       | Name   | Age |
|-------|--------|-----|
| 0     | Vihari | 20  |
| 1     | Vidya  | 23  |
| 2     | Veka   | 24  |
```
---
***From dict of series of objects***
```python
stu_roll = {
    'vidya':147,
    'tara':187,
    'lara':164
}
stu_marks = {
    'vidya':89,
    'tara':90,
    'lara':88
}
stu_roll_series = pd.Series(stu_roll)
stu_marks_series = pd.Series(stu_marks)
stu_record = pd.DataFrame({'Roll_NO':stu_roll_series,'Marks':stu_marks_series})
stu_record
```
```
| Name  | Roll_NO | Marks |
|-------|---------|-------|
| Vidya | 147     | 89    |
| Tara  | 187     | 90    |
| Lara  | 164     | 88    |
```
---
***From an existing file***
```python
ata_json = pd.read_json('example.json',)
data_json
```

