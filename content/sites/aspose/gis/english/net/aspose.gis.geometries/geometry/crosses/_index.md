---
title: Geometry.Crosses
second_title: Aspose.GIS for .NET API Reference
description: Geometry method. Determines if this geometry and a specified geometry cross.
type: docs
weight: 170
url: /net/aspose.gis.geometries/geometry/crosses/
---
## Geometry.Crosses method

Determines if this geometry and a specified geometry cross.

```csharp
public bool Crosses(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry. |

### Return Value

`true` if this geometry is "spatially crosses" another geometry. `false` otherwise.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | One of the geometries is invalid in such way that operation can not be finished. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### Remarks

This method tests whether geometries are crosses in terms of DE-9IM intersection matrix. Two geometries cross each other if they have some but not all interior points in common and the dimension of the intersection is less then dimension of at least one of the geometries. That is: two [`LineString`](../../linestring/)s cross, if they form an 'X' letter, a LineString and a [`Polygon`](../../polygon/) cross if LineString goes through interior of a Polygon. See OpenGIS Simple Features Specification for more details about DE-9IM and "spatially crosses" relation.

### See Also

* interface [IGeometry](../../igeometry/)
* class [Geometry](../)
* namespace [Aspose.Gis.Geometries](../../geometry/)
* assembly [Aspose.GIS](../../../)


