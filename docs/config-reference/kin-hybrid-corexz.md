# Configuration reference

## Common kinematic settings

### Hybrid-CoreXZ Kinematics

See [example-hybrid-corexz.cfg](../../config/example-hybrid-corexz.cfg)
for an example hybrid corexz kinematics config file.

This kinematic is also known as Markforged kinematic.

Only parameters specific to hybrid corexy printers are described here
see [[printer]](printer.md) for available parameters.

```
[printer]
kinematics: hybrid_corexz
max_z_velocity:
#   This sets the maximum velocity (in mm/s) of movement along the z
#   axis. The default is to use max_velocity for max_z_velocity.
max_z_accel:
#   This sets the maximum acceleration (in mm/s^2) of movement along
#   the z axis. The default is to use max_accel for max_z_accel.

# The stepper_x section is used to describe the X axis as well as the
# stepper controlling the X-Z movement.
[stepper_x]

# The stepper_y section is used to describe the stepper controlling
# the Y axis.
[stepper_y]

# The stepper_z section is used to describe the stepper controlling
# the Z axis.
[stepper_z]
```
