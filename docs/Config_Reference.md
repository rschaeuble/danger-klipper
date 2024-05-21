# Configuration reference

This document is a reference for options available in the Klipper
config file.

The descriptions in this document are formatted so that it is possible
to cut-and-paste them into a printer config file. See the
[installation document](Installation.md) for information on setting up
Klipper and choosing an initial config file.

## Micro-controller configuration

#### Format of micro-controller pin names

Many config options require the name of a micro-controller pin.
Klipper uses the hardware names for these pins - for example `PA4`.

Pin names may be preceded by `!` to indicate that a reverse polarity
should be used (eg, trigger on low instead of high).

Input pins may be preceded by `^` to indicate that a hardware pull-up
resistor should be enabled for the pin. If the micro-controller
supports pull-down resistors then an input pin may alternatively be
preceded by `~`.

Note, some config sections may "create" additional pins. Where this
occurs, the config section defining the pins must be listed in the
config file before any sections using those pins.

#### [[mcu]](config-reference/mcu.md)

## Danger Options

#### [[danger_options]](config-reference/danger_options.md)

## Common kinematic settings

#### [[printer]](config-reference/printer.md)

#### [[stepper]](config-reference/stepper.md)

#### [Cartesian Kinematics](config-reference/kin_cartesian.md)

#### [Cartesian Kinematics with limits for X and Y axes](config-reference/kin_limited_cartesian.md)

#### [Linear Delta Kinematics](config-reference/kin-delta.md)

#### [Deltesian Kinematics](config-reference/kin_deltesian.md)

#### [CoreXY Kinematics](config-reference/kin_corexy.md)

#### [CoreXY Kinematics with limits for X and Y axes](config-reference/kin_limited_corexy.md)

#### [CoreXZ Kinematics](config-reference/kin_corexz.md)

#### [Hybrid-CoreXY Kinematics](config-reference/kin_hybrid_corexy.md)

#### [Hybrid-CoreXZ Kinematics](config-reference/kin_hybrid_corexz.md)

#### [Polar Kinematics](config-reference/kin_polar.md)

#### [Rotary delta Kinematics](config-reference/kin_rotary_delta.md)

#### [Cable winch Kinematics](config-reference/kin_winch.md)

#### [None Kinematics](config-reference/kin_none.md)

## Common extruder and heated bed support

#### [[extruder]](config-reference/extruder.md)

#### [[heater_bed]](config-reference/heater_bed.md)

## Bed level support

#### [[bed_mesh]](config-reference/bed_mesh.md)

#### [[bed_tilt]](config-reference/bed_tilt.md)

#### [[bed_screws]](config-reference/bed_screws.md)

#### [[screws_tilt_adjust]](config-reference/screws_tilt_adjust.md)

#### [[z_tilt]](config-reference/z_tilt.md)

#### [[quad_gantry_level]](config-reference/quad_gantry_level.md)

#### [[skew_correction]](config-reference/skew_correction.md)

#### [[z_thermal_adjust]](config-reference/z_thermal_adjust.md)

## Customized homing

#### [[safe_z_home]](config-reference/safe_z_home.md)

#### [[homing_override]](config-reference/homing_override.md)

#### [[endstop_phase]](config-reference/endstop_phase.md)

## G-Code macros and events

#### [[gcode_macro]](config-reference/gcode_macro.md)

#### [[delayed_gcode]](config-reference/delayed_gcode.md)

#### [[save_variables]](config-reference/save_variables.md)

#### [[idle_timeout]](config-reference/idle_timeout.md)

## Optional G-Code features

#### [[virtual_sdcard]](config-reference/virtual_sdcard.md)

#### [[sdcard_loop]](config-reference/sdcard_loop.md)

#### [[force_move]](config-reference/force_move.md)

#### [[pause_resume]](config-reference/pause_resume.md)

#### [[firmware_retraction]](config-reference/firmware_retraction.md)

#### [[gcode_arcs]](config-reference/gcode_arcs.md)

#### [[respond]](config-reference/respond.md)

#### [[exclude_object]](config-reference/exclude_object.md)

## Resonance compensation

#### [[input_shaper]](config-reference/input_shaper.md)

#### [[adxl345]](config-reference/adxl345.md)

#### [[lis2dw]](config-reference/lis2dw.md)

#### [[mpu9250]](config-reference/mpu9250.md)

#### [[resonance_tester]](config-reference/resonance_tester.md)

## Config file helpers

#### [[board_pins]](config-reference/board_pins.md)

#### [[include]](config-reference/include.md)

#### [[duplicate_pin_override]](config-reference/duplicate_pin_override.md)

## Bed probing hardware

#### [[probe]](config-reference/probe.md)

#### [[bltouch]](config-reference/bltouch.md)

#### [[dockable_probe]](config-reference/dockable_probe.md)

#### [[smart_effector]](config-reference/smart_effector.md)

#### [[probe_eddy_current]](config-reference/probe_eddy_current.md)

#### [[axis_twist_compensation]](config-reference/axis_twist_compensation.md)

#### [[z_calibration]](config-reference/z_calibration.md)

## Additional stepper motors and extruders

#### [[stepper_z1]](config-reference/stepper_z1.md)

#### [[extruder1]](config-reference/extruder1.md)

#### [[dual_carriage]](config-reference/dual_carriage.md)

#### [[extruder_stepper]](config-reference/extruder_stepper.md)

#### [[manual_stepper]](config-reference/manual_stepper.md)

## Custom heaters and sensors

#### [[verify_heater]](config-reference/verify_heater.md)

#### [[homing_heaters]](config-reference/homing_heaters.md)

#### [[thermistor]](config-reference/thermistor.md)

#### [[adc_temperature]](config-reference/adc_temperature.md)

#### [[heater_generic]](config-reference/heater_generic.md)

#### [[temperature_sensor]](config-reference/temperature_sensor.md)

## [Temperature sensors](Temperature_Sensors.md)

## Fans

#### [[fan]](config-reference/fan.md)

#### [[heater_fan]](config-reference/heater_fan.md)

#### [[controller_fan]](config-reference/controller_fan.md)

#### [[temperature_fan]](config-reference/temperature_fan.md)

#### [[fan_generic]](config-reference/fan_generic.md)

## LEDs

#### [[led]](config-reference/led.md)

#### [[neopixel]](config-reference/neopixel.md)

#### [[dotstar]](config-reference/dotstar.md)

#### [[pca9533]](config-reference/pca9533.md)

#### [[pca9632]](config-reference/pca9632.md)

## Additional servos, buttons, and other pins

#### [[servo]](config-reference/servo.md)

#### [[gcode_button]](config-reference/gcode_button.md)

#### [[output_pin]](config-reference/output_pin.md)

#### [[pwm_tool]](config-reference/pwm_tool.md)

#### [[pwm_cycle_time]](config-reference/pwm_cycle_time.md)

#### [[static_digital_output]](config-reference/static_digital_output.md)

#### [[multi_pin]](config-reference/multi_pin.md)

## TMC stepper driver configuration

Configuration of Trinamic stepper motor drivers in UART/SPI mode.
Additional information is in the [TMC Drivers guide](TMC_Drivers.md)
and in the [command reference](G-Codes.md#tmcxxxx).

#### [[tmc2130]](config-reference/tmc2130.md)

#### [[tmc2208]](config-reference/tmc2208.md)

#### [[tmc2209]](config-reference/tmc2209.md)

#### [[tmc2660]](config-reference/tmc2660.md)

#### [[tmc2240]](config-reference/tmc2240.md)

#### [[tmc5160]](config-reference/tmc5160.md)

## Run-time stepper motor current configuration

#### [[ad5206]](config-reference/ad5206.md)

#### [[mcp4451]](config-reference/mcp4451.md)

#### [[mcp4728]](config-reference/mpc4728.md)

#### [[mcp4018]](config-reference/mcp4018.md)

## Display support

#### [[display]](config-reference/display.md)

#### [[display_data]](config-reference/display_data.md)

#### [[display_template]](config-reference/display_template.md)

#### [[display_glyph]](config-reference/display_glyph.md)

#### [[display my_extra_display]](config-reference/display_extra.md)

#### [[menu]](config-reference/menu.md)

## Filament sensors

#### [[filament_switch_sensor]](config-reference/filament_switch_sensor.md)

#### [[filament_motion_sensor]](config-reference/filament_motion_sensor.md)

#### [[tsl1401cl_filament_width_sensor]](config-reference/tsl1401cl_filament_width_sensor.md)

#### [[hall_filament_width_sensor]](config-reference/hall_filament_width_sensor.md)

#### [[belay]](config-reference/belay.md)

## Board specific hardware support

#### [[sx1509]](config-reference/sx1509.md)

#### [[samd_sercom]](config-reference/samd_sercom.md)

#### [[adc_scaled]](config-reference/adc_scaled.md)

#### [[replicape]](config-reference/replicape.md)

## Other Custom Modules

#### [[palette2]](config-reference/palette2.md)

#### [[angle]](config-reference/angle.md)

#### [[trad_rack]](config-reference/trad_rack.md)

## Common bus parameters

#### Common SPI settings

The following parameters are generally available for devices using an
SPI bus.

```
#spi_speed:
#   The SPI speed (in hz) to use when communicating with the device.
#   The default depends on the type of device.
#spi_bus:
#   If the micro-controller supports multiple SPI busses then one may
#   specify the micro-controller bus name here. The default depends on
#   the type of micro-controller.
#spi_software_sclk_pin:
#spi_software_mosi_pin:
#spi_software_miso_pin:
#   Specify the above parameters to use "software based SPI". This
#   mode does not require micro-controller hardware support (typically
#   any general purpose pins may be used). The default is to not use
#   "software spi".
```

#### Common I2C settings

The following parameters are generally available for devices using an
I2C bus.

Note that Klipper's current micro-controller support for I2C is
generally not tolerant to line noise. Unexpected errors on the I2C
wires may result in Klipper raising a run-time error. Klipper's
support for error recovery varies between each micro-controller type.
It is generally recommended to only use I2C devices that are on the
same printed circuit board as the micro-controller.

Most Klipper micro-controller implementations only support an
`i2c_speed` of 100000 (_standard mode_, 100kbit/s). The Klipper "Linux"
micro-controller supports a 400000 speed (_fast mode_, 400kbit/s), but it must be
[set in the operating system](RPi_microcontroller.md#optional-enabling-i2c)
and the `i2c_speed` parameter is otherwise ignored. The Klipper
"RP2040" micro-controller and ATmega AVR family support a rate of 400000
via the `i2c_speed` parameter. All other Klipper micro-controllers use a
100000 rate and ignore the `i2c_speed` parameter.

```
#i2c_address:
#   The i2c address of the device. This must specified as a decimal
#   number (not in hex). The default depends on the type of device.
#i2c_mcu:
#   The name of the micro-controller that the chip is connected to.
#   The default is "mcu".
#i2c_bus:
#   If the micro-controller supports multiple I2C busses then one may
#   specify the micro-controller bus name here. The default depends on
#   the type of micro-controller.
#i2c_software_scl_pin:
#i2c_software_sda_pin:
#   Specify these parameters to use micro-controller software based
#   I2C "bit-banging" support. The two parameters should the two pins
#   on the micro-controller to use for the scl and sda wires. The
#   default is to use hardware based I2C support as specified by the
#   i2c_bus parameter.
#i2c_speed:
#   The I2C speed (in Hz) to use when communicating with the device.
#   The Klipper implementation on most micro-controllers is hard-coded
#   to 100000 and changing this value has no effect. The default is
#   100000. Linux, RP2040 and ATmega support 400000.
```
