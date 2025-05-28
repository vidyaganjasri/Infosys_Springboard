# Operations on nd arrays
    
## Accessing 1d elements
```python
a = np.array([1,2,3])
print(a[1])
```
```
2
```
## Accessing 2d elements
```python
a = np.array([[1,2,3],[4,5,6]])
print(a[0])
print(a[1])
print(a[0][1])
```
```
[1 2 3]
[4 5 6]
2
```

---

## Slicing 
[start:end:jump]
end is exclusive
- 1D
```python

arr = np.array([10, 20, 30, 40, 50])

print(arr[1:4])     # From index 1 to 3 (not including 4)
print(arr[:3])      # From beginning to index 2
print(arr[2:])      # From index 2 to end
print(arr[-3:])     # Last 3 elements
```
```
[20 30 40]
[10 20 30]
[30 40 50]
[30 40 50]
```

- 2D

```python
arr = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])

print(arr[0:2]) #first 2 rows
print('\n')
print(arr[:,0:2]) #first 2 col
print('\n')
print(arr[1:,1:]) #1 row from 1 col that particular block

```
```
[[1 2 3]
 [4 5 6]]


[[1 2]
 [4 5]
 [7 8]]


[[5 6]
 [8 9]]
```

## Mean & Median 
```python
a = np.array([1,2,3,4,4])
print(np.mean(a))
print(np.median(a))
```
```
2.8
3.0
```

## Min & Max
```python
a = np.array([1,2,3,4,4])
print(np.min(a))
print(np.max(a))
```
```
1
4
```

## Querying/Searching 
Returns the indices
```python 
a = np.array([1,2,3,4,5,6,7,8])
x = np.where(a>=5)
print(x)
```
```
(array([4, 5, 6, 7], dtype=int64),)
```


## Filtering 
Getting some elements out of an existing array based on certain conditions 
and creating a new array out of them is called filtering
```python
a = np.array([1,2,3,4,5,6,7,8])
filter = a>=5
print(filter)
print(a[filter])
```
```
[False False False False  True  True  True  True]
[5 6 7 8]
```

## Sorting
Can be sorted using np.sort(array) and array.sort()
- np.sort(array) will not sort in place
- array.sort() will sort in place

### np.sort(arr)
``` python
a = np.array([4,3,7,2,8])
print(np.sort(a))
print(a)
```
```
[2 3 4 7 8]
[4 3 7 2 8]
```
### arr.sort()

```python
a = np.array([4,3,7,2,8])
a.sort()
print(a)
```
```
[2 3 4 7 8]
```
---
## Vectorized operations
This allows us to perform operation on the entire array at once without writng loops

## Add two arrays
```python
a = np.array([1,2,3])
b = np.array([5,6,7])
c = a+b
print(c)
```
```
[ 6  8 10]
```

## Multiply
```python
a = np.array([1,2,3])
res = a*2
print(res)
```
```
[2 4 6]
```
Similarly **%,-,*,**

## Broadcasting
The Rule in Simple Words:
Starting from the right side, compare each dimension:

- If they are the same number → perfect.

- If one of them is 1 → NumPy will stretch that dimension.

- Otherwise → it can’t work.

