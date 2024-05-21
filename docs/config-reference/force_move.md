# Configuration reference

## Optional G-Code features

### [force_move]

This module is enabled by default in DangerKlipper!

Support manually moving stepper motors for diagnostic purposes. Note,
using this feature may place the printer in an invalid state - see the
[command reference](../G-Codes.md#force_move) for important details.

```
[force_move]
#enable_force_move: True
#   Set to true to enable FORCE_MOVE and SET_KINEMATIC_POSITION
#   extended G-Code commands. The default is true.
```
