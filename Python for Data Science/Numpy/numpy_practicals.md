# BASICS
## Importing NumPy
NumPy lib needs to be imported before using it in the env: 
```python
import numpy as np
```
np is the alias name given to it, for easy reference

- To create an object: 
### Syntax
```python
np.array(object,dtype)
```
1. a python object(list)
2.  dtype or datatype

```python
import numpy as np
student_marks = np.array([91,98,99,93])
```
## Can convert list to np array 

```python
marks = [91,93,92]
np_marks = np.array(marks)
np_marks
```

## Creating 2d arrays
```python
marks = [["Shushant","Tara","Vibhav"],[91,93,99]]
np_marks = np.array(marks)
print(np_marks)
```

## To get the shape/dim of the array 
- 1D
```python
marks_1d = [91,93,92]
np_marks_1d = np.array(marks_1d)
print(np_marks_1d.shape)
```

- 2D
```python
marks_2d = [["Shushant","Tara","Vibhav"],[91,93,99]]
np_marks_2d = np.array(marks_2d)
print(np_marks_2d)
```
- 1D shape → just number of elements: (n,)
- 2D shape → rows and columns: (rows, cols)

## dtype
- Use to know the data type of the data in the array
```python
marks_1d = [91,93,92]
np_marks_1d = np.array(marks_1d)
print(np_marks_1d.dtype)
```
```
int32
```


