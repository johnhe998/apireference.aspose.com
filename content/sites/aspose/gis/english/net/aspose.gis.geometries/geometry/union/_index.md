---
title: Geometry.Union
second_title: Aspose.GIS for .NET API Reference
description: Geometry method. Unites this geometry and a specified geometry.
type: docs
weight: 430
url: /net/aspose.gis.geometries/geometry/union/
---
## Geometry.Union method

Unites this geometry and a specified geometry.

```csharp
public IGeometry Union(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry to unite with. |

### Return Value

A geometry that represents a union of this geometry and an argument. The result geometry contains point set that present in this geometry or in an argument.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | *other* is `null`. |
| ArgumentException | One of the geometries is invalid in such way that operation can not be finished. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### See Also

* interface [IGeometry](../../igeometry/)
* class [Geometry](../)
* namespace [Aspose.Gis.Geometries](../../geometry/)
* assembly [Aspose.GIS](../../../)


