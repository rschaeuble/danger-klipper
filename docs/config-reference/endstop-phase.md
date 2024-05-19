# Configuration reference

## Customized homing

### [endstop_phase]

Stepper phase adjusted endstops. To use this feature, define a config
section with an "endstop_phase" prefix followed by the name of the
corresponding stepper config section (for example,
"[endstop_phase stepper_z]"). This feature can improve the accuracy of
endstop switches. Add a bare "[endstop_phase]" declaration to enable
the ENDSTOP_PHASE_CALIBRATE command.

See the [endstop phases guide](../Endstop_Phase.md) and
[command reference](../G-Codes.md#endstop_phase) for additional
information.

```
[endstop_phase stepper_z]
#endstop_accuracy:
#   Sets the expected accuracy (in mm) of the endstop. This represents
#   the maximum error distance the endstop may trigger (eg, if an
#   endstop may occasionally trigger 100um early or up to 100um late
#   then set this to 0.200 for 200um). The default is
#   4*rotation_distance/full_steps_per_rotation.
#trigger_phase:
#   This specifies the phase of the stepper motor driver to expect
#   when hitting the endstop. It is composed of two numbers separated
#   by a forward slash character - the phase and the total number of
#   phases (eg, "7/64"). Only set this value if one is sure the
#   stepper motor driver is reset every time the mcu is reset. If this
#   is not set, then the stepper phase will be detected on the first
#   home and that phase will be used on all subsequent homes.
#endstop_align_zero: False
#   If true then the position_endstop of the axis will effectively be
#   modified so that the zero position for the axis occurs at a full
#   step on the stepper motor. (If used on the Z axis and the print
#   layer height is a multiple of a full step distance then every
#   layer will occur on a full step.) The default is False.
```
