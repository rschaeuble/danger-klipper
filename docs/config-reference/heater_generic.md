# Configuration reference

## Custom heaters and sensors

### [heater_generic]

Generic heaters (one may define any number of sections with a
"heater_generic" prefix). These heaters behave similarly to standard
heaters (extruders, heated beds). Use the SET_HEATER_TEMPERATURE
command (see [G-Codes](../G-Codes.md#heaters) for details) to set the
target temperature.

```
[heater_generic my_generic_heater]
#gcode_id:
#   The id to use when reporting the temperature in the M105 command.
#   This parameter must be provided.
#heater_pin:
#max_power:
#sensor_type:
#sensor_pin:
#smooth_time:
#control:
#pid_Kp:
#pid_Ki:
#pid_Kd:
#pwm_cycle_time:
#min_temp:
#max_temp:
#   See the "extruder" section for the definition of the above
#   parameters.
```
