TTGO-Camera
=====================

![pic](image/1.jpg)

This fork of [martinberlin/esp32-camera-bme280](https://github.com/martinberlin/esp32-camera-bme280) is a trimmed down version of the camera interface with no display output or button interaction. (can be reenabled by removing the comments from line 10 to 13 in esp32-camera-bme280.ino).

## Installation instructions
- Install [Arduino IDE](https://www.arduino.cc/en/main/software)
- Go to preferences and add `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json` into Additional Board Manager URLs field.
- Open Boards Manager from Tools > Board menu and install esp32 platform.
- Select `ESP32 Wrover Module` from Tools > Board menu.
- Install necessary libraries from Tools > Manage libraries...
    - OneButton by Matthias Hertel
    - Adafruit BME280 Library by Adafruit
    - ESP8266 and ESP32 Oled Driver for SSD1306 display by Daniel Eichhorn
- In Adafruit_BME280_Library change <Adafruit_BME280.h> --> comment out `#include <Adafruit_Sensor.h>`. This library does not use this header file, so comment out and no problem.

## Special feature
This library has a V-mirror option which is achieved by rotating the image in html via css (transform: rotate). This option is enabled by default in this version.
I included the html sourcecode which is contained as gzip compressed byte array in camera_index.h.