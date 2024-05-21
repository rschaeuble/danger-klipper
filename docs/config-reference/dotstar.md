# Configuration reference

## LEDs

### [dotstar]

Dotstar (aka APA102) LED support (one may define any number of
sections with a "dotstar" prefix). See the
[command reference](../G-Codes.md#led) for more information.

```
[dotstar my_dotstar]
data_pin:
#   The pin connected to the data line of the dotstar. This parameter
#   must be provided.
clock_pin:
#   The pin connected to the clock line of the dotstar. This parameter
#   must be provided.
#chain_count:
#   See the "neopixel" section for information on this parameter.
#initial_RED: 0.0
#initial_GREEN: 0.0
#initial_BLUE: 0.0
#   See the "led" section for information on these parameters.
```
