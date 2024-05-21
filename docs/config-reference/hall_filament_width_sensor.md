# Configuration reference

## Filament sensors

### [hall_filament_width_sensor]

Hall filament width sensor (see
[Hall Filament Width Sensor](../Hall_Filament_Width_Sensor.md)).

```
[hall_filament_width_sensor]
adc1:
adc2:
#   Analog input pins connected to the sensor. These parameters must
#   be provided.
#cal_dia1: 1.50
#cal_dia2: 2.00
#   The calibration values (in mm) for the sensors. The default is
#   1.50 for cal_dia1 and 2.00 for cal_dia2.
#raw_dia1: 9500
#raw_dia2: 10500
#   The raw calibration values for the sensors. The default is 9500
#   for raw_dia1 and 10500 for raw_dia2.
#default_nominal_filament_diameter: 1.75
#   The nominal filament diameter. This parameter must be provided.
#max_difference: 0.200
#   Maximum allowed filament diameter difference in millimeters (mm).
#   If difference between nominal filament diameter and sensor output
#   is more than +- max_difference, extrusion multiplier is set back
#   to %100. The default is 0.200.
#measurement_delay: 70
#   The distance from sensor to the melting chamber/hot-end in
#   millimeters (mm). The filament between the sensor and the hot-end
#   will be treated as the default_nominal_filament_diameter. Host
#   module works with FIFO logic. It keeps each sensor value and
#   position in an array and POP them back in correct position. This
#   parameter must be provided.
#enable: False
#   Sensor enabled or disabled after power on. The default is to
#   disable.
#measurement_interval: 10
#   The approximate distance (in mm) between sensor readings. The
#   default is 10mm.
#logging: False
#   Out diameter to terminal and klipper.log can be turn on|of by
#   command.
#min_diameter: 1.0
#   Minimal diameter for trigger virtual filament_switch_sensor.
#max_diameter:
#   Maximum diameter for triggering virtual filament_switch_sensor.
#   The default is default_nominal_filament_diameter + max_difference.
#use_current_dia_while_delay: False
#   Use the current diameter instead of the nominal diameter while
#   the measurement delay has not run through.
#pause_on_runout:
#runout_gcode:
#insert_gcode:
#event_delay:
#pause_delay:
#   See the "filament_switch_sensor" section for a description of the
#   above parameters.
```
