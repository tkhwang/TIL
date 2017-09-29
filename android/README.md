# Android

## `ab2tar`

macOS 에서 `openssl zlib` 없어서 ab backup 파일을 extract 하기 어려움.

[random-scripts/ab2tar at master · poliva/random-scripts](https://github.com/poliva/random-scripts/blob/master/android/ab2tar)

```bash
#!/bin/bash
# convert android 'adb backup' unencrypted archives to tar format

if [ ! -e "$1" ]; then
    echo "Usage: $0 <backupfile.ab>"
    exit 1
fi

echo "$1" |grep ".ab$" 2>&1 >/dev/null
if [ "$?" != "0" ]; then
    echo "ERROR: $1 must be a .ab file"
    exit 1
fi

DST=`echo "$1" |sed -e "s/.ab$//g"`

echo "Converting: $1 -> ${DST}.tar"
#dd if="$1" bs=1 skip=24|openssl zlib -d > "${DST}.tar"
dd if="$1" bs=1 skip=24 | python -c "import zlib,sys;sys.stdout.write(zlib.decompress(sys.stdin.read()))" > "${DST}.tar"
```