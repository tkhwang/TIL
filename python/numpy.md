# numpy

```python
import numpy as np
```

```python
np.array
np.zero
np.random.rand(3,4)
```

## read file

```python
np.genfromtxt("XXXX.csv", delimiter=",", skip_header=1)
```

## [numpy.array](https://docs.scipy.org/doc/numpy/reference/generated/numpy.array.html)

```python
numpy.array(object, dtype=None, copy=True, order='K', subok=False, ndmin=0)

# Parameters:
- ndmin : int, optional
Specifies the minimum number of dimensions that the resulting array should have. Ones will be pre-pended to the shape as needed to meet this requirement.

# Returns:
- out : ndarray
An array object satisfying the specified requirements.
```




## [numpy.random.normal](https://docs.scipy.org/doc/numpy/reference/generated/numpy.random.normal.html)

```
numpy.random.normal(loc=0.0, scale=1.0, size=None)

# Parameters:	
- loc : float or array_like of floats 
        Mean (“centre”) of the distribution.
- scale : float or array_like of floats 
        Standard deviation (spread or “width”) of the distribution.
- size : int or tuple of ints, optional 
        Output shape. If the given shape is, e.g., (m, n, k), then m * n * k samples are drawn. If size is None (default), a single value is returned if loc and scale are both scalars. Otherwise, np.broadcast(loc, scale).size samples are drawn.

#Returns:	
- out : ndarray or scalar 
        Drawn samples from the parameterized normal distribution.
```


