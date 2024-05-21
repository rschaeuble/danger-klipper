# Configuration reference

## Fans

### [fan_generic]

Manually controlled fan (one may define any number of sections with a
"fan_generic" prefix). The speed of a manually controlled fan is set
with the SET_FAN_SPEED [gcode command](../G-Codes.md#fan_generic).

```
[fan_generic extruder_partfan]
#pin:
#max_power:
#shutdown_speed:
#cycle_time:
#hardware_pwm:
#kick_start_time:
#min_power:
#tachometer_pin:
#tachometer_ppr:
#tachometer_poll_interval:
#enable_pin:
#   See the "fan" section for a description of the above parameters.
```
