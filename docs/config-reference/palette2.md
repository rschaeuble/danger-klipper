# Configuration reference

## Other Custom Modules

### [palette2]

Palette 2 multimaterial support - provides a tighter integration
supporting Palette 2 devices in connected mode.

This modules also requires `[virtual_sdcard]` and `[pause_resume]`
for full functionality.

If you use this module, do not use the Palette 2 plugin for
Octoprint as they will conflict, and 1 will fail to initialize
properly likely aborting your print.

If you use Octoprint and stream gcode over the serial port instead of
printing from virtual*sd, then remo **M1** and **M0** from \_Pausing commands*
in _Settings > Serial Connection > Firmware & protocol_ will prevent
the need to start print on the Palette 2 and unpausing in Octoprint
for your print to begin.

```
[palette2]
serial:
#   The serial port to connect to the Palette 2.
#baud: 115200
#   The baud rate to use. The default is 115200.
#feedrate_splice: 0.8
#   The feedrate to use when splicing, default is 0.8
#feedrate_normal: 1.0
#   The feedrate to use after splicing, default is 1.0
#auto_load_speed: 2
#   Extrude feedrate when autoloading, default is 2 (mm/s)
#auto_cancel_variation: 0.1
#   Auto cancel print when ping variation is above this threshold
```
