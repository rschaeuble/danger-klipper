# Configuration reference

## Optional G-Code features

### [virtual_sdcard]

A virtual sdcard may be useful if the host machine is not fast enough
to run OctoPrint well. It allows the Klipper host software to directly
print gcode files stored in a directory on the host using standard
sdcard G-Code commands (eg, M24).

```
[virtual_sdcard]
path:
#   The path of the local directory on the host machine to look for
#   g-code files. This is a read-only directory (sdcard file writes
#   are not supported). One may point this to OctoPrint's upload
#   directory (generally ~/.octoprint/uploads/ ). This parameter must
#   be provided.
#on_error_gcode:
#   A list of G-Code commands to execute when an error is reported.
#   See docs/Command_Templates.md for G-Code format. The default is to
#   run TURN_OFF_HEATERS.
#with_subdirs: False
#   Enable scanning of subdirectories for the menu and for the
#   M20 and M23 commands. The default is False.
```
