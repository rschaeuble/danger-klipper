# Configuration reference

## Additional servos, buttons, and other pins

### [multi_pin]

Multiple pin outputs (one may define any number of sections with a
"multi_pin" prefix). A multi_pin output creates an internal pin alias
that can modify multiple output pins each time the alias pin is
set. For example, one could define a "[multi_pin my_fan]" object
containing two pins and then set "pin=multi_pin:my_fan" in the "[fan]"
section - on each fan change both output pins would be updated. These
aliases may not be used with stepper motor pins.

```
[multi_pin my_multi_pin]
pins:
#   A comma separated list of pins associated with this alias. This
#   parameter must be provided.
```
