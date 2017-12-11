# Natural Language 

## KoNLpy 

[설치하기 — KoNLPy 0.4.3 documentation](http://konlpy.org/ko/v0.4.3/install/)

```bash
$ pip3 install konlpy    # Python 3.x

```

하지만 Error 발행.

```python
$ python get_korean_keyword.py
Traceback (most recent call last):
  File "get_korean_keyword.py", line 3, in <module>
    from konlpy.tag import Kkma
  File "/Users/tkhwang/.virtualenvs/web-scrap/lib/python3.6/site-packages/konlpy/__init__.py", line 15, in <module>
    from . import tag
  File "/Users/tkhwang/.virtualenvs/web-scrap/lib/python3.6/site-packages/konlpy/tag/__init__.py", line 4, in <module>
    from ._hannanum import Hannanum
  File "/Users/tkhwang/.virtualenvs/web-scrap/lib/python3.6/site-packages/konlpy/tag/_hannanum.py", line 7, in <module>
    import jpype
ModuleNotFoundError: No module named 'jpype'
```

댓글보니깐 해결책 명시.

```bash
$ pip install JPype1-py3
```

근데 서버에서 설치해보니 필요로 하는 것이 많네요.

```bash
$ sudo apt install default-jdk
$ sudo apt install gcc
$ sudo apt install g++
$ sudo apt install python3-dev


$ sudo apt-get install libfontenc1 libxfont1 xfonts-encodings xfonts-utils xfonts-base xfonts-75dpi
$ sudo apt install language-pack-ko
$ 
```
