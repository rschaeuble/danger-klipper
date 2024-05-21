# Configuration reference

## G-Code macros and events

### [delayed_gcode]

Execute a gcode on a set delay. See the
[command template guide](../Command_Templates.md#delayed-gcodes) and
[command reference](../G-Codes.md#delayed_gcode) for more information.

```
[delayed_gcode my_delayed_gcode]
gcode:
#   A list of G-Code commands to execute when the delay duration has
#   elapsed. G-Code templates are supported. This parameter must be
#   provided.
#initial_duration: 0.0
#   The duration of the initial delay (in seconds). If set to a
#   non-zero value the delayed_gcode will execute the specified number
#   of seconds after the printer enters the "ready" state. This can be
#   useful for initialization procedures or a repeating delayed_gcode.
#   If set to 0 the delayed_gcode will not execute on startup.
#   Default is 0.
```
