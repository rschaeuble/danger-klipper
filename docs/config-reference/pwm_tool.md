# Configuration reference

## Additional servos, buttons, and other pins

### [pwm_tool]

Pulse width modulation digital output pins capable of high speed
updates (one may define any number of sections with an "output_pin"
prefix). Pins configured here will be setup as output pins and one may
modify them at run-time using "SET_PIN PIN=my_pin VALUE=.1" type
extended [g-code commands](../G-Codes.md#output_pin).

```
[pwm_tool my_tool]
pin:
#   The pin to configure as an output. This parameter must be provided.
#maximum_mcu_duration:
#   The maximum duration a non-shutdown value may be driven by the MCU
#   without an acknowledge from the host.
#   If host can not keep up with an update, the MCU will shutdown
#   and set all pins to their respective shutdown values.
#   Default: 0 (disabled)
#   Usual values are around 5 seconds.
#value:
#shutdown_value:
#cycle_time: 0.100
#hardware_pwm: False
#scale:
#   See the "output_pin" section for the definition of these parameters.
```
