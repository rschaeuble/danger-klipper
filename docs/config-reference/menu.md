# Configuration reference

## Display support

### [menu]

Customizable lcd display menus.

A [default set of menus](../../klippy/extras/display/menu.cfg) are
automatically created. One can replace or extend the menu by
overriding the defaults in the main printer.cfg config file.

See the
[command template document](../Command_Templates.md#menu-templates) for
information on menu attributes available during template rendering.

```
# Common parameters available for all menu config sections.
#[menu __some_list __some_name]
#type: disabled
#   Permanently disabled menu element, only required attribute is 'type'.
#   Allows you to easily disable/hide existing menu items.

#[menu some_name]
#type:
#   One of command, input, list, text:
#       command - basic menu element with various script triggers
#       input   - same like 'command' but has value changing capabilities.
#                 Press will start/stop edit mode.
#       list    - it allows for menu items to be grouped together in a
#                 scrollable list.  Add to the list by creating menu
#                 configurations using "some_list" as a prefix - for
#                 example: [menu some_list some_item_in_the_list]
#       vsdlist - same as 'list' but will append files from virtual sdcard
#                 (will be removed in the future)
#name:
#   Name of menu item - evaluated as a template.
#enable:
#   Template that evaluates to True or False.
#index:
#   Position where an item needs to be inserted in list. By default
#   the item is added at the end.

#[menu some_list]
#type: list
#name:
#enable:
#   See above for a description of these parameters.

#[menu some_list some_command]
#type: command
#name:
#enable:
#   See above for a description of these parameters.
#gcode:
#   Script to run on button click or long click. Evaluated as a
#   template.

#[menu some_list some_input]
#type: input
#name:
#enable:
#   See above for a description of these parameters.
#input:
#   Initial value to use when editing - evaluated as a template.
#   Result must be float.
#input_min:
#   Minimum value of range - evaluated as a template. Default -99999.
#input_max:
#   Maximum value of range - evaluated as a template. Default 99999.
#input_step:
#   Editing step - Must be a positive integer or float value. It has
#   internal fast rate step. When "(input_max - input_min) /
#   input_step > 100" then fast rate step is 10 * input_step else fast
#   rate step is same input_step.
#realtime:
#   This attribute accepts static boolean value. When enabled then
#   gcode script is run after each value change. The default is False.
#gcode:
#   Script to run on button click, long click or value change.
#   Evaluated as a template. The button click will trigger the edit
#   mode start or end.
```
