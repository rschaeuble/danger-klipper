# Configuration reference

## Optional G-Code features

### [pause_resume]

Pause/Resume functionality with support of position capture and
restore. See the [command reference](../G-Codes.md#pause_resume) for more
information.

```
[pause_resume]
#recover_velocity: 50.
#   When capture/restore is enabled, the speed at which to return to
#   the captured position (in mm/s). Default is 50.0 mm/s.
```
