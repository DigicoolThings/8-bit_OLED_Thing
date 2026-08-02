# 8-bit OLED Thing - Firmware

Here you’ll find the .s19 firmware files.

Firmware is programmed via the SWIM interface, using a ST-LINK V2 USB Programmer (or alternative), via ST Visual Programmer.

## Changelog

**v1.1** - Adds Hold (HLD) and Latch (LCH) input pin controls.

Implements functionality for both of the 2 remaining port pins (PD2 & PD3), to enable both a falling-edge interrupt driven input sampling “Latch” (PD3), and also a level driven “Hold” (PD2 - pulled low to temporarily hold the current sample).
In summary, the falling-edge triggered Latch pin (PD3), is a permanent sample & hold (until a reset is applied to the reset pin).  But, it is repeatable.  i.e. Each PD3 falling edge interrupt, latches the current input.
In this way, you could (for example), feed-in a low frequency square wave, to control the duration of sample updates.  e.g. 2Hz would drive 2 updates per second etc.  (for a readable Hex display on a dynamic bus).
In addition, the level based “Hold" pin (PD2) enables dynamically switching between a latched sampled value, and the normal (default) free running mode.
 
**v1.0** - Original release version (as demonstrated in the original YouTube video).