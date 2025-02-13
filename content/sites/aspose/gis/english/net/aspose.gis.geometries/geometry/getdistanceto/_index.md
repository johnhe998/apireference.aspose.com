---
title: Geometry.GetDistanceTo
second_title: Aspose.GIS for .NET API Reference
description: Geometry method. Computes the minimum distance between this geometry and a specified geometry.
type: docs
weight: 240
url: /net/aspose.gis.geometries/geometry/getdistanceto/
---
## Geometry.GetDistanceTo method

Computes the minimum distance between this geometry and a specified geometry.

```csharp
public double GetDistanceTo(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry to find distance to. |

### Return Value

If both geometries are not [`IsEmpty`](../isempty/) - a distance between closest points of the geometries. If at least one geometry is empty -1 is returned.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### See Also

* interface [IGeometry](../../igeometry/)
* class [Geometry](../)
* namespace [Aspose.Gis.Geometries](../../geometry/)
* assembly [Aspose.GIS](../../../)


