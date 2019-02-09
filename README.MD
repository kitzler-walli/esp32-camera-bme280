TTGO-Camera with BME280 and Pir sensor
======================================

![TTGO-Camera image](schematic/TTGO-T-camera-bme280.jpg| width=100)

3D Printed Case
===============

[TTGO-Camera with buttons](https://www.thingiverse.com/thing:3413796) I designed this case for this model and I find it very nice to protect the board. Buttons need sanding and also a bit of lubricant to work nicely.

- Now Arduino officially supports the camera, you need to update the Arduino to the latest, see [arduino-esp32](https://github.com/espressif/arduino-esp32/releases) 
Note: This is my humble try to make a hackeable and modificable esp32 Camera using ARDUINO as a framework but with the official Espressif Camera Libraries. In another step to understand more how IOT dev. Famework integrates
  
- In order to support BME280, I will use [Adafruit_BME280_Library](https://github.com/adafruit/Adafruit_BME280_Library), but this library conflicts with <esp_camera.h> and enters [Adafruit_BME280_Library](https://github.com/adafruit/Adafruit_BME280_Library) In Adafruit_BME280_Library change <Adafruit_BME280.h> --> 29 lines comment #include <Adafruit_Sensor.h>, BME280 this library does not use this header file, so comment out and no problem

NOTE: Trying to find a bme280 library replacement that will not conflict.

- OLED requires [esp8266-oled-ssd1306](https://github.com/ThingPulse/esp8266-oled-ssd1306) library support

Maybe u8g2 will be a great replacement for this
  
- Buttons require [OneButton](https://github.com/mathertel/OneButton) library support

## TTGO CAM PINS
| Name  | Num    |
| ----- | ------ |
| Y9    | 39     |
| Y8    | 36     |
| Y7    | 23     |
| Y6    | 18     |
| Y5    | 15     |
| Y4    | 4      |
| Y3    | 14     |
| Y2    | 5      |
| VSNC  | 27     |
| HREF  | 25     |
| PCLK  | 19     |
| PWD   | 26     |
| XCLK  | 32     |
| SIOD  | 13     |
| SIOC  | 12     |
| RESET | No use |

Not about Camera could not make it work at the frequency in this repository, put it at half and worked (maybe chip speed config? Dont think so need to research more)

## Sensor & OLED
| Name | Num |
| ---- | --- |
| SDA  | 21  |
| SCL  | 22  | Working perfectly

## Other
| Name   | Num |
| ------ | --- |
| Button | 34  |
| PIR    | 33  | Pir works out the box

* BUTTON Click: Reverse camera ~~Currently the camera reverse color will not be normal, see [issues#9](https://github.com/espressif/esp32-camera/issues/9)~~

* BUTTON LongPress : Enter sleep Mode , Sleep current ~6.9mA
  
* RESET BUTTON: When the battery is powered, click to turn on the power

* PIR: Detecting human motion and will display the first screen



## Test Video
[YouTube](https://www.youtube.com/watch?v=CibcsmurTbo)
