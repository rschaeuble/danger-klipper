# Configuration reference

## Additional stepper motors and extruders

### [dual_carriage]

Support for cartesian and hybrid_corexy/z printers with dual carriages
on a single axis. The carriage mode can be set via the
SET_DUAL_CARRIAGE extended g-code command. For example,
"SET_DUAL_CARRIAGE CARRIAGE=1" command will activate the carriage defined
in this section (CARRIAGE=0 will return activation to the primary carriage).
Dual carriage support is typically combined with extra extruders - the
SET_DUAL_CARRIAGE command is often called at the same time as the
ACTIVATE_EXTRUDER command. Be sure to park the carriages during deactivation.
Note that during G28 homing, typically the primary carriage is homed first
followed by the carriage defined in the `[dual_carriage]` config section.
However, the `[dual_carriage]` carriage will be homed first if both carriages
home in a positive direction and the [dual_carriage] carriage has a
`position_endstop` greater than the primary carriage, or if both carriages home
in a negative direction and the `[dual_carriage]` carriage has a
`position_endstop` less than the primary carriage.

Additionally, one could use "SET_DUAL_CARRIAGE CARRIAGE=1 MODE=COPY" or
"SET_DUAL_CARRIAGE CARRIAGE=1 MODE=MIRROR" commands to activate either copying
or mirroring mode of the dual carriage, in which case it will follow the
motion of the carriage 0 accordingly. These commands can be used to print
two parts simultaneously - either two identical parts (in COPY mode) or
mirrored parts (in MIRROR mode). Note that COPY and MIRROR modes also require
appropriate configuration of the extruder on the dual carriage, which can
typically be achieved with
"SYNC_EXTRUDER_MOTION MOTION_QUEUE=extruder EXTRUDER=<dual_carriage_extruder>"
or a similar command.

See [sample-idex.cfg](../../config/sample-idex.cfg) for an example
configuration.

```
[dual_carriage]
axis:
#   The axis this extra carriage is on (either x or y). This parameter
#   must be provided.
#safe_distance:
#   The minimum distance (in mm) to enforce between the dual and the primary
#   carriages. If a G-Code command is executed that will bring the carriages
#   closer than the specified limit, such a command will be rejected with an
#   error. If safe_distance is not provided, it will be inferred from
#   position_min and position_max for the dual and primary carriages. If set
#   to 0 (or safe_distance is unset and position_min and position_max are
#   identical for the primary and dual carraiges), the carriages proximity
#   checks will be disabled.
#step_pin:
#dir_pin:
#enable_pin:
#microsteps:
#rotation_distance:
#endstop_pin:
#position_endstop:
#position_min:
#position_max:
#   See the "stepper" section for the definition of the above parameters.
```
