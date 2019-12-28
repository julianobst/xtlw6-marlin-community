# XTLW6 Marlin Community Firmware based on Marlin 2.0.3
For further information about the amazing Marlin project please visit: http://www.marlinfw.org/

Special thanks to *Her Mann* from the *XTLW6 IDEX 3D printer* Facebook group who shared the sources with the community.

## Important update information
If you want to update your printers firmware to the community firmware based on Marlin 2.0.3, you must initialize your EEPROM after the update. This will delete all your settings and restore the defaults from the firmware.

It's highly recommend to read your current eeprom settings with G-Code ```M503``` http://marlinfw.org/docs/gcode/M503.html and copy & paste the output into a text file.

Therefore connect your printer with your PC via USB, start the Arduino IDE and open the serial Monitor ```Tools -> Serial Monitor``` or use the shortcut ```CTRL+SHIFT+M```.
At the top of the serial monitor, enter ```M503``` into the input text field and press enter or click ```Send```.
Copy the output from the text field below and paste it into a simple text file.
Now you have saved your eeprom settings and you can restore them via the printers display or depending G-Codes, which are mentioned before your settings value as Mxxx G-Code.

For more detailed information about backup your eeprom settings, take a look at this youtube video: https://www.youtube.com/watch?v=Jw-ZSkzd-uY

## Build and upload

### Install U8glib
Before you try to build the firmware with the Arduino IDE, please make sure you installed the U8glib librarie from this respository. The ```U8glib.zip``` was provioded and modified by XTLW3D. If you have installed a newer Version of U8glib, you maybe have to remove the newer library.

1. Open Arduino IDE
2. Sketch -> Include Library -> Add .ZIP Library
3. Choose U8glib.zip from the xtlw6-marlin-community folder and click open
4. You should restart the Marlin IDE before compiling the firmware

### Build
Start the Arduino IDE by opening the ```Marlin.ino``` file from the ```Marlin``` folder.

Use these hardware settings:
```
Board: 'Arduino/Genuino Mega or Mega 2560'
Processor: 'ATmega 2560 (Mega 2560)'
```

Connect the printer via USB to your PC, get the COM-Port of the printer and set the correct port inside the Arduino IDE. At least press ```Upload``` and wait until the build AND upload process is done.

## Features and changes
The community firmware for the XTLW6 has the follwowing features and changes:
- Bed corner leveling enabled
- Babystepping enabled
- Decimals in tool offset menu increased from 1 (xxx.y) to 2 (xxx.yy)
- Stock motion settings
- PLA preheat bed temperature reduced to 60°C
- Preconfigured for BLtouch<sup>1</sup>
- Mainboard set to MKS gen L
- Included the u8lib library made available by XTLW6

<sup>1</sup>Use the holes at the back of the toolhead, they are specially made for it. You just have to uncomment a few lines. Dont forget to enable Z safe homing!
