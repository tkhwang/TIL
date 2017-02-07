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

## dot : matrix multiplication

```python
import numpy as np

x = np.array([[1,2],[3,4]])
y = np.array([[5,6],[7,8]])

v = np.array([9,10])
w = np.array([11, 12])

# 백터의 내적, v[0]*w[0] + v[1]*w[1] = 219
print v.dot(w)
print np.dot(v, w)

# 매트릭스 벡터 곱, 랭크 1 배열 [29 67]을 만든다  [x[0,0]*v[0]+x[0,1]*v[0]=29, x[1,0]*v[0]+x[1,1]*v[1]=67]
print x.dot(v)
print np.dot(x, v)

# 행렬 곱은 랭크 2 배열을 만듬. x[0,0]*y[0,0]+x[0,1]*y[1,0]=19, x[0,0]*y[0,1]+x[0,1]*y[1,1]=22, x[1,0]*y[0,1]+x[1,1]*y[1,1]=43, x[1,0]*y[0,1]+x[1,1]*y[1,1]=50
# [[19 22]
#  [43 50]]
print x.dot(y)
print np.dot(x, y)
```


