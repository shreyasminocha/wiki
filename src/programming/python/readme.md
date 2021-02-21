# Python

```python
if low <= num <= high: # this works!
    pass
```

```python
from itertools import product as cartesian_product

print(cartesian_product(['a', 'f', 'd'], [3, 4, 5]))
```

```python
from functools import reduce
from operators import mul

print(reduce(mul, [5, 9, 2, 10, 4]))
```