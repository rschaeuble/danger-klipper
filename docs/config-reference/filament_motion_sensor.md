# Configuration reference

## Filament sensors

### [filament_motion_sensor]

Filament Motion Sensor. Support for filament insert and runout
detection using an encoder that toggles the output pin during filament
movement through the sensor.

See the [command reference](../G-Codes.md#filament_switch_sensor) for
more information.

```
[filament_motion_sensor my_sensor]
detection_length: 7.0
#   The minimum length of filament pulled through the sensor to trigger
#   a state change on the switch_pin
#   Default is 7 mm.
extruder:
#   The name of the extruder section this sensor is associated with.
#   This parameter must be provided.
switch_pin:
#pause_on_runout:
#runout_gcode:
#insert_gcode:
#event_delay:
#pause_delay:
#smart:
#always_fire_events:
#   See the "filament_switch_sensor" section for a description of the
#   above parameters.
```
