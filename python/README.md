# Python basics

- Variable 은 `letter` 혹은 `_`로 시작해야 함. 즉 `2a` 와 같이 숫자가 먼저 오면 에러가 발생함.

## Chained operation

```python
In [1]: 1 < 2 < 3
Out[1]: True


In [2]: 1 < 2 > 3
Out[2]: False
```

## Dictionary

- Dictionary comprehension

```python
In [18]: d = {"a": 1, "b": 2, "c": 3}


In [19]: d = dict((key, value) for key, value in d.items() if value <= 1)


In [20]: print(d)
{'a': 1}
```

- `dictionary.items()` : `key` : `value`

```python
for key, value in d.items():
	XXX
```


## Math

- `from math import pi`


## `pprint`

- `from pprint import pprint`


```python
# print(d)
{'a': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 'b': [11, 12, 13, 14, 15, 16, 17, 18, 19, 20], 'c': [21, 22, 23, 24, 25, 26, 27, 28, 29, 30]}

# print(d)
{'a': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
 'b': [11, 12, 13, 14, 15, 16, 17, 18, 19, 20],
 'c': [21, 22, 23, 24, 25, 26, 27, 28, 29, 30]}
 ```
