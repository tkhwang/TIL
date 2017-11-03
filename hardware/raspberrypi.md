# Raspberry Pi

## local problem 

[boot - Unable to reconfigure locale in raspberry pi - Raspberry Pi Stack Exchange](https://raspberrypi.stackexchange.com/questions/43550/unable-to-reconfigure-locale-in-raspberry-pi)

- Edit /etc/locale.gen and uncomment the line with en_US.UTF-8 e.g. `sudo nano /etc/locale.gen` uncomment line by deleting leading #
- Run `sudo locale-gen en_US.UTF-8`
- Run `sudo update-locale en_US.UTF-8`


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

