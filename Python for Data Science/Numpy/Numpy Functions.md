# Numpy Functions
## Arrange
returns a consecutive list of numbers starting from first input and going upto, but 
excluding the second input
```python
np.arange(0,10)
```
```
array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
```
## Linspace
It helps you to return a list specific number of values ranging between the given start and end point, 
spaced evenly.
```python
arr = np.linspace(1,10,4)
print(arr)
```
```
[ 1.  4.  7. 10.]
```

## Zeros
returns an array of provided input at shape filled with zeros
```python
a = np.zeros(5)
print(a)
```
```
[0. 0. 0. 0. 0.]
```

## Ones
returns an array of provided input as shape filled with ones 
```python
a = np.ones([1,2])
print(a)
```
```
[[1. 1.]]
```

## Full 
returns an array of given shape filled with the give value irrespetive of the input data type
```python
a = np.full([1,5],"hi")
print(a)
```
```
[['hi' 'hi' 'hi' 'hi' 'hi']]
```

## Eye
returns an identity matrix of the given input 
```python
a = np.eye(4)
print(a)
```
```
[[1. 0. 0. 0.]
 [0. 1. 0. 0.]
 [0. 0. 1. 0.]
 [0. 0. 0. 1.]]
```

## Random
- Random.rand()
```python
np.random.rand(5)
```
```
array([0.95859923, 0.24573162, 0.14805916, 0.87225337, 0.48619975])
```

- np.random.randint(low,high,size=val)
- - np.random.randint(low, high, size=val) generates val random integers between low (inclusive) and high (exclusive).
```python
np.random.randint(1,10, size=5)
```
```
array([1, 3, 9, 8, 2])
```



