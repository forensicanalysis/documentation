---
title: Processing
weight: 3
description:
---

The `elementary` command line tool can run single commands or workflows, e.g.:

    elementary run usb test/data/example1.forensicstore

Currently available commands:

- **eventlogs**: Process eventlogs into single events
- **export**: Export selected elements
- **hotfixes**: Process windows hotfixes
- **import-file**: Import files
- **import-forensicstore**: Import forensicstore files
- **import-image**: Import images
- **import-json**: Import json files
- **networking**: Process windows network interfaces
- **plaso**: Process with plaso
- **prefetch**: Process prefetch files
- **run-keys**: Process windows run keys
- **services**: Process windows services
- **shimcache**: Process the shimcache
- **software**: Process uninstall entries
- **usb**: Process windows usb artifacts

<!-- TODO: Output --> 

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

<!--
TODO: ## Workflow format

The workflow.yml file contains a list of tasks like the following:

```yaml
eventlogs:
    command: eventlogs
prefetch:
    command: prefetch
    arguments:
        format: table
        output: prefetch.txt
```
-->
