# Configuration reference

## Common kinematic settings

### Cartesian Kinematics with limits for X and Y axes

Behaves exactly the as cartesian kinematics, but allows to set a velocity and
acceleration limit for X and Y axis. This also makes command [`SET_KINEMATICS_LIMIT`](../G-Codes.md#⚠️-set_kinematics_limit) available to sets these limits at runtime.


```
[printer]
kinematics: limited_cartesian
max_x_velocity:
#   This sets the maximum velocity (in mm/s) of movement along the x
#   axis. This setting can be used to restrict the maximum speed of
#   the x stepper motor. The default is to use max_velocity for
#   max_x_velocity.
max_y_velocity:
#   This sets the maximum velocity (in mm/s) of movement along the y
#   axis. This setting can be used to restrict the maximum speed of
#   the y stepper motor. The default is to use max_velocity for
#   max_x_velocity.
max_z_velocity:
#   See cartesian above.
max_velocity:
#   In order to get maximum velocity gains on diagonals, this should be equal or
#   greater than the hypotenuse (sqrt(x*x + y*y)) of max_x_velocity and
#   max_y_velocity.
max_x_accel:
#   This sets the maximum acceleration (in mm/s^2) of movement along
#   the x axis. It limits the acceleration of the x stepper motor. The
#   default is to use max_accel for max_x_accel.
max_y_accel:
#   This sets the maximum acceleration (in mm/s^2) of movement along
#   the y axis. It limits the acceleration of the y stepper motor. The
#   default is to use max_accel for max_y_accel.
max_z_accel:
# See cartesian above.
max_accel:
# See cartesian above.
scale_xy_accel: False
#   When true, scales the XY limits by the current tool head acceleration.
#   The factor is: slicer accel / hypot(max_x_accel, max_y_accel).
#   See below.
```

If scale_xy_accel is `False`, the acceleration set by `max_accel`, M204 or
SET_VELOCITY_LIMIT, acts as a third limit. In that case, this module doesn't
apply limitations on moves having an acceleration lower than `max_x_accel`` and
`max_y_accel`. When scale_xy_accel is `True`, `max_x_accel` and `max_y_accel`
are scaled by the ratio of the dynamically set acceleration and the hypotenuse
of max_x_accel and `max_y_accel`, as reported from `SET_KINEMATICS_LIMIT`. This
implies that the actual acceleration will always depend on the direction. For
example, these settings:

```
[printer]
max_x_accel: 12000
max_y_accel: 9000
scale_xy_accel: true
```

`SET_KINEMATICS_LIMIT` will report a maximum acceleration of 15000 mm/s^2 on 37°
diagonals. If the slicer emit `M204 S3000` (3000 mm/s^2 accel). On these 37° and
143° diagonals, the toolhead will accelerate at 3000 mm/s^2. On the X axis, the
acceleration will be  12000 * 3000 / 15000 = 2400 mm/s^2, and 18000 mm/s^2 for
pure Y moves.

```
[printer]
kinematics: delta
max_z_velocity:
#   For delta printers this limits the maximum velocity (in mm/s) of
#   moves with z axis movement. This setting can be used to reduce the
#   maximum speed of up/down moves (which require a higher step rate
#   than other moves on a delta printer). The default is to use
#   max_velocity for max_z_velocity.
#max_z_accel:
#   This sets the maximum acceleration (in mm/s^2) of movement along
#   the z axis. Setting this may be useful if the printer can reach higher
#   acceleration on XY moves than Z moves (eg, when using input shaper).
#   The default is to use max_accel for max_z_accel.
#minimum_z_position: 0
#   The minimum Z position that the user may command the head to move
#   to. The default is 0.
delta_radius:
#   Radius (in mm) of the horizontal circle formed by the three linear
#   axis towers. This parameter may also be calculated as:
#    delta_radius = smooth_rod_offset - effector_offset - carriage_offset
#   This parameter must be provided.
#print_radius:
#   The radius (in mm) of valid toolhead XY coordinates. One may use
#   this setting to customize the range checking of toolhead moves. If
#   a large value is specified here then it may be possible to command
#   the toolhead into a collision with a tower. The default is to use
#   delta_radius for print_radius (which would normally prevent a
#   tower collision).

# The stepper_a section describes the stepper controlling the front
# left tower (at 210 degrees). This section also controls the homing
# parameters (homing_speed, homing_retract_dist) for all towers.
[stepper_a]
position_endstop:
#   Distance (in mm) between the nozzle and the bed when the nozzle is
#   in the center of the build area and the endstop triggers. This
#   parameter must be provided for stepper_a; for stepper_b and
#   stepper_c this parameter defaults to the value specified for
#   stepper_a.
arm_length:
#   Length (in mm) of the diagonal rod that connects this tower to the
#   print head. This parameter must be provided for stepper_a; for
#   stepper_b and stepper_c this parameter defaults to the value
#   specified for stepper_a.
#angle:
#   This option specifies the angle (in degrees) that the tower is
#   at. The default is 210 for stepper_a, 330 for stepper_b, and 90
#   for stepper_c.

# The stepper_b section describes the stepper controlling the front
# right tower (at 330 degrees).
[stepper_b]

# The stepper_c section describes the stepper controlling the rear
# tower (at 90 degrees).
[stepper_c]

# The delta_calibrate section enables a DELTA_CALIBRATE extended
# g-code command that can calibrate the tower endstop positions and
# angles.
[delta_calibrate]
radius:
#   Radius (in mm) of the area that may be probed. This is the radius
#   of nozzle coordinates to be probed; if using an automatic probe
#   with an XY offset then choose a radius small enough so that the
#   probe always fits over the bed. This parameter must be provided.
#speed: 50
#   The speed (in mm/s) of non-probing moves during the calibration.
#   The default is 50.
#horizontal_move_z: 5
#   The height (in mm) that the head should be commanded to move to
#   just prior to starting a probe operation. The default is 5.
```
