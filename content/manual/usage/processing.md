---
title: Processing with elementary
weight: 30
description:
---

Elementary is a command line tool that can create and process forensicstore
files.

## Unpack forensicstores

To extract all file artifacts stored in the forensicstore you can use:

``` shell
elementary archive unpack TestMachine.forensicstore
```

More examples:

``` shell
# Extract all prefetch files
elementary archive unpack --match "*.pf" TestMachine.forensicstore

# Extract all windows eventlogs recreateing the original folder structure
elementary archive unpack --match "*.evtx" --mode folder \
    --prefix-artifact=false TestMachine.forensicstore
```
## Run forensic tasks

The `elementary` command line tool can run single commands, e.g.:

```shell
elementary run usb TestMachine.forensicstore
```

<!--
Some available commands are explained below.

### eventlogs
Process eventlogs into single events

``` shell
elementary run eventlogs TestMachine.forensicstore
```

### export
Export selected elements

### hotfixes
Process windows hotfixes

### import-file
Import files

### import-forensicstore
Import forensicstore files. This can be used

### import-image
Import images

### import-json
Import json files

### networking
Process windows network interfaces

### plaso
Process with plaso

### prefetch
Process prefetch files

### run-keys
Process windows run keys

### services
Process windows services

### shimcache
Process the shimcache

### software
Process uninstall entries

### usb
Process windows usb artifacts


An updated list can be seen using the `elementary run` command.

<!-- TODO: Output -->


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
