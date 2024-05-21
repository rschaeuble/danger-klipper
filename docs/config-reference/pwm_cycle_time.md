# Configuration reference

## Additional servos, buttons, and other pins

### [pwm_cycle_time]

Run-time configurable output pins with dynamic pwm cycle timing (one
may define any number of sections with an "pwm_cycle_time" prefix).
Pins configured here will be setup as output pins and one may modify
them at run-time using "SET_PIN PIN=my_pin VALUE=.1 CYCLE_TIME=0.100"
type extended [g-code commands](../G-Codes.md#pwm_cycle_time).

```
[pwm_cycle_time my_pin]
pin:
#value:
#shutdown_value:
#cycle_time: 0.100
#scale:
#   See the "output_pin" section for information on these parameters.
```
