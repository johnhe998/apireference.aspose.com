---
title: Geometry.Disjoint
second_title: Aspose.GIS for .NET API Reference
description: Geometry method. Determines if this geometry is disjoint from a specified geometry.
type: docs
weight: 190
url: /net/aspose.gis.geometries/geometry/disjoint/
---
## Geometry.Disjoint method

Determines if this geometry is disjoint from a specified geometry.

```csharp
public bool Disjoint(IGeometry other)
```

| Parameter | Type | Description |
| --- | --- | --- |
| other | IGeometry | A geometry. |

### Return Value

`true` if this geometry is "spatially disjoint" from another geometry. `false` otherwise.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |
| ArgumentException | One of the geometries is invalid in such way that operation can not be finished. |
| ArgumentException | [`SpatialReferenceSystem`](../../igeometry/spatialreferencesystem/) of geometries are not equivalent. You can use [`SpatialReferenceSystemTransformation`](../../../aspose.gis.spatialreferencing/spatialreferencesystemtransformation/) in order to convert geometries to the same spatial reference system. |

### Remarks

This method tests whether geometries are disjoint in terms of DE-9IM intersection matrix. Basically, it tests that two geometries have no common points. This method is equivalent to:

```csharp
this.Relate(other, "FF*FF****");
```

See OpenGIS Simple Features Specification for more details about DE-9IM.

### See Also

* method [Intersects](../../igeometry/intersects/)
* interface [IGeometry](../../igeometry/)
* class [Geometry](../)
* namespace [Aspose.Gis.Geometries](../../geometry/)
* assembly [Aspose.GIS](../../../)


