# Configuration reference

## Bed probing hardware

### [dockable_probe]

Certain probes are magnetically coupled to the toolhead and stowed
in a dock when not in use. One should define this section instead
of a probe section if the probe uses magnets to attach and a dock
for storage. See [Dockable Probe Guide](../Dockable_Probe.md)
for more detailed information regarding configuration and setup.

```
[dockable_probe]
dock_position: 0,0,0
#   The physical position of the probe dock relative to the origin of
#   the bed. The coordinates are specified as a comma separated X, Y, Z
#   list of values. Certain dock designs are independent of the Z axis.
#   If Z is specified the toolhead will move to the Z location before the X, Y
#   coordinates.
#   This parameter is required.
approach_position: 0,0,0
#   The X, Y, Z position where the toolhead needs to be prior to moving into the
#   dock so that the probe is aligned properly for attaching or detaching.
#   If Z is specified the toolhead will move to the Z location before the X, Y
#   coordinates.
#   This parameter is required.
detach_position: 0,0,0
#   Similar to the approach_position, the detach_position is the coordinates
#   where the toolhead is moved after the probe has been docked.
#   For magnetically coupled probes, this is typically perpendicular to
#   the approach_position in a direction that does not cause the tool to
#   collide with the printer.
#   If Z is specified the toolhead will move to the Z location before the X, Y
#   coordinates.
#   This parameter is required.
#extract_position: 0,0,0
#   Similar to the approach_position, the extract_position is the coordinates
#   where the toolhead is moved to extract the probe from the dock.
#   If Z is specified the toolhead will move to the Z location before the X, Y
#   coordinates.
#   The default value is approach_probe value.
#insert_position: 0,0,0
#   Similar to the extract_position, the insert_position is the coordinates
#   where the toolhead is moved before inserting the probe into the dock.
#   If Z is specified the toolhead will move to the Z location before the X, Y
#   coordinates.
#   The default value is extract_probe value.
#z_hop: 15.0
#   Distance (in mm) to lift the Z axis prior to attaching/detaching the probe.
#   If the Z axis is already homed and the current Z position is less
#   than `z_hop`, then this will lift the head to a height of `z_hop`. If
#   the Z axis is not already homed the head is lifted by `z_hop`.
#   The default is to not implement Z hop.
#restore_toolhead: True
#   While True, the position of the toolhead is restored to the position prior
#   to the attach/detach movements.
#   The default value is True.
#dock_retries:
#   The number of times to attempt to attach/dock the probe before raising
#   an error and aborting probing.
#   The default is 0.
#auto_attach_detach: False
#   Enable/Disable the automatic attaching/detaching of the probe during
#   actions that require the probe.
#   The default is True.
#attach_speed:
#detach_speed:
#travel_speed:
#   Optional speeds used during moves.
#   The default is to use `speed` of `probe` or 5.0.
#check_open_attach:
#   The probe status should be verified prior to homing. Setting this option
#   to true will check the probe "endstop" is "open" after attaching and
#   will abort probing if not, also checking for "triggered" after docking.
#   Conversively, setting this to false, the probe should read "triggered"
#   after attaching and "open" after docking. If not, probing will abort.
#probe_sense_pin:
#   This supplemental pin can be defined to determine an attached state
#   instead of check_open_attach.
#dock_sense_pin:
#   This supplemental pin can be defined to determine a docked state in
#   addition to probe_sense_pin or check_open_attach.
#x_offset:
#y_offset:
#z_offset:
#lift_speed:
#speed:
#samples:
#sample_retract_dist:
#samples_result:
#samples_tolerance:
#samples_tolerance_retries:
#activate_gcode:
#deactivate_gcode:
#   See the "probe" section for information on these parameters.
```
