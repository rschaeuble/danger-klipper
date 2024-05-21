# Configuration reference

## Other Custom Modules

### [angle]

Magnetic hall angle sensor support for reading stepper motor angle
shaft measurements using a1333, as5047d, or tle5012b SPI chips. The
measurements are available via the [API Server](../API_Server.md) and
[motion analysis tool](../Debugging.md#motion-analysis-and-data-logging).
See the [G-Code reference](../G-Codes.md#angle) for available commands.

```
[angle my_angle_sensor]
sensor_type:
#   The type of the magnetic hall sensor chip. Available choices are
#   "a1333", "as5047d", and "tle5012b". This parameter must be
#   specified.
#sample_period: 0.000400
#   The query period (in seconds) to use during measurements. The
#   default is 0.000400 (which is 2500 samples per second).
#stepper:
#   The name of the stepper that the angle sensor is attached to (eg,
#   "stepper_x"). Setting this value enables an angle calibration
#   tool. To use this feature, the Python "numpy" package must be
#   installed. The default is to not enable angle calibration for the
#   angle sensor.
cs_pin:
#   The SPI enable pin for the sensor. This parameter must be provided.
#spi_speed:
#spi_bus:
#spi_software_sclk_pin:
#spi_software_mosi_pin:
#spi_software_miso_pin:
#   See the "common SPI settings" section for a description of the
#   above parameters.
```
