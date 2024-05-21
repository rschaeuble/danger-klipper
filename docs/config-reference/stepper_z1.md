# Configuration reference

## Additional stepper motors and extruders

### [stepper_z1]

Multi-stepper axes. On a cartesian style printer, the stepper
controlling a given axis may have additional config blocks defining
steppers that should be stepped in concert with the primary stepper.
One may define any number of sections with a numeric suffix starting
at 1 (for example, "stepper_z1", "stepper_z2", etc.).

```
[stepper_z1]
#step_pin:
#dir_pin:
#enable_pin:
#microsteps:
#rotation_distance:
#   See the "stepper" section for the definition of the above parameters.
#endstop_pin:
#   If an endstop_pin is defined for the additional stepper then the
#   stepper will home until the endstop is triggered. Otherwise, the
#   stepper will home until the endstop on the primary stepper for the
#   axis is triggered.
```
