# Configuration reference

## Micro-controller configuration

### [mcu]

Configuration of the primary micro-controller.

```
[mcu]
serial:
#   The serial port to connect to the MCU. If unsure (or if it
#   changes) see the "Where's my serial port?" section of the FAQ.
#   This parameter must be provided when using a serial port.
#baud: 250000
#   The baud rate to use. The default is 250000.
#canbus_uuid:
#   If using a device connected to a CAN bus then this sets the unique
#   chip identifier to connect to. This value must be provided when using
#   CAN bus for communication.
#canbus_interface:
#   If using a device connected to a CAN bus then this sets the CAN
#   network interface to use. The default is 'can0'.
#restart_method:
#   This controls the mechanism the host will use to reset the
#   micro-controller. The choices are 'arduino', 'cheetah', 'rpi_usb',
#   and 'command'. The 'arduino' method (toggle DTR) is common on
#   Arduino boards and clones. The 'cheetah' method is a special
#   method needed for some Fysetc Cheetah boards. The 'rpi_usb' method
#   is useful on Raspberry Pi boards with micro-controllers powered
#   over USB - it briefly disables power to all USB ports to
#   accomplish a micro-controller reset. The 'command' method involves
#   sending a Klipper command to the micro-controller so that it can
#   reset itself. The default is 'arduino' if the micro-controller
#   communicates over a serial port, 'command' otherwise.
```

### [mcu my_extra_mcu]

Additional micro-controllers (one may define any number of sections
with an "mcu" prefix). Additional micro-controllers introduce
additional pins that may be configured as heaters, steppers, fans,
etc.. For example, if an "[mcu extra_mcu]" section is introduced, then
pins such as "extra_mcu:ar9" may then be used elsewhere in the config
(where "ar9" is a hardware pin name or alias name on the given mcu).

```
[mcu my_extra_mcu]
# See the "mcu" section for configuration parameters.
```
