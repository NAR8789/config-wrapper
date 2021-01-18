wrapper script to add an xdg-respecting config file to commands that weren't built with config support

# Quickstart

1. Create a bash-flavored config file at `~/.config/YOUR_NAMESPACE/config.sh` (or at `$XDG_CONFIG_HOME/YOUR_NAMESPACE_HERE/config.sh` if you've customized your XDG dirs).
2. Populate said config file with some bash variables.
3. run `cfg YOUR_NAMESPACE COMMAND...`. This executes `COMMAND` with the variables defined in `config.sh` added to the environment.

`COMMAND` will also see the following additional env vars:
- `CFG_NAMESPACE`: the namespace passed to `cfg` (`YOUR_NAMESPACE` in the example above)
- `XDG_CONFIG_HOME`: `~/.config`, or the environment-configured value if already set
- `CONFIG_DIR`: `$XDG_CONFIG_HOME/$CFG_HAMESPACE/`, or the environment-configured value if already set
- `CONFIG`: `$CONFIG_DIR/config.sh`, or the environment-configured value if already set
- `XDG_CACHE_HOME`: `~/.cache`, or the environment-configured value if already set
- `CACHE_DIR`: `$XDG_CACHE_HOME/$CFG_NAMESPACE`, or the environment-configured value if already set
