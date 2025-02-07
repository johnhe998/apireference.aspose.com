---
title: Polygon.AddInteriorRing
second_title: Aspose.GIS for .NET API Reference
description: Polygon method. Adds an interior ring.
type: docs
weight: 90
url: /net/aspose.gis.geometries/polygon/addinteriorring/
---
## Polygon.AddInteriorRing method

Adds an interior ring.

```csharp
public void AddInteriorRing(ILinearRing ring)
```

| Parameter | Type | Description |
| --- | --- | --- |
| ring | ILinearRing | The ring to add. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | The argument is `null`. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of this geometry and [`SpatialReferenceSystem`](../spatialreferencesystem/) of argument are both not `null` and don't equal to each other. |

### See Also

* interface [ILinearRing](../../ilinearring/)
* class [Polygon](../)
* namespace [Aspose.Gis.Geometries](../../polygon/)
* assembly [Aspose.GIS](../../../)


