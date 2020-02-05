# SMA-Q2_replacement_board_v2
nRF5840-based replacement board for the SMA-Q2 smartwatch. Uses the MDBT50Q-1MV2 (and similar) module. Based on the Adafruit Feather nRF52840. Has to be fabricated on 0,8mm FR4 material. Main changes are: no external RTC, all mosfets in SOT-323 package (at least in v2.2), optional barometer and power latching circuit, everything controlled by the nRF52840.

2 versions have been created: v2.2 without MS5611 barometer, but with a simple power latching circuit. v2.1.1 does not have a power latching circuit, but has a footprint for a MS5611 barometer. Both versions use both interrupts of the accelerometer.
