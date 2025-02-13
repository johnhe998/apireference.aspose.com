---
title: TransformMatrix
second_title: Aspose.3D for .NET API Reference
description: 
type: docs
weight: 90
url: /net/aspose.threed/transform/transformmatrix/
---
## Transform.TransformMatrix property

Gets or sets the transform matrix.

```csharp
public Matrix4 TransformMatrix { get; set; }
```

### Remarks

Assign on this will reset the [`Translation`](../translation), [`Scale`](../scale) and [`Rotation`](../rotation), the [`GeometricRotation`](../geometricrotation), [`GeometricScaling`](../geometricscaling) and [`GeometricTranslation`](../geometrictranslation) will not be affected.

### Examples

```csharp
Node node = new Node();
node.Transform.TransformMatrix = Matrix4.Identity;
```

### See Also

* struct [Matrix4](../../../aspose.threed.utilities/matrix4)
* class [Transform](../../transform)
* namespace [Aspose.ThreeD](../../transform)
* assembly [Aspose.3D](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.3D.dll -->
