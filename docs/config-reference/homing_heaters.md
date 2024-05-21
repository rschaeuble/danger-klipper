# Configuration reference

## Custom heaters and sensors

### [homing_heaters]

Tool to disable heaters when homing or probing an axis.

```
[homing_heaters]
#steppers:
#   A comma separated list of steppers that should cause heaters to be
#   disabled. The default is to disable heaters for any homing/probing
#   move.
#   Typical example: stepper_z
#heaters:
#   A comma separated list of heaters to disable during homing/probing
#   moves. The default is to disable all heaters.
#   Typical example: extruder, heater_bed
```
