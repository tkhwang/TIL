# adb

## adb installation by mac brew

[android - Installing ADB on MAC OS X - Stack Overflow](https://stackoverflow.com/questions/31374085/installing-adb-on-mac-os-x)

```bash
brew cask install android-platform-tools
```

## `adb backup`

[Android Backup Extractor download | SourceForge.net](https://sourceforge.net/projects/adbextractor/)

```bash
$ java -jar abe.jar
Android backup extractor v20160710
Cipher.getMaxAllowedKeyLength("AES") = 2147483647
Strong AES encryption allowed, MaxKeyLenght >= 256
Usage:
        info:   abe [-debug] [-useenv=yourenv] info <backup.ab> [password]
        unpack: abe [-debug] [-useenv=yourenv] unpack <backup.ab> <backup.tar> [password]
        pack:   abe [-debug] [-useenv=yourenv] pack <backup.tar> <backup.ab> [password]
        pack 4.4.3+:    abe [-debug] [-useenv=yourenv] pack-kk <backup.tar> <backup.ab> [password]
        If -useenv is used, yourenv is tried when password is not given
        If -debug is used, information and passwords may be shown
        If the filename is `-`, then data is read from standard input or written to standard output
```



## no permission 

[android - set up device for development (?????? no permissions) - Stack Overflow](http://stackoverflow.com/questions/9210152/set-up-device-for-development-no-permissions)

- `sudo vim /etc/udev/rules.d/51-android.rules`

```
SUBSYSTEM=="usb", ATTRS{idVendor}=="0bb4", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0e79", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0502", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0b05", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="413c", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0489", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="091e", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="18d1", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0bb4", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="12d1", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="24e3", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="2116", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0482", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="17ef", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1004", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="22b8", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0409", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="2080", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0955", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="2257", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="10a9", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1d4d", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0471", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="04da", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="05c6", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1f53", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="04e8", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="04dd", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0fce", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0930", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="19d2", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1bbb", MODE="0666"
```

```bash
sudo cp /tmp/android.rules /etc/udev/rules.d/51-android.rules
sudo chmod 644   /etc/udev/rules.d/51-android.rules
sudo chown root. /etc/udev/rules.d/51-android.rules
sudo service udev restart
sudo killall adb
```
