# Raspberry Pi

## [flashrom](https://www.flashrom.org/Flashrom)

```bash
$ sudo apt-get install pciutils
$ sudo apt-get install libftdi-dev
$ sudo apt-get install libusb-dev
$ sudo apt-get install libpci-dev
$ sudo apt-get install libusb-1.0
$ git clone https://github.com/stefanct/flashrom.git
$ cd flashrom
$ make
$ sudo make install
```


## WIFI configuration

`$ sudo vi /etc/wpa_supplicant/wpa_supplicant.conf`

```
network={
    ssid="The_ESSID_from_earlier"
    psk="Your_wifi_password"
}
```

