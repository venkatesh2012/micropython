# ESP32 Micropython for TTGO-2020 V1 Watch

This is a fork of http://github.com/micropython from V1.14 branch

# ESP32 T-Watch

![image](https://user-images.githubusercontent.com/22662559/111427886-0f7fa600-86f7-11eb-91d7-db0c1f60d92b.png)



The board consists of:
a. BMA423 - 3 Axis accelerometer
b. MAX98357A - PCM Audio via I2C
c. AXP202 - A power management Unit
d. PCF8563 - Real Time Clock
e. ST7789 - TFT Display via SPI
f. FT6206 - Focal Tech chip for touch via I2C

## Build Instructions

1. clone this repository 
2. Initialize submodules git submodule update --Initialize
3. clone ESP-IDF repository git clone https://github.com/espressif/esp-idf.git
4. export ESPIDF=<PATH>/esp-idf
5. cd $ESPIDF && ./install.sh
6. source ./export.sh
7. Make sure xtensa-esp32-elf-gcc is added to PATH and works
8. compile mpy-cross.  cd uPython && make -C mpy-cross
9. Build the uPython firmware make -C ports/esp32
10. Deploy the firmware make -C ports/esp32 deploy

## Test deployment
1. use picocom to connect to device 
   picocom /dev/ttyUSB0 -b115200
2. Execute sample program to test the hardware PINs
