---
title: Forensicstore
weight: 135
description:
---

A forensicstore is a forensic database that contains selected forensic artifacts.

# The forensicstore format (version 2)

The forensicstore format implements the following conventions:

<!-- TODO: appdata field, version field -->

- The forensicstore is a sqlite 3 database containing metadata element and
compressed raw artifacts.
- The `elements` table contains all collected registry keys and values as well as
metadata on files, paths, and processes.
- The files themselves as well as any process output is saved in the `sqlar` table.
- Elements are represented as json objects.
- Elements are valid STIX 2.1 Observable Objects where applicable.
- Files stored in the forensicstore are referenced by element attributes ending
in `_path`, e.g. `export_path`, `stdout_path` and `wmi_path`.
- Element attributes ending in `_time` or named `atime`, `ctime` or `mtime` are
assumed to be dates and should be stored according RFC3339/ISO 8601.
- Any element stored in the forensicstore can have an errors attribute that
contains `errors` that are related to retrival or processing of this element.
- Raw artifacts are stored using the deflate compression algorithm.
- Artifacts with a compressed size larger than 1,000,000,000 Byte (1 GB) cannot
be stored.
