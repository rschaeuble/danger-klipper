# Configuration reference

## Config file helpers

### [include]

Include file support. One may include additional config file from the
main printer config file. Wildcards may also be used (eg,
"configs/\*.cfg", or "configs/\*\*/\*.cfg" if using python version >=3.5).

```
[include my_other_config.cfg]
```
