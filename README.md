# Info
This is a modified firmware for the retail Picade arduino board.
The original firmware was not able to work with recalbox because the board
acts like a keyboard and recalbox only supports joysticks in games.
It is preconfigured to work with recalbox.

## Features
* Board can act like a joystick or a keyboard
* One single configuration file (config.h)
* Modular code design
 
## Info
* Author:      DsChAeK

* Version:     v1.3

* License:     Copyright (c) 2015 by DsChAeK

        Permission to use, copy, modify, and/or distribute this software for any purpose
        with or without fee is hereby granted, provided that the above copyright notice
        and this permission notice appear in all copies.
                
        THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH
        REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND
        FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT,
        OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE,
        DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS
        ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

## Contribution
I used and modified code from some hard workers:

https://github.com/pimoroni/Picade-Sketch
-> basic sketch code

http://www.imaginaryindustries.com/blog/?p=80
-> code for usb game controller recognition    

http://www.zerker.ca/zzone/
-> code to let the board finally act like a SNES controller

## Compile/Flash (Windows)
* Download Arduino IDE **v1.6.5** for Windows (**Only this version works!**) from here: https://www.arduino.cc/en/Main/OldSoftwareReleases#previous3
* Download latest firmware sources as zip: https://github.com/DsChAeK/Picade/releases
* Extract it anywhere in a directory named "**Picade**"
* Replace the files in your arduino installation directory "*../Arduino/hardware/arduino/avr/cores/arduino*" with those from your extracted "*../Picade/USB_HID/*" subdirectory (backup recommended!)
* Plugin the USB Cable from Arduino Board into your PC, wait a few seconds to let it initialize.
* Open */Picade/Picade.ino* with Arduino IDE.
* Go into "*File -> Preferences*" and select both checkboxes at "*Show verbose output during:*"
* Select "*Tools -> Board -> Arduino Leonardo*"
* Select "*Programmer -> AVRISP mkll*"
* Select "*Tools -> Port -> COMx (Arduino Leonardo)*"
* Select "*Sketch -> Verify/Compile*", it should end without errors. (-> like "*Sketch uses 7,728 bytes of program...*")
* Select "*Sketch -> Upload*", it should also end without errors. (-> like "*avrdude done. Thank you*")
* If you want the original firmware back again use https://github.com/pimoroni/Picade-Sketch/releases

## Changes
v1.3, 13.08.2016
* Use front buttons for input
* Use volume buttons for input (optional)

v1.2, 04.09.2015
* Fixed volume zero bug

v1.1, 03.09.2015
* Changed joystick debounce to fix slow volume reaction

v1.0, 29.08.2015
* Modularized project files (keyboard/joystick/volume)
* Only two main functions in each module (Init/Check)
* Added configurable startup volume
* Added joystick support for Recalbox
* Added config.h for all user settings
