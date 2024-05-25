# voron-v0-config
My custom Klipper config for the Voron V0.2r1 that I built from an LDO kit.

## Prerequisites
This set of configuration files assumes you have a working Klipper installation (Klipper + Moonraker) and that you're
using Mainsail as your web frontend for Klipper.

There are references to KAMP (https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging), but only for its line purge
functionality, so you'll either need to install KAMP or remove the `LINE_PURGE` reference in the `PRINT_START` macro.

## Usage
As my printer was built from an LDO Voron 0.2r1 kit, the configuration values for motors, sensors, etc are all specific
to the components that come with that kit. If you're using a V0.2 with different components you'll need to modify all
the relevant settings to match your specific printer.

Things you'll definitely need to change for your printer:
* In the `[mcu]` section of `skr_pico.cfg` edit the `serial` line to match the USB id of your SKR Pico board.
* In the `[mcu]` section of `picobilical.cfg` edit the `serial` line to match the USB id of your Picobilical board.
* In `homing.cfg` set the `driver_SGTHRS` values for `stepper_x` and `stepper_y` using the method described in the Voron guide for sensorless homing.

I highly recommend reading through all of the config files to make sure you understand what each one is doing, and to ensure
that your specific setup doesn't require additional changes. Just because these files work great for me and my specific printer,
that doesn't guarantee that they'll work for you.
