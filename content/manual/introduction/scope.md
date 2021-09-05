---
title: Scope
weight: 5
description:
---

# Audience
While the artifactcollector can be run without special IT expertise the
elementary tooling and this documentation is aimed at forensicators, incident
responders and analysts.


# What's in scope

The Elementary project aims to develop open source tools for Digital Forensics and Incident Reponse
(**DFIR**). The project will support all phases of an investigation:

1. Acquisition of relevant evidence extracts
1. Processing of data files
1. Human and machine-readable reporting of findings

# What's not in scope

Since Elementary is primarily meant for quick and semi-automated investigations, there is currently
no plan to support the following workflows:

**Case management**
: As we will see, a *forensicstore* is meant to hold forensic information. The user may choose
to use this abstraction to separate single machines or whole cases, whichever fits best with the
investigation at hand.

**Full acquisitions**
: While supported as an input format for further processing, we do not plan to provide tooling to
create or manage full disk disk images or memory dumps.

**Chain-of-Custody tracking**
: We propose to use an external tool for any needed CoC-tracking.
