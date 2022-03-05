# WeAct-Blackpill-STM32F411CEU6-QMK
The things you need to compile QMK firmware to work on the "blackpill" development board with STM32F411CEU6 ARM based MCU.

The WeAct "blackpill" development board with STM32F411CEU6 has 32 I/O pins, 4 of which are used by the USB. However 1 of those 4 can be potentially used but you would have to install 22k pullup resistors as the user u/drashna commented in a reddit post. In my experience you can also use another of those 4 pins.

| PIN | Usability |
| --- | --------- |
| B12 | OK |
| B13 | OK |
| B14 | OK |
| B15 | OK |
| A8 | OK |
| A9 | could cause problems |
| A10 | could cause problems (resistor nedded) |
| A11 | NO |
| A12 | NO |
| A15 | OK |
| B3 | OK |
| B4 | OK |
| B5 | OK |
| B6 | OK |
| B7 | OK |
| B8 | OK |
| B9 | OK |
| B10 | OK |
| B2 | OK |
| B1 | OK |
| B0 | OK |
| A7 | OK |
| A6 | OK |
| A5 | OK |
| A4 | OK |
| A3 | OK |
| A2 | OK |
| A1 | OK |
| A0 | OK |
| C15 | OK |
| C14 | OK |
| C13 | OK |

In order to flash this controller is a bit different to the Pro Micro, but you dont need that serial programmer thing they sell, with this you will have to hold the KEY button on the controller for 2 seconds and then without lifting it press BOOTo and then nRST to power cycle the MCU and put it into USB DFU mode, at this point you should be able to see things going on in the QMK toolbox.
To flash it you will have to compile your firmware and the output will be a .bin file instead of a .hex one. Click flash and when completed push and lift the KEY button and then the nRST button (sometimes this is not neccesary and it will reset automatically after flashing is complete).
If all went right you should get a message from windows saying its configuring "keyboard name" or you will not get anything (funny that that is also a possibility). If you get a message saying Windows couldn't detect the device then you screwed up something, most likely you used one of those 4 forbidden pins as the compiler will not give you a warning for that.

That leaves us with a maximum number of keys of 196 using a 14x14 matrix but if you decide to use the other pins too you could do 225 keys using a 15x15 matrix.
It's a shame that this controller is not very popular as it has a lot of versatility, a lot more pins than the allmighty Pro Micro with ATmega32u4 being only slightly longer and using USB C. 
It also has a lot moer processing power to drive even more LEDs in more complicated patterns.