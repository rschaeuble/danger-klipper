# Configuration reference

## Additional stepper motors and extruders

### [manual_stepper]

Manual steppers (one may define any number of sections with a
"manual_stepper" prefix). These are steppers that are controlled by
the MANUAL_STEPPER g-code command. For example: "MANUAL_STEPPER
STEPPER=my_stepper MOVE=10 SPEED=5". See
[G-Codes](../G-Codes.md#manual_stepper) file for a description of the
MANUAL_STEPPER command. The steppers are not connected to the normal
printer kinematics.

```
[manual_stepper my_stepper]
#step_pin:
#dir_pin:
#enable_pin:
#microsteps:
#rotation_distance:
#   See the "stepper" section for a description of these parameters.
#velocity:
#   Set the default velocity (in mm/s) for the stepper. This value
#   will be used if a MANUAL_STEPPER command does not specify a SPEED
#   parameter. The default is 5mm/s.
#accel:
#   Set the default acceleration (in mm/s^2) for the stepper. An
#   acceleration of zero will result in no acceleration. This value
#   will be used if a MANUAL_STEPPER command does not specify an ACCEL
#   parameter. The default is zero.
#endstop_pin:
#   Endstop switch detection pin. If specified, then one may perform
#   "homing moves" by adding a STOP_ON_ENDSTOP parameter to
#   MANUAL_STEPPER movement commands.
```
