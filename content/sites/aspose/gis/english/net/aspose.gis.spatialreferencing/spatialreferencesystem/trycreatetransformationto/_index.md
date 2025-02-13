---
title: SpatialReferenceSystem.TryCreateTransformationTo
second_title: Aspose.GIS for .NET API Reference
description: SpatialReferenceSystem method. Creates transformation from this SpatialReferenceSystem to another SpatialReferenceSystem.
type: docs
weight: 230
url: /net/aspose.gis.spatialreferencing/spatialreferencesystem/trycreatetransformationto/
---
## SpatialReferenceSystem.TryCreateTransformationTo method

Creates transformation from this `SpatialReferenceSystem` to another `SpatialReferenceSystem`.

```csharp
public bool TryCreateTransformationTo(SpatialReferenceSystem targetSrs, 
    out SpatialReferenceSystemTransformation value)
```

| Parameter | Type | Description |
| --- | --- | --- |
| targetSrs | SpatialReferenceSystem | Another `SpatialReferenceSystem`. |
| value | SpatialReferenceSystemTransformation& | When this methods returns `true`, contains a transformation; otherwise, contains `null`. |

### Return Value

Transformation from this `SpatialReferenceSystem` to another `SpatialReferenceSystem`.

`true` if transformation was created successfully; `false` otherwise.

### See Also

* method [CreateTransformationTo](../createtransformationto/)
* class [SpatialReferenceSystemTransformation](../../spatialreferencesystemtransformation/)
* class [SpatialReferenceSystem](../)
* namespace [Aspose.Gis.SpatialReferencing](../../spatialreferencesystem/)
* assembly [Aspose.GIS](../../../)


