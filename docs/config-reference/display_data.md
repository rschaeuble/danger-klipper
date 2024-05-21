# Configuration reference

## Display support

### [display_data]

Support for displaying custom data on an lcd screen. One may create
any number of display groups and any number of data items under those
groups. The display will show all the data items for a given group if
the display_group option in the [display] section is set to the given
group name.

A
[default set of display groups](../../klippy/extras/display/display.cfg)
are automatically created. One can replace or extend these
display_data items by overriding the defaults in the main printer.cfg
config file.

```
[display_data my_group_name my_data_name]
position:
#   Comma separated row and column of the display position that should
#   be used to display the information. This parameter must be
#   provided.
text:
#   The text to show at the given position. This field is evaluated
#   using command templates (see docs/Command_Templates.md). This
#   parameter must be provided.
```
