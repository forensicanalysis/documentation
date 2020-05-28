---
title: Usage
weight: 1
description:
---


{{< warning title="" >}}
The elementary tools can be used as an entry point for your analysis. 
Always double check your results. 
{{< /warning >}}



## The elementary workflow

The elementary workflow (not to be confused with the elementary workflow 
command) is centered around the forensicstore database file. The forensicstore 
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

<script async src="https://unpkg.com/mermaid@8.2.3/dist/mermaid.min.js"></script>