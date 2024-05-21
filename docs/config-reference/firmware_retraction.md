# Configuration reference

## Optional G-Code features

### [firmware_retraction]

Firmware filament retraction. This enables G10 (retract) and G11
(unretract) GCODE commands issued by many slicers. The parameters
below provide startup defaults, although the values can be adjusted
via the SET_RETRACTION [command](../G-Codes.md#firmware_retraction)),
allowing per-filament settings and runtime tuning.

```
[firmware_retraction]
#retract_length: 0.0
#   The length of filament (in mm) to retract when a G10 command is
#   executed. When a G11 command is executed, the unretract_length
#   is the sum of the retract_length and the unretract_extra_length
#   (see below). The minimum value and default are 0 mm, which
#   disables firmware retraction.
#retract_speed: 20.0
#   The speed of filament retraction moves (in mm/s).
#   This value is typically set relatively high (>40 mm/s),
#   except for soft and/oozy filaments like TPU and PETG
#   (20 to 30 mm/s). The minimum value is 1 mm/s, the default value
#   is 20 mm/s.
#unretract_extra_length: 0.0
#   The *additional* length (in mm) to add or the length to subtract
#   from the filament move when unretracting compared to the retract
#   move length. This allows priming the nozzle (positive extra length)
#   or delaying extrusion after unretracting (negative length). The
#   latter may help reduce blobbing. The minimum value is -1 mm
#   (2.41 mm3 volume for 1.75 mm filament), the default value is 0 mm.
#unretract_speed: 10.0
#   The speed of filament unretraction moves (in mm/s).
#   This parameter is not particularly critical, although often lower
#   than retract_speed. The minimum value is 1 mm/s, the default value
#   is 10 mm/s.
#z_hop_height: 0.0
#   The vertical height by which the nozzle is lifted from the print to
#   prevent collisions with the print during travel moves when retracted.
#   The minimum value is 0 mm, the default value is 0 mm, which disables
#   zhop moves.
```
