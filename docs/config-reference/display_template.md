# Configuration reference

## Display support

### [display_template]

Display data text "macros" (one may define any number of sections with
a display_template prefix). See the
[command templates](../Command_Templates.md) document for information on
template evaluation.

This feature allows one to reduce repetitive definitions in
display_data sections. One may use the builtin `render()` function in
display_data sections to evaluate a template. For example, if one were
to define `[display_template my_template]` then one could use `{
render('my_template') }` in a display_data section.

This feature can also be used for continuous LED updates using the
[SET_LED_TEMPLATE](../G-Codes.md#set_led_template) command.

```
[display_template my_template_name]
#param_<name>:
#   One may specify any number of options with a "param_" prefix. The
#   given name will be assigned the given value (parsed as a Python
#   literal) and will be available during macro expansion. If the
#   parameter is passed in the call to render() then that value will
#   be used during macro expansion. For example, a config with
#   "param_speed = 75" might have a caller with
#   "render('my_template_name', param_speed=80)". Parameter names may
#   not use upper case characters.
text:
#   The text to return when the this template is rendered. This field
#   is evaluated using command templates (see
#   docs/Command_Templates.md). This parameter must be provided.
```
