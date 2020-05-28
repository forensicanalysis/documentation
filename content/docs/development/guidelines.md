---
title: Development Guidelines
weight: 190
description:
draft: true
---

## Code

- Solve the 80%
- No overengineering, solve real problem first
- Be explicit, use no magic
- Stability over features

## Code Review

- Use Code Reviews where possible
- Maximum Linter
- Maintain a stable master
- Use Semantic Versioning

## CLI

- Use [known options](https://www.gnu.org/prep/standards/html_node/Option-Table.html#Option-Table) 
    where possible (e.g. --verbose, --version, --help, --output)
- Use git and docker as examples for nested command line tools

## GUI

- Use material design
- Colors
  - Primary color is #ef5350
  - Secondary color is #37474f
- Font
  - Headlines: [Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab)
  - Text: [Roboto](https://fonts.google.com/specimen/Roboto)
  - Code: [Roboto Mono](https://fonts.google.com/specimen/Roboto+Mono)