# Configuration reference

## Common kinematic settings

### CoreXY Kinematics with limits for X and Y axes

Behaves exactly the as CoreXY kinematics, but allows to set a acceleration limit
for X and Y axis.

There is no velocity limits for X and Y, since on a CoreXY the pull-out velocity
are identical on both axes.

```
[printer]
kinematics: limited_corexy
max_z_velocity:
#   See CoreXY above.
max_x_accel:
#   This sets the maximum acceleration (in mm/s^2) of movement along
#   the x axis. It limits the acceleration of the x stepper motor. The
#   default is to use max_accel for max_x_accel.
max_y_accel:
#   This sets the maximum acceleration (in mm/s^2) of movement along
#   the y axis. It limits the acceleration of the y stepper motor. The
#   default is to use max_accel for max_y_accel.
max_z_accel:
# See CoreXY above.
max_accel:
# See CoreXY above..
scale_xy_accel:
#   When True, scales the XY limits by the current tool head acceleration.
#   The factor is: slicer accel / max(max_x_accel, max_y_accel).
```
