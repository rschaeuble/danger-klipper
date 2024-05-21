# Configuration reference

## Fans

### [controller_fan]

Controller cooling fan (one may define any number of sections with a
"controller_fan" prefix). A "controller fan" is a fan that will be
enabled whenever its associated heater or its associated stepper
driver is active. The fan will stop whenever an idle_timeout is
reached to ensure no overheating will occur after deactivating a
watched component.

```
[controller_fan my_controller_fan]
#pin:
#max_power:
#shutdown_speed:
#cycle_time:
#hardware_pwm:
#kick_start_time:
#min_power:
#tachometer_pin:
#tachometer_ppr:
#tachometer_poll_interval:
#enable_pin:
#   See the "fan" section for a description of the above parameters.
#fan_speed: 1.0
#   The fan speed (expressed as a value from 0.0 to 1.0) that the fan
#   will be set to when a heater or stepper driver is active.
#   The default is 1.0
#idle_timeout:
#   The amount of time (in seconds) after a stepper driver or heater
#   was active and the fan should be kept running. The default
#   is 30 seconds.
#idle_speed:
#   The fan speed (expressed as a value from 0.0 to 1.0) that the fan
#   will be set to when a heater or stepper driver was active and
#   before the idle_timeout is reached. The default is fan_speed.
#heater:
#stepper:
#   Name of the config section defining the heater/stepper that this fan
#   is associated with. If a comma separated list of heater/stepper names
#   is provided here, then the fan will be enabled when any of the given
#   heaters/steppers are enabled. The default heater is "extruder", the
#   default stepper is all of them.
```
