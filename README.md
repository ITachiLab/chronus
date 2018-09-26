# Introduction #

EZ430 is a programmable watch produced by Texas Instruments. It is created on top of the **CC430F6137** SoC which includes:

- MSP430 microcontroller,
- CC1101 transceiver,
- other peripherals.

EZ430 can be seen as a wearable development board for CC430 microcontrollers, and that was probably the main intention of TI engineers.

It comes preflashed with a vendor firmware which is mainly created as a feature demonstration rather than being useful. It is perfectly enough for daily use and we can have much fun with it, but some people wants more. That is why I decided to create my own firmware basing on the original.

# Changes #

The original firmware is not energy-efficient, and having in mind that the entire system runs on a small CR2032 battery, the effects are easy to predict. In a single evening I came up with a few simple methods that can save power and I think I can come up with more. Here I list upgrades and new features that will make the EZ430 better, and the development environment easier to understand.

(The list is still 'in progress', this is only a small portion of my ideas)

### Disable screen when not used ###

EZ430 is constantly displaying something and refreshes screen with a one second interval. That is not necessary as we can turn off the display and wait for a button event or specific hand movement.

### Change temperature source ###

EZ430 includes a BMA250 accelerometer, which can be used for a better temperature measurement.

### Remove unnecessary functions ###

Only useful functions should remain.

### Configurable functions on compile time ###

Some people wants to know the environment temperature, and some people doesn't. Why force the second group to have a temperature menu in their watches? Every non-critical function should be disableable at a compile time to decrease the compile time and the final image size. When some chip on the board is not used because, for example, one doesn't want to know the acceleration or temperature, the accelerometer can be fully switched off to save the energy.

### Settings menu ###

Some features like buzzer or backlight time should be configurable through some sort of settings menu.
