---
title: Overview
weight: 7
description:
---

Elementary consists of different parts that can be used together or as single tools. The following
is a very brief overview over the different parts and the overall workflow

## The elementary workflow

The elementary workflow (not to be confused with the `elementary workflow`
command) is centered around the *forensicstore* database file. The *forensicstore* 
can be created using either the [artifactcollector](acquisition) on a live 
system or from a disk image.

This forensicstore can be [processed using elementary](processing) afterwards 
to create reports to investigate e.g. connected usb devices or persistent
software.

<div class="mermaid">
graph LR;
    A[Live System] -->|artifactcollector| B(forensicstore)
    G[Disk Image] -->|elementary run import-image| B(forensicstore)
    B -->|elementary run x| D[Report]
</div>

## forensicstore

The *forensicstore* provides a storage abstraction of collected forensic information as a single
file. This makes the *forensicstore* very easy to handle and transfer. Storage is provided for
binary data (e.g. file extracts) as well as structured data like Windows registry keys. Some formats
for structured data are loosely based on
[STIX 2.1](https://docs.oasis-open.org/cti/stix/v2.1/csprd01/stix-v2.1-csprd01.html), but can also
be completely user-defined.

*forensicstore* contents can be queried programatically using
[Python](https://github.com/forensicanalysis/pyforensicstore) or
[Go](https://github.com/forensicanalysis/forensicstore). It is also possible to query the store
using the [Command line](https://github.com/forensicanalysis/elementary).  Since we rely on SQLite
as the storage backend, further options to access the store are available using third-part tools.

## artifactcollector

The *artifactcollector* (**ac**) is a standalone collection utility written in Go. It can be used
in forensic investigations to extract specific data instead of creating full disk images. The
artifactextractor can collect low-level (like `$MFT`) and high-level file artifacts as well as
registry keys which can then be used in forensic investigations.

The user can define the artifacts to collect using simple YAML definition files. 
Output will be collected in a *forensicstore* file.

## Workflows

The *elementary* binary will process data in a *forensicstore* using various processing steps to
extract forensically interesting information. The processing steps can be customized using a simple
YAML configuration file, making data processing very flexible and allowing to include all kinds of
already existing and tested processing tools into the workflow.

## Reporting

Workflow steps can optionally output structured or unstructured report data that will be saved to
the *forensicstore* and to separate output files for analysis.
