---
title: Cross compilation
weight: 125
description:
---

Cross compilation is a bit more difficult, as a cross compiler like MinGW is required by CGO.

Example cross compilation for Windows:

```sh
CGO_ENABLED=1 CC=i686-w64-mingw32-gcc GOOS=windows GOARCH=386 go build .
CGO_ENABLED=1 CC=x86_64-w64-mingw32-gcc GOOS=windows GOARCH=amd64 go build .
```