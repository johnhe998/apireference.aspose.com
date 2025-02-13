---
title: RotateFromEuler
second_title: Aspose.3D for .NET API Reference
description: 
type: docs
weight: 40
url: /net/aspose.threed.utilities/matrix4/rotatefromeuler/
---
## Matrix4.RotateFromEuler method (1 of 2)

Create a rotation matrix from Euler angle

```csharp
public static Matrix4 RotateFromEuler(Vector3 eul)
```

| Parameter | Type | Description |
| --- | --- | --- |
| eul | Vector3 | Rotation in radian |

### Examples

The following code shows how to create a matrix for rotate operation.

```csharp
var t = Matrix4.RotateFromEuler(new Vector3(0, Math.PI, 0));
var pos = new Vector3(1, 1, 10);
Console.WriteLine($"Transformed: {t * pos}");
```

### See Also

* struct [Vector3](../../vector3)
* struct [Matrix4](../../matrix4)
* namespace [Aspose.ThreeD.Utilities](../../matrix4)
* assembly [Aspose.3D](../../../)

---

## Matrix4.RotateFromEuler method (2 of 2)

Create a rotation matrix from Euler angle

```csharp
public static Matrix4 RotateFromEuler(double rx, double ry, double rz)
```

| Parameter | Type | Description |
| --- | --- | --- |
| rx | Double | Rotation in x axis in radian |
| ry | Double | Rotation in y axis in radian |
| rz | Double | Rotation in z axis in radian |

### Examples

The following code shows how to create a matrix for rotate operation.

```csharp
var t = Matrix4.RotateFromEuler(0, Math.PI, 0);
var pos = new Vector3(1, 1, 10);
Console.WriteLine($"Transformed: {t * pos}");
```

### See Also

* struct [Matrix4](../../matrix4)
* namespace [Aspose.ThreeD.Utilities](../../matrix4)
* assembly [Aspose.3D](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.3D.dll -->
