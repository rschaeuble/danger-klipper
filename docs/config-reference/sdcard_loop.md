# Configuration reference

## Optional G-Code features

### [sdcard_loop]

Some printers with stage-clearing features, such as a part ejector or
a belt printer, can find use in looping sections of the sdcard file.
(For example, to print the same part over and over, or repeat the
a section of a part for a chain or other repeated pattern).

See the [command reference](../G-Codes.md#sdcard_loop) for supported
commands. See the [sample-macros.cfg](../../config/sample-macros.cfg)
file for a Marlin compatible M808 G-Code macro.

```
[sdcard_loop]
```
