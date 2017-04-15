# requests | python

[Requests: HTTP for Humans — Requests 2.13.0 documentation](http://docs.python-requests.org/en/master/)

## GET

```python
payload = {'key1': 'value1', 'key2': 'value2'}
r = requests.get('http://httpbin.org/get', params=payload)
```

## POST

```python
import json

url = 'https://api.github.com/some/endpoint'
payload = {'some': 'data'}

r = requests.post(url, data=json.dumps(payload))
```