# Raspberry pi Sense Hat

[Getting Started with the Sense HAT | Raspberry Pi Learning Resources](https://www.raspberrypi.org/learning/getting-started-with-the-sense-hat/)

```python
from sense_hat import SenseHat
sense = SenseHat()
```

## Text

```python
sense.show_message("Hello my name is Tim Peake")
```

## Project

- [DyelKassaKoumba/sense_hat_weather_station: Raspberry pi weather station using sense hat and forecast.io](https://github.com/DyelKassaKoumba/sense_hat_weather_station)

### [jean-sh/pi-equalizer: An audio visualizer for the Raspberry Pi Sense Hat's LED display](https://github.com/jean-sh/pi-equalizer)

[ffmpeg on raspbian / Raspberry Pi : Hannes ihm sein Blog](http://hannes.enjoys.it/blog/2016/03/ffmpeg-on-raspbian-raspberry-pi/)

```bash
# build and install x264
git clone --depth 1 git://git.videolan.org/x264
cd x264
./configure --host=arm-unknown-linux-gnueabi --enable-static --disable-opencl
make -j 4
sudo make install
 
# build and make ffmpeg
git clone --depth=1 git://source.ffmpeg.org/ffmpeg.git
cd ffmpeg
./configure --arch=armel --target-os=linux --enable-gpl --enable-libx264 --enable-nonfree
make -j4
sudo make install
```


