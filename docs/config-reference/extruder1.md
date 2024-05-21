# Configuration reference

## Additional stepper motors and extruders

### [extruder1]

In a multi-extruder printer add an additional extruder section for
each additional extruder. The additional extruder sections should be
named "extruder1", "extruder2", "extruder3", and so on. See the
"extruder" section for a description of available parameters.

See [sample-multi-extruder.cfg](../../config/sample-multi-extruder.cfg)
for an example configuration.

```
[extruder1]
#step_pin:
#dir_pin:
#...
#   See the "extruder" section for available stepper and heater
#   parameters.
#shared_heater:
#   This option is deprecated and should no longer be specified.
```
