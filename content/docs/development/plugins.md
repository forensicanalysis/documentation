---
title: Elementary plugins
weight: 130
description:
---

## Command types

There are three commands types: Built-in Go Commands, Docker Commands or Script Commands.

### Built-in command

`elementary` contains some builtin commands. Those cannot be dynamically extended via plugins.

### Docker commands

Docker commands utilize installed docker images. Those images need to be named xxx/elementary-yyy.
`elementary` loads some image on startup but also handles other images matching the
naming schema.

### Script commands

Script commands are rum from the config dir. The config is located at:

- `$XDG_CONFIG_HOME/elementary` or `$HOME/.config/elementary` for Unix systems
- `$HOME/Library/Application Support/elementary` on macOS
- `%AppData%/elementary` on Windows

The script needs to be prefixed with elementary, e.g. elementary-runkeys.py.
`elementary` installs some scripts on startup but also handles other scripts
matching the naming schema.

<!-- Create plugins -->