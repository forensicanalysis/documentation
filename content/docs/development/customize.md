---
title: Collect custom artifacts
weight: 110
description:
---

## Collect a custom set of artifacts

1. Clone the repository `git clone https://github.com/forensicanalysis/artifactcollector`.
2. Run `go generate` to download all artifacts.
3. Add artifact definition yaml files as needed in `pack/artifacts`. Do not edit the
artifact definitions, as they will be overwritten.
4. Edit `pack/ac.yaml` and add the artifacts you want to collect.
5. Run `go generate`. This might yield some errors or problems in your artifacts.
6. On windows you can move the syso into the root folder (e.g. `cp resources\artifactcollector.syso .`)
to enable the icon for the executable and the UAC popup.
7. Run `go build .` to generates an executable.

### Embed binaries

Binaries can be added to `pack/bin` and than included into the artifactcollector
in the `go generate` step. Additionally a corresponding COMMAND artifact like
the following is required.

```yaml
name: Autoruns
sources:
- type: COMMAND
  attributes:
    cmd: autorunsc.exe
    args: ["-x", "-accepteula"]
supported_os: [Windows]
```

Currently the output to stdout and stderr is saved, but generated
files are not collected.