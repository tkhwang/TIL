# Django / Python

## Django : how to create app

```bash
# 생성 
$ django-admin startproject mysite .

# 모델
$ python manage.py makemigrations blog
$ python manage.py migrate blog

# 계정
$ python manage.py createsuperuser

...

# 실행
$ python manage.py runserver 0:8000
```