# Configuration reference

## Bed level support

### [skew_correction]

Printer Skew Correction. It is possible to use software to correct
printer skew across 3 planes, xy, xz, yz. This is done by printing a
calibration model along a plane and measuring three lengths. Due to
the nature of skew correction these lengths are set via gcode. See
[Skew Correction](../Skew_Correction.md) and
[Command Reference](../G-Codes.md#skew_correction) for details.

```
[skew_correction]
```
