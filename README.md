# Wanhao-i3-Firmware
The master copy of the firmware for our Wanhao 3D printer running Repetier Firmware.

I followed the procedure laid down here on [Google Groups](https://groups.google.com/forum/#!topic/wanhao-printer-3d/pjWof2uIkNE%5B26-50%5D)

You need to use:
Arduino IDE 1.0.5-r2

Install the attached sanguino folder unzipped into the hardware folder inside arduino ide
Choose board type of "Melzi 1284p 16mhz" at the bottom of the boards list

Board must be powered before flashing.

#Repetier Implemented Codes - May be old
Repetier G Codes
[https://github.com/repetier/Repetier-Firmware/wiki/G-codes](https://github.com/repetier/Repetier-Firmware/wiki/G-codes)

* G0 -> G1
* G1 - Coordinated Movement X Y Z E
* G4 - Dwell S or P
* G20 - Units for G0/G1 are inches.
* G21 - Units for G0/G1 are mm.
* G28 - Home all axis or named axis.
* G90 - Use absolute coordinates
* G91 - Use relative coordinates
* G92 - Set current position to cordinates given

Repetier M Codes

* M104 S[targetTemperature] - Set extruder target temp
* M105 - Read current temp
* M106 S[Speed 0..255] - Fan on
* M107 - Fan off
* M109 - Wait for extruder current temp to reach target temp.
* M112 - Emergency stop.
* M114 - Display current position

Custom M Codes

* M80 - Turn on Power Supply
* M20 - List SD card
* M21 - Init SD card
* M22 - Release SD card
* M23 - Select SD file (M23 filename.g)
* M24 - Start/resume SD print
* M25 - Pause SD print
* M26 - Set SD position in bytes (M26 S12345)
* M27 - Report SD print status
* M28 - Start SD write (M28 filename.g)
* M29 - Stop SD write
* M80 - Turn on power supply
* M81 - Turn off power supply
* M82 - Set E codes absolute (default)
* M83 - Set E codes relative while in Absolute Coordinates (G90) mode
* M84 - Disable steppers until next move, or use S to specify an inactivity timeout, after which the steppers will be disabled. S0 to disable the timeout.
* M85 - Set inactivity shutdown timer with parameter S. To disable set zero (default)
* M92 - Set axis_steps_per_unit - same syntax as G92
* M115 - Capabilities string
* M140 S[TargetTemperature] - Set bed target temp
* M190 - Wait for bed current temp to reach target temp.
* M201 - Set max acceleration in units/s^2 for print moves (M201 X1000 Y1000)
* M202 - Set max acceleration in units/s^2 for travel moves (M202 X1000 Y1000)
* M203 - Set temperture monitor to Sx
* M204 X[Kp] Y[Ki] Z[Kd] - Set PID parameter. Values are 100*real value!
* M205 - Output EEPROM settings
* M206 - Set EEPROM value
* M231 S[OPS_MODE] X[Min_Distance] Y[Retract] Z[Backslash] F[ReatrctMove] - Set OPS parameter
* M232 - Read and reset max. advance values
