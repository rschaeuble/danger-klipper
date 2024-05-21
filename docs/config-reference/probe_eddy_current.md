# Configuration reference

### [probe_eddy_current]

Support for eddy current inductive probes. One may define this section
(instead of a probe section) to enable this probe. See the
[command reference](../G-Codes.md#probe_eddy_current) for further information.

```
[probe_eddy_current my_eddy_probe]
sensor_type: ldc1612
#   The sensor chip used to perform eddy current measurements. This
#   parameter must be provided and must be set to ldc1612.
#z_offset:
#   The nominal distance (in mm) between the nozzle and bed that a
#   probing attempt should stop at. This parameter must be provided.
#i2c_address:
#i2c_mcu:
#i2c_bus:
#i2c_software_scl_pin:
#i2c_software_sda_pin:
#i2c_speed:
#   The i2c settings for the sensor chip. See the "common I2C
#   settings" section for a description of the above parameters.
#x_offset:
#y_offset:
#speed:
#lift_speed:
#samples:
#sample_retract_dist:
#samples_result:
#samples_tolerance:
#samples_tolerance_retries:
#   See the "probe" section for information on these parameters.
```
