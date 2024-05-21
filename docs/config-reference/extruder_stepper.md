# Configuration reference

## Additional stepper motors and extruders

### [extruder_stepper]

Support for additional steppers synchronized to the movement of an
extruder (one may define any number of sections with an
"extruder_stepper" prefix).

See the [command reference](../G-Codes.md#extruder) for more information.

```
[extruder_stepper my_extra_stepper]
extruder:
#   The extruder this stepper is synchronized to. If this is set to an
#   empty string then the stepper will not be synchronized to an
#   extruder. This parameter must be provided.
#step_pin:
#dir_pin:
#enable_pin:
#microsteps:
#rotation_distance:
#   See the "stepper" section for the definition of the above
#   parameters.
```
