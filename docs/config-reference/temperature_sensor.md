# Configuration reference

## Custom heaters and sensors

### [temperature_sensor]

Generic temperature sensors. One can define any number of additional
temperature sensors that are reported via the M105 command.

```
[temperature_sensor my_sensor]
#sensor_type:
#sensor_pin:
#min_temp:
#max_temp:
#   See the "extruder" section for the definition of the above
#   parameters.
#gcode_id:
#   See the "heater_generic" section for the definition of this
#   parameter.
```
