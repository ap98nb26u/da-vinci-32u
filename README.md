# da-vinci-32u

Add support for [Strawberry Linux's Arduino Leonardo compatible board "Da Vinci 32U"](https://strawberry-linux.com/catalog/items?code=25005) to Arduino IDE 1.6.9

# I've checked
* Windows 7 Pro 64 bit with Arduino.exe ~ 1.6.9
* OS X El Capitan with Arduino.app ~ 1.6.9

NB: Arduino IDE 1.6.10 seems to have some issues.  Application crashes on Windows, OS X panics when the board's serial device is probed.

# How to use

* copy extracted `da-vinci-32u` directory to `hardware` directory, which contains `arduino` and `tools` directories.

* OS X: You may want to do `codesign -s <Cert Name> -f /Applications/Arduino.app` to stop annoying firewall message after modifying downloaded Arduino.app.

* Windows: Connect "Da Vinci 32U" board to PC, then install its driver from `da-vinci-32u\driver\da-vinci-32u.inf`.  It has some timing issue so you should try several times with pressing the board's reset button.  And the driver has no signature. (I must use `bcdedit /set testsigning on` on my PC.)

* restart Arduino application.

* select "Da Vinci 32U" board from "Tool" -> "board" menu.

* select serial port.  com? on Windows, /dev/usbmodem* on OS X.

* build and write e.g. blink sketch.  Auto resetting is supported.
