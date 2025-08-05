---
weight: 999
title: "Audio2D"
description: "Plays audio streams in 2D space."
icon: "square"
draft: false
toc: true
---

While not largely useful on a small scale, it can sometimes be nice to have a centralized way to play audio streams from anywhere in the program. I've found, though, that adding audio players to nodes of interest is just as if not more convenient.

This version of the module, based off of the [one-dimensional audio manager]({{< ref "docs/audio/audio_1d.md" >}}), does the same thing in 2D space.

**This module must be added as an autoload to function as intended.**

## Usage

{{< tabs tabTotal="2">}}

{{% tab tabName="GDScript" %}}

Playing an audio stream is as simple as passing it alongside a 2D position into the `Audio2D.play()` function. Keep in mind the naming can change depending on what you named the autoload for this module.

```GDScript
const HONK := preload("res://honk.tres")
Audio2D.play(HONK, Vector2(64.0, 32.0))
```

Optionally, a volume and pitch, both in linear scale, can be provided.

```GDScript
const HONK := preload("res://honk.tres")

var volume := 2.0
var pitch := 0.5

Audio2D.play(HONK, Vector2(64.0, 32.0), volume, pitch)
```

If you wish to play an audio stream on a specific audio bus, you can use the `Audio2D.play_on()` function. It follows the same format as the regular version, only with an extra argument before the optional parameters.

```GDScript
const HONK := preload("res://honk.tres")

var volume := 2.0
var pitch := 0.5

Audio2D.play_on(HONK, Vector2(64.0, 32.0), "Effects", volume, pitch)
```

{{% /tab %}}

{{% tab tabName="C#" %}}

The C# version of this module hasn't been implemented yet.

{{% /tab %}}

{{< /tabs >}}