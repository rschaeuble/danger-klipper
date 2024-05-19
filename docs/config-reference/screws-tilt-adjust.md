# Configuration reference

## Bed level support

### [screws_tilt_adjust]

Tool to help adjust bed screws tilt using Z probe. One may define a
screws_tilt_adjust config section to enable a SCREWS_TILT_CALCULATE
g-code command.

See the
[leveling guide](../Manual_Level.md#adjusting-bed-leveling-screws-using-the-bed-probe)
and [command reference](../G-Codes.md#screws_tilt_adjust) for additional
information.

```
[screws_tilt_adjust]
#screw1:
#   The (X, Y) coordinate of the first bed leveling screw. This is a
#   position to command the nozzle to so that the probe is directly
#   above the bed screw (or as close as possible while still being
#   above the bed). This is the base screw used in calculations. This
#   parameter must be provided.
#screw1_name:
#   An arbitrary name for the given screw. This name is displayed when
#   the helper script runs. The default is to use a name based upon
#   the screw XY location.
#screw2:
#screw2_name:
#...
#   Additional bed leveling screws. At least two screws must be
#   defined.
#speed: 50
#   The speed (in mm/s) of non-probing moves during the calibration.
#   The default is 50.
#horizontal_move_z: 5
#   The height (in mm) that the head should be commanded to move to
#   just prior to starting a probe operation. The default is 5.
#screw_thread: CW-M3
#   The type of screw used for bed leveling, M3, M4, or M5, and the
#   rotation direction of the knob that is used to level the bed.
#   Accepted values: CW-M3, CCW-M3, CW-M4, CCW-M4, CW-M5, CCW-M5, CW-M8, CCW-M8.
#   Default value is CW-M3 which most printers use. A clockwise
#   rotation of the knob decreases the gap between the nozzle and the
#   bed. Conversely, a counter-clockwise rotation increases the gap.
```
