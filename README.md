# co2_esphome
![WhatsApp Image 2021-07-31 at 3 30 18 PM](https://user-images.githubusercontent.com/78609906/127737056-21c92be9-78cf-49c9-88bf-fd5cdb5c010e.jpeg)
A co2 Monitor based on ESP32 with SCD30 sensor

**Board selection:**
using lilygo TTGO T-DISPLAY ESP32 board.
The reason for this board was because it comes with a 140x240 pixel display and it has i2c pins and also support for LI-PO

**CO2 sensor selection:**
Sensirion SCD30 is much more accurate and energy efficent compared to the much cheaper MH-z19 sensor.
Plus this has i2c bus.
SCD has long term useful life of 15years and is self calibrating. 

**ESPhome**
I have used to ESPhome to make the firmware , as it intergrates with Home Assistant natively.
ESPhome already has full support for, i2c bus, SCD30, TTgo's display ST7789V TFT LCD display.

**A Casing for The project**
I have used a design by user @pjmi on thingsverse ( https://www.thingiverse.com/thing:4501444 )
Its a very tight fit design but doesnt have vents in the bottom half. You will need to edit file to add vents and might even need to increase height if a larger Li-po is required. 

**Instructions:**

Its Assumed at this point, that HOME Assistant is already installed on being used and ESPhome add-on has been installed too.
The SCD30 Needs to be conncted to the TTGO T-display board as follows.

VDD of the SCD30 to the 3.3V of the ESP32

GND of the SCD30 to the GND of the ESP32

SCL of the SCD30 to the IO22 of the ESP32

SDA of the SCD30 to the IO21 of the ESP32

![connections](https://user-images.githubusercontent.com/78609906/127737422-c5ef1653-ad2b-4a5f-9b49-80c5494954c4.jpeg)

All that needs to be done is, connect the device to ESPhome.
If on windows, then just connect it via USB, windows will auto install drivers. Once successfull, ESPhome is able to detect it via USB serial.
This is only required for devices being flashed by ESPhome for the first time, once succesful the device can be flashed wireless OTA.

For Mac users, you will need to install drivers for the USB serial chipset (TTGO comes in two differnt models with either ch340 vs cp2102).

You will need to upload any image or font files used in the esphome folder on the HomeAssistant (can use file editor add-on for this)
Just edit the Wifi and passowrds parameters and install the YAML code to device using ESPHOME interface.
And the device should be visible and can be added in via the integrations page in home assistant.
