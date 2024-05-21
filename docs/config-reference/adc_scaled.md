# Configuration reference

## Board specific hardware support

### [adc_scaled]

Duet2 Maestro analog scaling by vref and vssa readings. Defining an
adc_scaled section enables virtual adc pins (such as "my_name:PB0")
that are automatically adjusted by the board's vref and vssa
monitoring pins. Be sure to define this config section above any
config sections that use one these virtual pins.

See the
[generic-duet2-maestro.cfg](../../config/generic-duet2-maestro.cfg) file
for an example.

```
[adc_scaled my_name]
vref_pin:
#   The ADC pin to use for VREF monitoring. This parameter must be
#   provided.
vssa_pin:
#   The ADC pin to use for VSSA monitoring. This parameter must be
#   provided.
#smooth_time: 2.0
#   A time value (in seconds) over which the vref and vssa
#   measurements will be smoothed to reduce the impact of measurement
#   noise. The default is 2 seconds.
```
