# Configuration reference

## Common kinematic settings

### None Kinematics

It is possible to define a special "none" kinematics to disable
kinematic support in Klipper. This may be useful for controlling
devices that are not typical 3d-printers or for debugging purposes.

```
[printer]
kinematics: none
max_velocity: 1
max_accel: 1
#   The max_velocity and max_accel parameters must be defined. The
#   values are not used for "none" kinematics.
```
