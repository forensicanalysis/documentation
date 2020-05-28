---
title: Forensicstore
weight: 130
description: 
---

A forensicstore is a forensic database that contains selected forensic artifacts.

# The forensicstore format

The forensicstore format implements the following conventions:

- The forensicstore is a sqlite database containing metadata element and 
compressed raw artifacts.
- Elements are represented as json objects.
- Elements are valid STIX 2.1 Observable Objects where applicable.
- Elements must not have dots (".") in their json keys.
- Files stored in the forensicstore are referenced by element attributes ending 
in `_path`, e.g. `export_path`, `stdout_path` and `wmi_path`.
- Element attributes ending in `_time` or named `atime`, `ctime` or `mtime` are
assumed to be dates and should be stored according RFC3339/ISO 8601.
- Any element stored in the forensicstore can have an errors attribute that 
contains errors that are related to retrival or processing of this element.
- Raw artifacts are stored using the deflate compression algorithm.