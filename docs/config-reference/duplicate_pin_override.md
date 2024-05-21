# Configuration reference

## Config file helpers

### [duplicate_pin_override]

This tool allows a single micro-controller pin to be defined multiple
times in a config file without normal error checking. This is intended
for diagnostic and debugging purposes. This section is not needed
where Klipper supports using the same pin multiple times, and using
this override may cause confusing and unexpected results.

```
[duplicate_pin_override]
pins:
#   A comma separated list of pins that may be used multiple times in
#   a config file without normal error checks. This parameter must be
#   provided.
```
