# Configuration reference

## LEDs

### [neopixel]

Neopixel (aka WS2812) LED support (one may define any number of
sections with a "neopixel" prefix). See the
[command reference](../G-Codes.md#led) for more information.

Note that the [linux mcu](../RPi_microcontroller.md) implementation does
not currently support directly connected neopixels. The current design
using the Linux kernel interface does not allow this scenario because
the kernel GPIO interface is not fast enough to provide the required
pulse rates.

```
[neopixel my_neopixel]
pin:
#   The pin connected to the neopixel. This parameter must be
#   provided.
#chain_count:
#   The number of Neopixel chips that are "daisy chained" to the
#   provided pin. The default is 1 (which indicates only a single
#   Neopixel is connected to the pin).
#color_order: GRB
#   Set the pixel order required by the LED hardware (using a string
#   containing the letters R, G, B, W with W optional). Alternatively,
#   this may be a comma separated list of pixel orders - one for each
#   LED in the chain. The default is GRB.
#initial_RED: 0.0
#initial_GREEN: 0.0
#initial_BLUE: 0.0
#initial_WHITE: 0.0
#   See the "led" section for information on these parameters.
```
