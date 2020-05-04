---
title: Processing
weight: 3
description:
---

The command line tool can either run single commands or workflows
The command line tool requires a workflow yml file which is executed on an
arbitrary number of forensicstores, e.g.:

    forensicworkflows workflow --file default.yml test/data/example1.forensicstore

There are currently 3 different types of commands.

##Built-in Command

Run either a builtin Go plugin.

##Docker

Run a docker command. The docker image need to be named xxx/elementary-yyy.
The forensicstore will be mounted '/store'.
 
##Script

Run a script command from the config dir. The config is located at:

- $XDG_CONFIG_HOME/elementary or $HOME/.config/elementary for Unix systems
- $HOME/Library/Application Support/elementary on macOS
- %AppData%/elementary on Windows

The script needs to be prefixed with elementary, e.g. elementary-runkeys.py.
Workflow format
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
