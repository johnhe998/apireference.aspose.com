---
title: FromStream
second_title: Aspose.3D for .NET API Reference
description: 
type: docs
weight: 30
url: /net/aspose.threed/scene/fromstream/
---
## Scene.FromStream method (1 of 3)

Opens the scene from given stream using specified file format.

```csharp
public static Scene FromStream(Stream stream, FileFormat format, 
    CancellationToken cancellationToken = default)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | Input stream, user is responsible for closing the stream. |
| format | FileFormat | File format. |
| cancellationToken | CancellationToken | Cancellation token to the load task |

### Examples

The following code shows how to create a scene from a stream

```csharp
using(var stream = new FileStream("input.fbx", FileMode.Open))
{
    Scene scene = Scene.FromStream(stream);
}
```

### See Also

* class [FileFormat](../../fileformat)
* class [Scene](../../scene)
* namespace [Aspose.ThreeD](../../scene)
* assembly [Aspose.3D](../../../)

---

## Scene.FromStream method (2 of 3)

Opens the scene from given stream using specified IO config.

```csharp
public static Scene FromStream(Stream stream, LoadOptions options, 
    CancellationToken cancellationToken = default)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | Input stream, user is responsible for closing the stream. |
| options | LoadOptions | More detailed configuration to open the stream. |
| cancellationToken | CancellationToken | Cancellation token to the load task |

### Examples

The following code shows how to create a scene from a stream with load options

```csharp
var opts = new FbxLoadOptions();
opts.LookupPaths.Add("textures");
using(var stream = new FileStream("input.fbx", FileMode.Open))
{
    Scene scene = Scene.FromStream(stream, opts);
}
```

### See Also

* class [LoadOptions](../../../aspose.threed.formats/loadoptions)
* class [Scene](../../scene)
* namespace [Aspose.ThreeD](../../scene)
* assembly [Aspose.3D](../../../)

---

## Scene.FromStream method (3 of 3)

Opens the scene from given stream

```csharp
public static Scene FromStream(Stream stream, CancellationToken cancellationToken = default)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | Input stream, user is responsible for closing the stream. |
| cancellationToken | CancellationToken | Cancellation token to the load task |

### Examples

The following code shows how to create a scene from a stream with a cancellation token source

```csharp
var cts = new CancellationTokenSource();
using(var stream = new FileStream("input.fbx", FileMode.Open))
{
    Scene scene = Scene.FromStream(stream, cts.Token);
}
```

### See Also

* class [Scene](../../scene)
* namespace [Aspose.ThreeD](../../scene)
* assembly [Aspose.3D](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.3D.dll -->
