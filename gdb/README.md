# gdb


## ARM binary cross-debugging 환경 구축

### Cross-compiler

```bash
$ sudo apt-get install libc6-armel-cross libc6-dev-armel-cross
$ sudo apt-get install binutils-arm-linux-gnueabi
$ sudo apt-get install libncurses5-dev

$ sudo apt-get install gcc-arm-linux-gnueabi
$ sudo apt-get install g++-arm-linux-gnueabi
```

### GDB multi-arch 설치

```bash
$ sudo apt-get install gdb-multiarch
```



## Python 2.7 호환 GDB 설치 

[Trouble compiling GDB with python 2.7 support for gdb-peda - Ask Ubuntu](http://askubuntu.com/questions/548435/trouble-compiling-gdb-with-python-2-7-support-for-gdb-peda)

#### 64 bit

```bash
$ sudo apt-get remove gdb
$ wget http://security.ubuntu.com/ubuntu/pool/main/g/gdb/gdb_7.4-2012.02-0ubuntu2_amd64.deb
$ sudo dpkg -i ./gdb_7.4-2012.02-0ubuntu2_amd64.deb
```

#### 32 bit

```bash
$ sudo apt-get remove gdb
$ wget http://security.ubuntu.com/ubuntu/pool/main/g/gdb/gdb_7.4-2012.02-0ubuntu2_amd64.deb
$ sudo dpkg -i ./gdb_7.4-2012.02-0ubuntu2_i386.deb
```