# Crack

## John the ripper

### `fopen: $JOHN/john.ini`: No such file or directory

```bash
$ john --show zipfile_500.zip.hash
fopen: $JOHN/john.ini: No such file or directory
```

[John the Ripper](https://www.win.tue.nl/~aeb/linux/john/john.html)

then either (e.g., if you plan a dictionary attack)

```bash
% touch john.ini
```

or change directory to the run directory that has the john executable and various other useful files.

```
(The program john wants to read john.conf, and when that is not found it tries the alternative name john.ini, and when that is not found it complains and exits. Each invocation of john has a ‘home’, usually the directory where its executable was found. It will write its output files john.log, john.rec and john.pot there. One might think that $JOHN refers to an environment variable one can set to tell john where its home is, but it is only an internal name; when run as somepath/john the program john first tries open("somepath/john.conf", O_RDONLY) and, if that fails, open("$JOHN/john.conf", O_RDONLY), where $JOHN/ is not expanded but is just this 6-byte string. When run as john, the current directory will be john's home. Compile with -DJOHN_SYSTEMWIDE=1 to make it use ~/.john. A useful side effect of systemwide installation is that tilde expansion works in options like -w:~/dir/words.)
```

