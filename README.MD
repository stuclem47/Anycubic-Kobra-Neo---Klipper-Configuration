# Klipper configuration file for the Anycubic Kobra Neo - based heavily on work of others.

## Based on printer.cfg by 1coderookie (https://github.com/1coderookie/Klipper4KobraGoNeo) - with some changes. I recommend you visit his GitHub page as it has very useful information and links.

I have set up to use the probe for Z home instead of the endstop (this is my preference on my other printers). Z safe homing now in bed centre.

## Included two extra files:

gcode.cfg - this includes the macros from the mainsail.cfg (CANCEL_PRINT, PAUSE, RESUME etc). These are not touched from stock, but should get you past any errors if using Fluidd or Mainsail. **NOTE you will have to change the path in [virtual_sdcard] section to suit your install - I am using two machine intances on my Pi with seperate directories for virtual SD.

macros.cfg - includes macros for START_PRINT, END_PRINT & PRIME_NOZZLE- (used in START_PRINT)

## Use the below in your slicer Start GCode:

M104 S0

M140 S0

M107 ;Dummy Temps to fool slicer not to add wait.

START_PRINT

(This will handle homing setting temps and draw nozzle priming line before print)

## Use this in slicer End GCode:

END_PRINT

(This will raise Z by 5mm, present bed and turn off heaters, part colling fan and steppers).
##
The code and commenting is not the cleanest. I have tested with multiple prints without issue, but as always: 
***USE AT YOUR OWN RISK ***
