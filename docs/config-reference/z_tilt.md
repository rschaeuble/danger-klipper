# Configuration reference

## Bed level support

### [z_tilt]

Multiple Z stepper tilt adjustment. This feature enables independent
adjustment of multiple z steppers (see the "stepper_z1" section) to
adjust for tilt. If this section is present then a Z_TILT_ADJUST
extended [G-Code command](../G-Codes.md#z_tilt) becomes available.

```
[z_tilt]
#z_positions:
#   A list of X, Y coordinates (one per line; subsequent lines
#   indented) describing the location of each bed "pivot point". The
#   "pivot point" is the point where the bed attaches to the given Z
#   stepper. It is described using nozzle coordinates (the X, Y position
#   of the nozzle if it could move directly above the point). The
#   first entry corresponds to stepper_z, the second to stepper_z1,
#   the third to stepper_z2, etc. This parameter must be provided.
#points:
#   A list of X, Y coordinates (one per line; subsequent lines
#   indented) that should be probed during a Z_TILT_ADJUST command.
#   Specify coordinates of the nozzle and be sure the probe is above
#   the bed at the given nozzle coordinates. This parameter must be
#   provided.
#speed: 50
#   The speed (in mm/s) of non-probing moves during the calibration.
#   The default is 50.
#horizontal_move_z: 5
#   The height (in mm) that the head should be commanded to move to
#   just prior to starting a probe operation. The default is 5.
#retries: 0
#   Number of times to retry if the probed points aren't within
#   tolerance.
#retry_tolerance: 0
#   If retries are enabled then retry if largest and smallest probed
#   points differ more than retry_tolerance. Note the smallest unit of
#   change here would be a single step. However if you are probing
#   more points than steppers then you will likely have a fixed
#   minimum value for the range of probed points which you can learn
#   by observing command output.
#increasing_threshold: 0.0000001
#   Sets the threshold that probe points can increase before z_tilt aborts.
#   To disable the validation, set this parameter to a high value.
```

```
[z_tilt_ng]
#z_positions:
# See [z_tilt]. This parameter must be provided,
#   unless the parameter "extra_points" is provided. In that case only
#   the command Z_TILT_AUTODETECT can be run to automatically determine
#   the z_positions. See 'extra_points' below.
#z_offsets:
#   A list of Z offsets for each z_position. The z_offset is added to each
#   probed value during Z_TILT_ADJUST to offset for unevenness of the bed.
#   This values can also be automatically detected by running
#   Z_TILT_CALIBRATE. See "extra_points" below.
#points:
# See [z_tilt]
#speed: 50
# See [z_tilt]
#horizontal_move_z: 5
# See [z_tilt]
#retries: 0
# See [z_tilt]
#retry_tolerance: 0
# See [z_tilt]
#increasing_threshold: 0.0000001
# See [z_tilt]
#extra_points:
#   A list in the same format as "points" above. This list contains
#   additional points to be probed during the two calibration commands
#   Z_TILT_CALIBRATE and Z_TILT_AUTODETECT. If the bed is not perfectly
#   level, it is possible to specify more probing points with "points".
#   In that Z_TILT_ADJUST will determine the best fit via a least squares
#   algorithm. As this comes with additional overhead on each Z_TILT_ADJUST
#   run, it is instead possible to move the additional probing points here,
#   and use Z_TILT_CALIBRATE to find z_offsets to use for the probing points
#   used in Z_TILT_ADJUST.
#   The extra points are also used during T_ZILT_AUTODETECT. This command
#   can determine the z_positions automatically by during several probings
#   with intentionally tilted bed. It is currently only implemented for 3
#   z steppers.
#   Note that for both commands to work numpy has to be installed.
#averaging_len: 3
#   Z_TILT_CALIBRATE and Z_TILT_AUTODETECT both run repeatedly until the
#   result can no longer be improved. To determine this, the probed values
#   are averaged. The number of runs to average over is configured with this
#   parameter.
#autodetect_delta: 1.0
#   The amount by which Z_TILT_AUTODETECT intentionally tilts the bed. Higher
#   values yield better results, but can also lead to situations where the
#   bed is tilted in a way that the nozzle touched the bed before the probe.
#   The default is conservative.
```
