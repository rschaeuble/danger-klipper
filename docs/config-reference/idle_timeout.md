# Configuration reference

## G-Code macros and events

### [idle_timeout]

Idle timeout. An idle timeout is automatically enabled - add an
explicit idle_timeout config section to change the default settings.

```
[idle_timeout]
#gcode:
#   A list of G-Code commands to execute on an idle timeout. See
#   docs/Command_Templates.md for G-Code format. The default is to run
#   "TURN_OFF_HEATERS" and "M84".
#timeout: 600
#   Idle time (in seconds) to wait before running the above G-Code
#   commands. Set it to 0 to disable the timeout feature.
#   The default is 600 seconds.
```
