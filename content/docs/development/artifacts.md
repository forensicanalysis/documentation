---
title: Define Artifacts
weight: 120
description:
---



### Artifact definition files
The artifact definition format is described in detail in the 
[Style Guide](https://github.com/forensicanalysis/artifacts/blob/master/style_guide.md).
The following shows an example for an artifact definition file. It defines the
location of linux audit log files on a system.

``` yaml
name: LinuxAuditLogFiles
doc: Linux audit log files.
sources:
- type: FILE
  attributes: {paths: ['/var/log/audit/*']}
supported_os: [Linux]
```

We use [https://github.com/forensicanalysis/artifacts](https://github.com/forensicanalysis/artifacts) as the main repository for
forensic artifacts definitions.
