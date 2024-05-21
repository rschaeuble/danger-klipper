# Configuration reference

## Additional servos, buttons, and other pins

### [static_digital_output]

Statically configured digital output pins (one may define any number
of sections with a "static_digital_output" prefix). Pins configured
here will be setup as a GPIO output during MCU configuration. They can
not be changed at run-time.

```
[static_digital_output my_output_pins]
pins:
#   A comma separated list of pins to be set as GPIO output pins. The
#   pin will be set to a high level unless the pin name is prefaced
#   with "!". This parameter must be provided.
```
