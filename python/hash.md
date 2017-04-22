# Hash

[Hashing Strings with Python | Python Central](http://pythoncentral.io/hashing-strings-with-python/)

## MD5

```python
import hashlib
hash_object = hashlib.md5(b'Hello World')
print(hash_object.hexdigest())
```

## SHA1

```python
import hashlib
hash_object = hashlib.sha1(b'Hello World')
hex_dig = hash_object.hexdigest()
print(hex_dig)
```

## SHA256

```python
import hashlib
hash_object = hashlib.sha256(b'Hello World')
hex_dig = hash_object.hexdigest()
print(hex_dig)
```
