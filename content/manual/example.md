---
title: Hidden documentation feature page
description: Let's turn up the heat in here 🔥
weight: 100
tags: [intro]
buttons: # only on homepage?
- text: Einführung
  url: /docs
  icon: rocket
  color: primary
  inverted: true
- text: Doku
  url: /docs
  color: secondary
  icon: book
draft: true
---

## Text

Once you've completed [setup](..), you can get started adding [Markdown](https://www.markdownguide.org/) content by creating a `content` directory.

Then you can add a docs folder. You can name that folder anything you like, for example `docs` or `documentation` (or something in a different language!). For this guide, we'll call it `docs`:

## Code

```bash
mkdir content/docs
```

```yaml
---
title: My docs
description: Everything you need to know about my project
---
```

```markdown
Welcome to the docs page!
```

## Boxes

{{< success title="TOML and JSON also supported" >}}
Don't like YAML? That's okay! Hugo also supports providing document metadata in JSON or TOML. Love that flexibility 💖
{{< /success >}}

{{< info title="Available themes" >}}
You can see a listing of all available syntax highlighting themes, plus examples, in the [Chroma Style Gallery](https://xyproto.github.io/splash/docs/all.html).
{{< /info >}}

{{< warning title="Available themes" >}}
You can see a listing of all available syntax highlighting themes, plus examples, in the [Chroma Style Gallery](https://xyproto.github.io/splash/docs/all.html).
{{< /warning >}}

{{< requirement title="Available themes" >}}
You can see a listing of all available syntax highlighting themes, plus examples, in the [Chroma Style Gallery](https://xyproto.github.io/splash/docs/all.html).
{{< /requirement >}}

{{< danger title="Available themes" >}}
You can see a listing of all available syntax highlighting themes, plus examples, in the [Chroma Style Gallery](https://xyproto.github.io/splash/docs/all.html).
{{< /danger >}}
