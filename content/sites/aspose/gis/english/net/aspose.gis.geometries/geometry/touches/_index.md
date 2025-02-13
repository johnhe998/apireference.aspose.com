---
title: Geometry.Touches
second_title: Aspose.GIS for .NET API Reference
description: Geometry method. Determines if this geometry and a specified geometry touch.
type: docs
weight: 420
url: /net/aspose.gis.geometries/geometry/touches/
---
## Geometry.Touches method

Determines if this geometry and a specified geometry touch.

```csharp
public bool Touches(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry. |

### Return Value

`true` if this geometry is "spatially touches" another geometry. `false` otherwise.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | One of the geometries is invalid in such way that operation can not be finished. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### Remarks

This method tests whether geometries touch each other in terms of DE-9IM intersection matrix. Two geometries touch each other if they have at least one boundary point in common, but no interior points. That is: two [`LineString`](../../linestring/)s touch each other if they share an endpoint, but don't share a segment, two polygons touch each other if they share part of exterior or interior ring, but their interiors don't overlap. This method is equivalent to:

```csharp
this.Relate(other, "FT*******") || this.Relate(other, "F**T*****") || this.Relate(other, "F***T****");
```

See OpenGIS Simple Features Specification for more details about DE-9IM and "spatially touches" relation.

### See Also

* interface [IGeometry](../../igeometry/)
* class [Geometry](../)
* namespace [Aspose.Gis.Geometries](../../geometry/)
* assembly [Aspose.GIS](../../../)


