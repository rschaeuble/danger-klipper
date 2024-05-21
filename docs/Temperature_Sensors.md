# Temperature sensors

Klipper includes definitions for many types of temperature sensors.
These sensors may be used in any config section that requires a
temperature sensor (such as an `[extruder]` or `[heater_bed]`
section).

## Common thermistors

Common thermistors. The following parameters are available in heater
sections that use one of these sensors.

```
sensor_type:
#   One of "EPCOS 100K B57560G104F", "ATC Semitec 104GT-2",
#   "ATC Semitec 104NT-4-R025H42G", "Generic 3950",
#   "Honeywell 100K 135-104LAG-J01", "NTC 100K MGB18-104F39050L32",
#   "SliceEngineering 450", or "TDK NTCG104LH104JT1"
sensor_pin:
#   Analog input pin connected to the thermistor. This parameter must
#   be provided.
#pullup_resistor: 4700
#   The resistance (in ohms) of the pullup attached to the thermistor.
#   The default is 4700 ohms.
#inline_resistor: 0
#   The resistance (in ohms) of an extra (not heat varying) resistor
#   that is placed inline with the thermistor. It is rare to set this.
#   The default is 0 ohms.
```

## Common temperature amplifiers

Common temperature amplifiers. The following parameters are available
in heater sections that use one of these sensors.

```
sensor_type:
#   One of "PT100 INA826", "AD595", "AD597", "AD8494", "AD8495",
#   "AD8496", or "AD8497".
sensor_pin:
#   Analog input pin connected to the sensor. This parameter must be
#   provided.
#adc_voltage: 5.0
#   The ADC comparison voltage (in Volts). The default is 5 volts.
#voltage_offset: 0
#   The ADC voltage offset (in Volts). The default is 0.
```

## Directly connected PT1000 sensor

Directly connected PT1000 sensor. The following parameters are
available in heater sections that use one of these sensors.

```
sensor_type: PT1000
sensor_pin:
#   Analog input pin connected to the sensor. This parameter must be
#   provided.
#pullup_resistor: 4700
#   The resistance (in ohms) of the pullup attached to the sensor. The
#   default is 4700 ohms.
```

## MAXxxxxx temperature sensors

MAXxxxxx serial peripheral interface (SPI) temperature based
sensors. The following parameters are available in heater sections
that use one of these sensor types.

```
sensor_type:
#   One of "MAX6675", "MAX31855", "MAX31856", or "MAX31865".
sensor_pin:
#   The chip select line for the sensor chip. This parameter must be
#   provided.
#spi_speed: 4000000
#   The SPI speed (in hz) to use when communicating with the chip.
#   The default is 4000000.
#spi_bus:
#spi_software_sclk_pin:
#spi_software_mosi_pin:
#spi_software_miso_pin:
#   See the "common SPI settings" section for a description of the
#   above parameters.
#tc_type: K
#tc_use_50Hz_filter: False
#tc_averaging_count: 1
#   The above parameters control the sensor parameters of MAX31856
#   chips. The defaults for each parameter are next to the parameter
#   name in the above list.
#rtd_nominal_r: 100
#rtd_reference_r: 430
#rtd_num_of_wires: 2
#rtd_use_50Hz_filter: False
#   The above parameters control the sensor parameters of MAX31865
#   chips. The defaults for each parameter are next to the parameter
#   name in the above list.
```

## BMP180/BMP280/BME280/BMP388/BME680 temperature sensor

BMP180/BMP280/BME280/BMP388/BME680 two wire interface (I2C) environmental sensors.
Note that these sensors are not intended for use with extruders and
heater beds, but rather for monitoring ambient temperature (C),
pressure (hPa), relative humidity and in case of the BME680 gas level.
See [sample-macros.cfg](../config/sample-macros.cfg) for a gcode_macro
that may be used to report pressure and humidity in addition to
temperature.

```
sensor_type: BME280
#i2c_address:
#   Default is 118 (0x76). The BMP180, BMP388 and some BME280 sensors
#   have an address of 119 (0x77).
#i2c_mcu:
#i2c_bus:
#i2c_software_scl_pin:
#i2c_software_sda_pin:
#i2c_speed:
#   See the "common I2C settings" section for a description of the
#   above parameters.
```

## AHT10/AHT20/AHT21 temperature sensor

AHT10/AHT20/AHT21 two wire interface (I2C) environmental sensors.
Note that these sensors are not intended for use with extruders and
heater beds, but rather for monitoring ambient temperature (C) and
relative humidity. See
[sample-macros.cfg](../config/sample-macros.cfg) for a gcode_macro
that may be used to report humidity in addition to temperature.

```
sensor_type: AHT10
#   Also use AHT10 for AHT20 and AHT21 sensors.
#i2c_address:
#   Default is 56 (0x38). Some AHT10 sensors give the option to use
#   57 (0x39) by moving a resistor.
#i2c_mcu:
#i2c_bus:
#i2c_speed:
#   See the "common I2C settings" section for a description of the
#   above parameters.
#aht10_report_time:
#   Interval in seconds between readings. Default is 30, minimum is 5
```

## HTU21D sensor

HTU21D family two wire interface (I2C) environmental sensor. Note that
this sensor is not intended for use with extruders and heater beds,
but rather for monitoring ambient temperature (C) and relative
humidity. See [sample-macros.cfg](../config/sample-macros.cfg) for a
gcode_macro that may be used to report humidity in addition to
temperature.

```
sensor_type:
#   Must be "HTU21D" , "SI7013", "SI7020", "SI7021" or "SHT21"
#i2c_address:
#   Default is 64 (0x40).
#i2c_mcu:
#i2c_bus:
#i2c_software_scl_pin:
#i2c_software_sda_pin:
#i2c_speed:
#   See the "common I2C settings" section for a description of the
#   above parameters.
#htu21d_hold_master:
#   If the sensor can hold the I2C buf while reading. If True no other
#   bus communication can be performed while reading is in progress.
#   Default is False.
#htu21d_resolution:
#   The resolution of temperature and humidity reading.
#   Valid values are:
#    'TEMP14_HUM12' -> 14bit for Temp and 12bit for humidity
#    'TEMP13_HUM10' -> 13bit for Temp and 10bit for humidity
#    'TEMP12_HUM08' -> 12bit for Temp and 08bit for humidity
#    'TEMP11_HUM11' -> 11bit for Temp and 11bit for humidity
#   Default is: "TEMP11_HUM11"
#htu21d_report_time:
#   Interval in seconds between readings. Default is 30
```

## SHT3X sensor

SHT3X family two wire interface (I2C) environmental sensor. These sensors
have a range of -55~125 C, so are usable for e.g. chamber temperature
monitoring. They can also function as simple fan/heater controllers.

```
sensor_type: SHT3X
#i2c_address:
#   Default is 68 (0x44).
#i2c_mcu:
#i2c_bus:
#i2c_software_scl_pin:
#i2c_software_sda_pin:
#i2c_speed:
#   See the "common I2C settings" section for a description of the
#   above parameters.
```

## LM75 temperature sensor

LM75/LM75A two wire (I2C) connected temperature sensors. These sensors
have a range of -55~125 C, so are usable for e.g. chamber temperature
monitoring. They can also function as simple fan/heater controllers.

```
sensor_type: LM75
#i2c_address:
#   Default is 72 (0x48). Normal range is 72-79 (0x48-0x4F) and the 3
#   low bits of the address are configured via pins on the chip
#   (usually with jumpers or hard wired).
#i2c_mcu:
#i2c_bus:
#i2c_software_scl_pin:
#i2c_software_sda_pin:
#i2c_speed:
#   See the "common I2C settings" section for a description of the
#   above parameters.
#lm75_report_time:
#   Interval in seconds between readings. Default is 0.8, with minimum
#   0.5.
```

## Builtin micro-controller temperature sensor

The atsam, atsamd, stm32 and rp2040 micro-controllers contain an internal
temperature sensor. One can use the "temperature_mcu" sensor to
monitor these temperatures.

```
sensor_type: temperature_mcu
#sensor_mcu: mcu
#   The micro-controller to read from. The default is "mcu".
#reference_voltage:
#   The reference voltage for the ADC of the mcu. Default is 3.3
#sensor_temperature1:
#sensor_adc1:
#   Specify the above two parameters (a temperature in Celsius and an
#   ADC value as a float between 0.0 and 1.0) to calibrate the
#   micro-controller temperature. This may improve the reported
#   temperature accuracy on some chips. A typical way to obtain this
#   calibration information is to completely remove power from the
#   printer for a few hours (to ensure it is at the ambient
#   temperature), then power it up and use the QUERY_ADC command to
#   obtain an ADC measurement. Use some other temperature sensor on
#   the printer to find the corresponding ambient temperature. The
#   default is to use the factory calibration data on the
#   micro-controller (if applicable) or the nominal values from the
#   micro-controller specification.
#sensor_temperature2:
#sensor_adc2:
#   If sensor_temperature1/sensor_adc1 is specified then one may also
#   specify sensor_temperature2/sensor_adc2 calibration data. Doing so
#   may provide calibrated "temperature slope" information. The
#   default is to use the factory calibration data on the
#   micro-controller (if applicable) or the nominal values from the
#   micro-controller specification.
```

## Host temperature sensor

Temperature from the machine (eg Raspberry Pi) running the host software.

```
sensor_type: temperature_host
#sensor_path:
#   The path to temperature system file. The default is
#   "/sys/class/thermal/thermal_zone0/temp" which is the temperature
#   system file on a Raspberry Pi computer.
```

## DS18B20 temperature sensor

DS18B20 is a 1-wire (w1) digital temperature sensor. Note that this sensor is not intended
for use with extruders and heater beds, but rather for monitoring ambient temperature (C).
These sensors have range up to 125 C, so are usable for e.g. chamber temperature monitoring.
They can also function as simple fan/heater controllers. DS18B20 sensors are only supported
on the "host mcu", e.g. the Raspberry Pi. The w1-gpio Linux kernel module must be installed.

```
sensor_type: DS18B20
serial_no:
#   Each 1-wire device has a unique serial number used to identify the device,
#   usually in the format 28-031674b175ff. This parameter must be provided.
#   Attached 1-wire devices can be listed using the following Linux command:
#   ls /sys/bus/w1/devices/
#ds18_report_time:
#   Interval in seconds between readings. Default is 3.0, with a minimum of 1.0
#sensor_mcu:
#   The micro-controller to read from. Must be the host_mcu
```

## Combined temperature sensor

Combined temperature sensor is a virtual temperature sensor based on several other sensors.
This sensor can be used with extruders, heater_generic and heater beds.

```
sensor_type: temperature_combined
#sensor_list:
#   Must be provided. List of sensors to combine to new "virtual"
#   sensor.
#   E.g. 'temperature_sensor sensor1,extruder,heater_bed'
#combination_method:
#   Must be provided. Combination method used for the sensor.
#   Available options are 'max', 'min', 'mean'.
#maximum_deviation:
#   Must be provided. Maximum permissible deviation between the sensors
#   to combine (e.g. 5 degrees). To disable it, use a large value (e.g. 999.9)
```
