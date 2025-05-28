Images are stored as arrays of millions of picture elements called as pixels, 
therefore, images can also be treated as NumPy array, as they can be represented
as matrix of pixels

# What are we doing?
We are loading and displaying a picture of an astronaut using python code. 

```python
import os.path
from skimage.io import imread
from skimage import data_dir
import matplotlib.pyplot as plt
```

- **import os.path**: this helps the computer to find the files on the system,no matter what type of system we have
- **from skimage.io import imread**:  we are using a tool imread this allows us to load pictures and work with them
- **from skimage import data_dir**:  This is a folder where sample pictures are stored like the astronaut
- **import matplotlib.pyplot as plt**: Tool to show pictures on screen

 ```python
img = imread(os.path.join(data_dir, 'astronaut.png'))
```
- os.path.join(data_dir, 'astronaut.png'): tells the computer where the pic is
- imread(...): loads the image and stores inside `img`

```python
plt.imshow(img)
```
To display the image 

```python
print(img)
print('Type of image: ', type(img))
print('Dimensions of image: ', img.ndim)
print('Shape of image:', img.shape)
```
- print(img) shows the actual numbers behind the pic, where each number is tiny color dot called pixel
- type(img): tells us that it is numpy array
- img.ndim: tells how many dimensions the picture has
- - if two means black and white
  - if 3 it is colored
  - EX:
  - (512,512,3) means
  - 512 pixels tall
  - 512 pixels wide
  - 3 colors per pixel(red,gree,blue)

