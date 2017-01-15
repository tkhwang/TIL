# any

## Password 규칙 check

- `any()`
- `i.XXX() for i in psw`

```python
while True:
    psw = input("Enter new password: ")
    if any(i.isdigit() for i in psw) and any(i.isupper() for i in psw) and len(psw) >= 5:
        print("Password is fine")
        break
    else:
        print("Passowrd is not fine")
```