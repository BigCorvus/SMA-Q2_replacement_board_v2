# SMA-Q2_replacement_board_v2
![2.1.1](https://github.com/BigCorvus/SMA-Q2_replacement_board_v2/blob/master/SMA-Q2nrf52840V2.1.1.png)
![2.1.1](https://github.com/BigCorvus/SMA-Q2_replacement_board_v2/blob/master/SMA-Q2nrf52840V2.png)
nRF5840-based replacement board for the SMA-Q2 smartwatch. Uses the MDBT50Q-1MV2 (and similar) module. Based on the Adafruit Feather nRF52840. Has to be fabricated on 0,8mm FR4 material. Main changes are: no external RTC, all mosfets in SOT-323 package (at least in v2.2), optional barometer and power latching circuit, everything controlled by the nRF52840.

2 versions have been created: v2.2 without MS5611 barometer, but with a simple power latching circuit. v2.1.1 does not have a power latching circuit, but has a footprint for a MS5611 barometer. Both versions use both interrupts of the accelerometer.  
During testing and everyday use RF performance turned out to be poor. The reason is the ceramic antenna which is shielded by the close proximity of the lipo battery. This problem was quite easy to solve in retrospective. I just desoldered the chip antenna with 2 soldering irons and connected a simple 30AWG wire which I shortened until reception started to get worse. Ended up with about 20mm of wire bent around the top left corner of the device where least interfering metal is located. Quite surprising that the antenna is quite a bit shorter than one would expect for 2.4GHz (lambda/4 = ~31mm).   
This got me motivated to create a 3rd version of the board using the bare chip instead of an integrated module. It makes use of the inbuilt antenna which is also surprisingly short (about 20mm). The feedline was designed to be about 50 ohm (although it probably doesn't have to be, in the original version it's about 65 ohm at 0,7mm trace width and 0.8mm FR4 substrate). This version 2.3 has the barometer, which has proven to be very accurate and useful, the power latching circuit and even a fuel gauge which can measure the supply current (albeit in 1mA steps).  

![2.3](https://github.com/BigCorvus/SMA-Q2_replacement_board_v2/blob/master/SMA-Q2-nrf52840v2.3.png)  

Note: 2.3 has not been tested yet. The Feather bootloader should still work, the pinout for the button, I2C, SPI, QSPI and UART is still the same. 
