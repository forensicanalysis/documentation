---
title: Architecture
weight: 180
description:
draft: true
---

# The forensicstore format

The forensicstore format implements the following conventions:

- The forensicstore is a folder containing an `item.db` file and an arbitrary number of other folders.
- The `item.db` file contains metadata for all extracted artifacts in a forensic investigation in flattened json objects 
  in a sqlite database.
- Items are represented as json objects.
- Items are valid STIX 2.0 Observable Objects where applicable.
- Items must not have dots (".") in their json keys.
- Files stored in the forensicstore are referenced by item attributes ending in `_path`, e.g. `export_path`, 
  `stdout_path` and `wmi_path`.
- Any item stored in the forensicstore can have an errors attribute that contains errors that are related to retrival or 
  processing of this item.

## Example structure
An example directory structure for a forensicstore:

```
example.forensicstore/
├── ChromeCache
│   ├── 0003357376fd75df_0
│   └── ...
├── ChromeHistory
│   └── History
├── ...
└── item.db
```
