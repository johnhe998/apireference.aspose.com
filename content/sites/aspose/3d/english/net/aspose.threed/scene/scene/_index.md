---
title: Scene
second_title: Aspose.3D for .NET API Reference
description: 
type: docs
weight: 10
url: /net/aspose.threed/scene/scene/
---
## Scene constructor (1 of 3)

Initializes a new instance of the [`Scene`](../../scene) class.

```csharp
public Scene()
```

### See Also

* class [Scene](../../scene)
* namespace [Aspose.ThreeD](../../scene)
* assembly [Aspose.3D](../../../)

---

## Scene constructor (2 of 3)

Initializes a new instance of the [`Scene`](../../scene) class with an entity attached to a new node.

```csharp
public Scene(Entity entity)
```

| Parameter | Type | Description |
| --- | --- | --- |
| entity | Entity | The initial entity that attached to the scene |

### Examples

The following code shows how to create a [`Scene`](../../scene) directly from an [`Entity`](../../entity):

```csharp
var scene = new Scene(new Box());
```

### See Also

* class [Entity](../../entity)
* class [Scene](../../scene)
* namespace [Aspose.ThreeD](../../scene)
* assembly [Aspose.3D](../../../)

---

## Scene constructor (3 of 3)

Initializes a new instance of the [`Scene`](../../scene) class as a sub-scene.

```csharp
public Scene(Scene parentScene, string name)
```

| Parameter | Type | Description |
| --- | --- | --- |
| parentScene | Scene | The parent scene. |
| name | String | Scene's name. |

### See Also

* class [Scene](../../scene)
* namespace [Aspose.ThreeD](../../scene)
* assembly [Aspose.3D](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.3D.dll -->
