# Configuration reference

## Fans

### [fan]

Print cooling fan.

```
[fan]
pin:
#   Output pin controlling the fan. This parameter must be provided.
#max_power: 1.0
#   The maximum power (0.0 to 1.0) that the pin may be set to. A value
#   of 1.0 enables the pin fully for extended periods, while 0.5 allows
#   it for no more than half the time. Use it to limit total power output
#   (over extended periods) to the fan. This value is combined with
#   min_power to scale fan speed. With `min_power` at 0.3 and
#   `max_power` at 1.0, fan speed request scales between 0.3 (min_power)
#   and 1.0 (max_power). Requesting 10% fan speed results in a value of
#   0.37. Default is 1.0.
#shutdown_speed: 0
#   The desired fan speed (expressed as a value from 0.0 to 1.0) if
#   the micro-controller software enters an error state. The default
#   is 0.
#cycle_time: 0.010
#   The amount of time (in seconds) for each PWM power cycle to the
#   fan. It is recommended this be 10 milliseconds or greater when
#   using software based PWM. The default is 0.010 seconds.
#hardware_pwm: False
#   Enable this to use hardware PWM instead of software PWM. Most fans
#   do not work well with hardware PWM, so it is not recommended to
#   enable this unless there is an electrical requirement to switch at
#   very high speeds. When using hardware PWM the actual cycle time is
#   constrained by the implementation and may be significantly
#   different than the requested cycle_time. The default is False.
#kick_start_time: 0.100
#   Time (in seconds) to run the fan at full speed when either first
#   enabling or increasing it by more than 50% (helps get the fan
#   spinning). The default is 0.100 seconds.
#min_power: 0.0
#   The minimum input power which will power the fan (expressed as a
#   value from 0.0 to 1.0). The default is 0.0.
#
#   To calibrate this setting, start with min_power=0 and max_power=1
#   Gradually lower the fan speed to determine the lowest
#   input speed which reliably drives the fan without stalls. Set
#   min_power to the duty cycle corresponding to this value (for
#   example, 12% -> 0.12) or slightly higher.
#tachometer_pin:
#   Tachometer input pin for monitoring fan speed. A pullup is generally
#   required. This parameter is optional.
#tachometer_ppr: 2
#   When tachometer_pin is specified, this is the number of pulses per
#   revolution of the tachometer signal. For a BLDC fan this is
#   normally half the number of poles. The default is 2.
#tachometer_poll_interval: 0.0015
#   When tachometer_pin is specified, this is the polling period of the
#   tachometer pin, in seconds. The default is 0.0015, which is fast
#   enough for fans below 10000 RPM at 2 PPR. This must be smaller than
#   30/(tachometer_ppr*rpm), with some margin, where rpm is the
#   maximum speed (in RPM) of the fan.
#enable_pin:
#   Optional pin to enable power to the fan. This can be useful for fans
#   with dedicated PWM inputs. Some of these fans stay on even at 0% PWM
#   input. In such a case, the PWM pin can be used normally, and e.g. a
#   ground-switched FET(standard fan pin) can be used to control power to
#   the fan.
```
