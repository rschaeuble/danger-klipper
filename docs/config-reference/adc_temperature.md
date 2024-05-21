# Configuration reference

## Custom heaters and sensors

### [adc_temperature]

Custom ADC temperature sensors (one may define any number of sections
with an "adc_temperature" prefix). This allows one to define a custom
temperature sensor that measures a voltage on an Analog to Digital
Converter (ADC) pin and uses linear interpolation between a set of
configured temperature/voltage (or temperature/resistance)
measurements to determine the temperature. The resulting sensor can be
used as a sensor_type in a heater section. (For example, if one
defines a "[adc_temperature my_sensor]" section then one may use a
"sensor_type: my_sensor" when defining a heater.) Be sure to place the
sensor section in the config file above its first use in a heater
section.

```
[adc_temperature my_sensor]
#temperature1:
#voltage1:
#temperature2:
#voltage2:
#...
#   A set of temperatures (in Celsius) and voltages (in Volts) to use
#   as reference when converting a temperature. A heater section using
#   this sensor may also specify adc_voltage and voltage_offset
#   parameters to define the ADC voltage (see "Common temperature
#   amplifiers" section for details). At least two measurements must
#   be provided.
#temperature1:
#resistance1:
#temperature2:
#resistance2:
#...
#   Alternatively one may specify a set of temperatures (in Celsius)
#   and resistance (in Ohms) to use as reference when converting a
#   temperature. A heater section using this sensor may also specify a
#   pullup_resistor parameter (see "extruder" section for details). At
#   least two measurements must be provided.
```
