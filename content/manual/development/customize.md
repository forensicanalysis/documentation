---
title: Collect custom artifacts
weight: 110
description:
---

Forensic investigations differ and investigators have different approaches in forensic cases. The artifactcollector can cater to these needs by collecting a different set of artifacts related to the situation.

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

### Define artifacts

A structured way to define forensic artifacts was introduced by Google in development of the grr endpoint client: https://github.com/ForensicArtifacts/artifacts. We use the forked [https://github.com/forensicanalysis/artifacts](https://github.com/forensicanalysis/artifacts) as the main repository for
forensic artifacts definitions, because the main project contains [some issues](https://github.com/forensicanalysis/artifacts#backgroundhistory).

The artifacts are yaml documents that define different types of forensic artifacts:

- Paths
- Directories
- Files
- Registry Keys and Values
- WMI Queries
- Command execution

Let’s have a look at an artifact definition for Windows Prefetch files. The artifact defines the location of the prefetch files on Windows.

``` yaml
name: WindowsPrefetchFiles
doc: Windows Prefetch files.
sources:
- type: FILE
  attributes:
    paths: ['%%environ_systemroot%%\Prefetch\*.pf']
    separator: '\'
labels: [System]
supported_os: [Windows]
urls: ['http://www.forensicswiki.org/wiki/Prefetch']
```

If added to the artifactcollector and included in the configuration file, the artifactcollector would collect all .pf files in `%%environ_systemroot%%\Prefetch`. The `%%environ_systemroot%%` variable is replaced by the artifactcollector using the WindowsEnvironmentVariableSystemRoot artifact definition. Creating artifacts like can be done on a case by case basis if needed.

The artifact definition format is described in detail in the
[Style Guide](https://github.com/forensicanalysis/artifacts/blob/master/style_guide.md).

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