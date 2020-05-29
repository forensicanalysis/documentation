---
title: Acquisition with the artifactcollector
weight: 2
description:
---

{{< danger title="" >}}
The artifactcollector behaves similar to malware as it collects
critical system files and might be detected as a
virus or malware.
{{< /danger >}}

## What is the artifactcollector?

The artifactcollector is a tool to collect forensic artifacts on a system. It
can be used in forensic investigations to extract specific data instead of
creating full disk images.

<!--Based on [artifact definitions](../../development/artifacts) in the established forensicartifacts-format, -->
The artifactextractor can collect low-level (like $MFT) and high-level file artifacts as well as registry keys (e.g. run keys) which can then be used in forensic investigations.

![](/documentation/docs/usage/ac.png)

**Figure  1. Running the artifactextractor on Windows.**

The artifactcollector is a single binary that can be transferred to computers which are part of a forensic investigation.

## Download

All releases of the artifactcollector can be downloaded from [GitHub](https://github.com/forensicanalysis/artifactcollector/releases). Prebuild
artifactcollectors for Windows, Linux and macOS are availabe. Those
artifactcollectors collect a predefined set of artifacts which are mostly taken
from the Sans FOR500 training. Sans provides a comprehensive
[poster](https://www.sans.org/security-resources/posters/windows-forensic-analysis/170/download)
explaining those artifacts.



## Usage

On Windows the `artifactcollector.exe` can be executed by double clicking it
on the investigated machine. The user will be provided with a
[UAC prompt](https://en.wikipedia.org/wiki/User_Account_Control) because the
artifactcollector required administrator rights to run. The collection takes
somes minutes, depending on processing power and contained artifacts.

On Linux and macOS the `artifactcollector` needs to be executed as root, e.g.
`sudo artifactcollector`. macOS can still prevent the execution, in this case
right click the artifactcollector, select "Open", confirm "Open" and afterwards
try again with `sudo artifactcollector`.


## Output

The artifactcollecor will create a .forensicstore file and a log file. The log file serves two purposes: inform an investigator about errors during the collection but also give the user a wayto know what elements were extracted. The forensicstore contains the results of the extraction and needs to be transferred back to the investigator.

<!-- The output of the artifactcollector is saved in the [forensicstore format](../../development/forensicstore). This format is a sqlite database than includes metadata elements and the collected
files. While the investigator can use the database directly, automated processing
should be done using the forensicstore libraries ([Go](https://github.com/forensicanalysis/forensicstore), [Python](https://github.com/forensicanalysis/pyforensicstore)). -->
