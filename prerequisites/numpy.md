# Numpy Basic crash course
* Python calls matrices lists, NumPy calls them arrays and TensorFlow calls them tensors. 
* Python represents matrices with the list data type.




```python
import numpy as np
```

* Create arrays


```python
one_dimensional_array = np.array([1.2, 2.4, 3.5, 4.7, 6.1, 7.2, 8.3, 9.5])
two_dimensional_array = np.array([[6, 5], [11, 7], [4, 8]]) # 3x2
```

* Populate arrays with specific numbers


```python
np_zeroes = np.zeros((3, 4)) # 3x4
np_ones = np.ones((2, 3)) # 2x3
np_sevens = np.full((3, 3), 7) # 3x3
```

* Sequence like [5, 6, 7, 8, 9, 10, 11]


```python
sequence_of_integers = np.arange(5, 12)
```

### Generating random numbers
* Note : the high value is exclusive


```python
# random numbers between 50 and 100 -> range [50, 100)
random_integers_between_50_and_100 = np.random.randint(low=50, high=101, size=(6,))
# random numbers between 50 and 100 2D array
random_integers_between_50_and_100_2D = np.random.randint(low=50, high=101, size=(3, 4))
# random numbers between 0.0 and 1.0 1D array
random_floats_between_0_and_1 = np.random.random((6))
# random numbers between 0.0 and 1.0 2D array
random_floats_between_0_and_1_2D = np.random.random((3, 4))
```

### Task 1: Create a Linear Dataset

Your goal is to create a simple dataset consisting of a single feature and a label as follows:

1. Assign a sequence of integers from 6 to 20 (inclusive) to a NumPy array named `feature`.
2. Assign 15 values to a NumPy array named `label` such that:

```
   label = (3)(feature) + 4
```
For example, the first value for `label` should be:

```
  label = (3)(6) + 4 = 22
 ```


```python
feature = np.arange(6,21)
label = feature*3 + 4
print(label)
```

    [22 25 28 31 34 37 40 43 46 49 52 55 58 61 64]


### Task 2: Add Some Noise to the Dataset

To make your dataset a little more realistic, insert a little random noise into each element of the `label` array you already created. To be more precise, modify each value assigned to `label` by adding a *different* random floating-point value between -2 and +2. 

Don't rely on broadcasting. Instead, create a `noise` array having the same dimension as `label`.


```python
noise = np.random.uniform(size=15,low=-2,high=2)
label = label + noise
print(label)
```

    [22.82754982 26.56508528 28.50520693 30.21625854 35.31760056 35.87802062
     38.97811582 44.97159835 45.79233557 48.52336693 50.41740174 56.86335759
     57.11022276 61.04054926 65.4972321 ]

