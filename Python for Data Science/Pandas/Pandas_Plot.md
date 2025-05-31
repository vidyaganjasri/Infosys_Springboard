# General Syntax:
```python
df.plot(x='X_COLUMN', y='Y_COLUMN', marker='shape', kind='plot_type')
```

---

## Scatter Plot for acceleration over the year's
```python
df.plot(x='model_year',y='acceleration',marker='o',kind='scatter')
```
![image](https://github.com/user-attachments/assets/76457a0e-9c89-4189-9442-afacb56d7a07)

### Scatter Plot Explanation: Acceleration vs Model Year

- **X-axis:** model_year (e.g., 1970, 1971, ..., 1982)  
- **Y-axis:** acceleration (how quickly a car speeds up)  

Each **dot** on the scatter plot represents **one car**.

---

#### What the dots mean:

| Situation                         | Meaning                                           |
|----------------------------------|-------------------------------------------------|
| Dots are close together (clustered) | Many cars in that year have similar acceleration |
| Dots are spread out vertically   | Cars in that year have a wide range of acceleration |
| Dots are higher up               | That car has high acceleration (faster pickup)  |
| Dots are lower                  | That car has low acceleration (slower pickup)   |
| Dots move upward over years      | Acceleration has improved over time              |
| Dots move downward               | Cars are becoming slower to accelerate           |
| Empty year or few dots           | Fewer cars in that year (less data)              |


### Bar Plot Explanation: Mean Acceleration by Year

- The code groups the data by `model_year` — meaning it gathers all cars made in the same year together.
- It then calculates the **average (mean) acceleration** for each year.
- Finally, it plots these average acceleration values as a **bar plot**.

---

#### What the bars mean:

| Bar height                 | Meaning                                             |
|----------------------------|---------------------------------------------------|
| Taller bar                 | Cars in that year had higher average acceleration (faster) |
| Shorter bar                | Cars in that year had lower average acceleration (slower)  |
| Different bar heights      | Shows how acceleration changes across the years          |

---

#### Use:

- Quickly compare the **average acceleration** of cars between different years.
- See if cars got faster or slower on average as years passed.

```python
df.groupby('model_year')['acceleration'].mean().plot(kind='bar')
```
![image](https://github.com/user-attachments/assets/d6f34a9d-a1ac-4c8c-ab8d-fa76389f9638)


### Histogram Explanation: Distribution of Cylinders

- `df['cylinders']` selects the column with the number of cylinders in each car.
- `.plot(kind='hist')` creates a **histogram**, which shows how many cars have a certain number of cylinders.

---

#### What the histogram means:

| Bars in histogram           | Meaning                                           |
|----------------------------|-------------------------------------------------|
| Taller bar at a number     | More cars have that many cylinders               |
| Shorter bar at a number    | Fewer cars have that many cylinders              |
| Bars spread out            | Cylinders vary a lot across cars                  |

---

#### Use:

- Quickly see which cylinder counts are most common in the dataset.
- Understand the frequency (count) of cars with different cylinder numbers.

What is a histogram?
A histogram shows how many times each value appears in a single column.

Your code:
python
Copy code
df['cylinders'].plot(kind='hist')
What’s happening here:
You give one column (cylinders) to pandas.

The x-axis is automatically the values inside the 'cylinders' column (like 4, 6, 8).

The y-axis is automatically the count of how many cars have each of those cylinder numbers.



```python
df['cylinders'].plot(kind='hist')
```
![image](https://github.com/user-attachments/assets/079362b2-4b91-4a91-bf3c-f78611bac228)


### Scatter Plot: Weight vs. MPG

- **X-axis:** weight of the car  
- **Y-axis:** miles per gallon (mpg) - fuel efficiency  
- Each dot = one car's weight and mpg

---

#### What the dots mean:

| Dot Position       | Meaning                          |
|--------------------|---------------------------------|
| Far right (high x) | Heavier car                     |
| Far left (low x)   | Lighter car                     |
| Higher up (high y) | More fuel efficient (better mpg)|
| Lower down (low y) | Less fuel efficient             |

---

#### What to look for:

- If dots slope downward (from left to right), it means **heavier cars usually have lower mpg** (negative correlation).
- Helps understand the relationship between weight and fuel efficiency.
```python
df.plot(x = 'weight', y = 'mpg', kind = 'scatter')
```
![image](https://github.com/user-attachments/assets/19d11d05-959a-4c03-915d-c9c9399fc22d)

---

## 📊 Visualizing Average Acceleration by Cylinders

This plot helps us understand how car acceleration varies with the number of cylinders.
How it knows X and Y:
The index of the grouped and averaged Series becomes the X-axis.

In this case: df['cylinders'] → this becomes X (the number of cylinders).

The values (mean of acceleration) become the Y-axis.
### ✅ Code

```python
pd.to_numeric(df['acceleration'], errors='coerce') \
  .dropna() \
  .groupby(df['cylinders']) \
  .mean() \
  .sort_values() \
  .plot(kind='bar')
```
![image](https://github.com/user-attachments/assets/69e6f0d3-27f1-4d63-8a37-65ade3d91426)

