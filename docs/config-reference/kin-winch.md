# Configuration reference

## Common kinematic settings

### Cable winch Kinematics

See the [example-winch.cfg](../../config/example-winch.cfg) for an
example cable winch kinematics config file.

Only parameters specific to cable winch printers are described here -
see [[printer]](printer.md) for available parameters.

CABLE WINCH SUPPORT IS EXPERIMENTAL. Homing is not implemented on
cable winch kinematics. In order to home the printer, manually send
movement commands until the toolhead is at 0, 0, 0 and then issue a
`G28` command.

```
[printer]
kinematics: winch

# The stepper_a section describes the stepper connected to the first
# cable winch. A minimum of 3 and a maximum of 26 cable winches may be
# defined (stepper_a to stepper_z) though it is common to define 4.
[stepper_a]
rotation_distance:
#   The rotation_distance is the nominal distance (in mm) the toolhead
#   moves towards the cable winch for each full rotation of the
#   stepper motor. This parameter must be provided.
anchor_x:
anchor_y:
anchor_z:
#   The X, Y, and Z position of the cable winch in cartesian space.
#   These parameters must be provided.
```
