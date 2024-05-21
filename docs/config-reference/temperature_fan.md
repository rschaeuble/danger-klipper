# Configuration reference

## Fans

### [temperature_fan]

Temperature-triggered cooling fans (one may define any number of
sections with a "temperature_fan" prefix). A "temperature fan" is a
fan that will be enabled whenever its associated sensor is above a set
temperature. By default, a temperature_fan has a shutdown_speed equal
to max_power.

See the [command reference](../G-Codes.md#temperature_fan) for additional
information.

```
[temperature_fan my_temp_fan]
#pin:
#max_power:
#shutdown_speed:
#cycle_time:
#hardware_pwm:
#kick_start_time:
#min_power:
#tachometer_pin:
#tachometer_ppr:
#tachometer_poll_interval:
#enable_pin:
#   See the "fan" section for a description of the above parameters.
#sensor_type:
#sensor_pin:
#control:
#max_delta:
#min_temp:
#max_temp:
#   See the "extruder" section for a description of the above parameters.
#pid_Kp:
#pid_Ki:
#pid_Kd:
#   The proportional (pid_Kp), integral (pid_Ki), and derivative
#   (pid_Kd) settings for the PID feedback control system. Klipper
#   evaluates the PID settings with the following general formula:
#     fan_pwm = max_power - (Kp*e + Ki*integral(e) - Kd*derivative(e)) / 255
#   Where "e" is "target_temperature - measured_temperature" and
#   "fan_pwm" is the requested fan rate with 0.0 being full off and
#   1.0 being full on. The pid_Kp, pid_Ki, and pid_Kd parameters must
#   be provided when the PID control algorithm is enabled.
#pid_deriv_time: 2.0
#   A time value (in seconds) over which temperature measurements will
#   be smoothed when using the PID control algorithm. This may reduce
#   the impact of measurement noise. The default is 2 seconds.
#target_temp: 40.0
#   A temperature (in Celsius) that will be the target temperature.
#   The default is 40 degrees.
#max_speed: 1.0
#   The fan speed (expressed as a value from 0.0 to 1.0) that the fan
#   will be set to when the sensor temperature exceeds the set value.
#   The default is 1.0.
#min_speed: 0.3
#   The minimum fan speed (expressed as a value from 0.0 to 1.0) that
#   the fan will be set to for PID temperature fans.
#   The default is 0.3.
#gcode_id:
#   If set, the temperature will be reported in M105 queries using the
#   given id. The default is to not report the temperature via M105.
#reverse: False
#   If true, the working mode of the fan is reversed. If the temperature
#   is lower than the target temperature, the fan speed increases;
#   otherwise, the fan speed decreases.
#   The default is False.
```

```
control: curve
#points:
#  50.0, 0.0
#  55.0, 0.5
#   A user might defne a list of points which consist of a temperature with
#   it's associated fan speed (temp, fan_speed).
#   The target_temp value defines the temperature at which the fan will run
#   at full speed.
#   The algorithm will use linear interpolation to get the fan speeds
#   between two points (if one has defined 0.0 for 50° and 1.0 for 60° the
#   fan would run with 0.5 at 55°)
#cooling_hysteresis: 0.0
#   define the temperature hysteresis for lowering the fan speed
#   (temperature differences to the last measured value that are lower than
#   the hysteresis will not cause lowering of the fan speed)
#heating_hysteresis: 0.0
#   same as cooling_hysteresis but for increasing the fan speed, it is
#   recommended to be left at 0 for safety reasons
#smooth_readings: 10
#   the amount of readings a median should be taken of to determine the fan
#   speed at each update interval, the default is 10
```
