# Configuration reference

## Filament sensors

### [filament_switch_sensor]

Filament Switch Sensor. Support for filament insert and runout
detection using a switch sensor, such as an endstop switch.

See the [command reference](../G-Codes.md#filament_switch_sensor) for
more information.

```
[filament_switch_sensor my_sensor]
#pause_on_runout: True
#   When set to True, a PAUSE will execute immediately after a runout
#   is detected. Note that if pause_on_runout is False and the
#   runout_gcode is omitted then runout detection is disabled. Default
#   is True.
#runout_gcode:
#   A list of G-Code commands to execute after a filament runout is
#   detected. See docs/Command_Templates.md for G-Code format. If
#   pause_on_runout is set to True this G-Code will run after the
#   PAUSE is complete. The default is not to run any G-Code commands.
#immediate_runout_gcode:
#   A list of G-Code commands to execute immediately after a filament
#   runout is detected and runout_distance is greater than 0.
#   See docs/Command_Templates.md for G-Code format.
#insert_gcode:
#   A list of G-Code commands to execute after a filament insert is
#   detected. See docs/Command_Templates.md for G-Code format. The
#   default is not to run any G-Code commands, which disables insert
#   detection.
#runout_distance: 0.0
#   Defines how much filament can still be pulled after the
#   switch sensor triggered (e.g. you have a 60cm reverse bowden between your
#   extruder and your sensor, you would then set runout_distance to something
#   like 590 to leave a small safety margin and now the print will not
#   immediately pause when the sensor triggers but rather keep printing until
#   the filament is at the extruder). The default is 0 millimeters.
#event_delay: 3.0
#   The minimum amount of time in seconds to delay between events.
#   Events triggered during this time period will be silently
#   ignored. The default is 3 seconds.
#pause_delay: 0.5
#   The amount of time to delay, in seconds, between the pause command
#   dispatch and execution of the runout_gcode. It may be useful to
#   increase this delay if OctoPrint exhibits strange pause behavior.
#   Default is 0.5 seconds.
#switch_pin:
#   The pin on which the switch is connected. This parameter must be
#   provided.
#smart:
#   If set to true the sensor will use the virtual_sd_card module to determine
#   whether the printer is printing which is more reliable but will not work
#   when streaming a print over usb or similar.
#always_fire_events:
#   If set to true, runout events will always fire no matter whether the sensor
#   is enabled or disabled. Usefull for MMUs
#check_on_print_start:
#   If set to true, the sensor will be reevaluated when a print starts and if
#   no filament is detected the runout_gcode will be run no matter the defined
#   runout_distance(immediate_runout_gcode will not be run in this case)
```
