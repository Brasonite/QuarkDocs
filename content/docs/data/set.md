---
weight: 999
title: "Set"
description: "A hash set implementation based on a dictionary."
icon: "data_object"
draft: false
toc: true
---

While Godot _does_ contain the basic data structures often used in game development, the array and the dictionary, it does not contain a hash set implementation. This module fixes that by adding a lightweight alternative implemented using types already present in the engine.

In short, a hash set is a data structure that can store an _unordered_ list of _unique_ values. This means that unlike an array, adding the same item twice _will not_ store two copies of it. Instead, only one copy of that item will be kept.

## Usage

{{< tabs tabTotal="2">}}

{{% tab tabName="GDScript" %}}

In order to use the `Set`, you will first need to instantiate it as an object.

```GDScript
var my_set := Set.new()
```

You can add values using `Set.add()`, as well as remove them using `Set.remove()`.

```GDScript
my_set.add(21)
my_set.remove(21)
```

To check if the set contains a value, you can use `Set.has()`.

```GDScript
if my_set.has(21):
    print("Has 21!")
```

To check if the set is empty, you can use `Set.is_empty()`.

```GDScript
if my_set.is_empty():
    print("Set is empty!)
```

To get a set's size, you can use `Set.size()`.

```GDScript
print(my_set.size())
```

If the set only has one value, you can get it by using the `Set.single()` function. If the set has a size other than 1, it will return null and print an error.

```GDScript
var my_only_value = my_set.single()
```

Lastly, if you want to get a list of all values in a set, you can use `Set.values()`.

```GDScript
for value in my_set.values():
    print(value)
```

Sometimes, it can be useful to be notified whenever a set's values have changed. In that case, you can connect to the `Set.values_changed` signal.

```GDScript
my_set.values_changed.connect(func(): print("Set updated!"))
```

{{% /tab %}}

{{% tab tabName="C#" %}}

C# already has a hash set implementation in its standard library. You should opt to use it over anything in Quark.

Refer to [the official documentation](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1) for more information.

{{% /tab %}}

{{< /tabs >}}