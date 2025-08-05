---
weight: 999
title: "SceneManager"
description: "Manages the flow of scenes in the game, facilitating background loading and transitions."
icon: "movie"
draft: false
toc: true
---

One of the most common parts of a game's flow is the changing of scenes. Loading them in the main thread can cause performance issues, though, which is why Godot provides a way to load resources in a separate thread. However, GDScript's lack of proper async support forces you to do that in a less than good looking way.

The `SceneManager` module aims to fix this issue while also providing signals to facilitate implementing transitions, as well as storing the currently loaded scene's path in memory.

**This module must be added as an autoload to function as intended.**

## Usage

{{< tabs tabTotal="2">}}

{{% tab tabName="GDScript" %}}

`SceneManager` only has one function: `SceneManager.open()`. When provided with a path, this function will asynchronously load a `PackedScene` and have the scene tree switch to it once it's done.

`SceneManager.started_loading` is emitted once the scene is located and starts being loaded. `SceneManager.finished_loading` is emitted once the scene finishes loading and is the scene tree switches to it.

**Keep in mind `SceneManager` is supposed to replace both `SceneTree.change_scene_to_file()` and `SceneTree.change_scene_to_packed()`.**

{{% /tab %}}

{{% tab tabName="C#" %}}

The C# version of this module hasn't been implemented yet.

If all you wish is to load scenes asynchronously, you can do that by calling `ResourceLoader.load()` inside a function declared as `async`.

{{% /tab %}}

{{< /tabs >}}